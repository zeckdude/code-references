## redux-saga

Redux Thunk middleware allows you to write action creators that return a function instead of an action. The function can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods dispatch and getState as parameters. It is useful for asynchronous requests made in the action, so it can delay sending the action until the response comes back.

#### Helpful Links
| Name | Link |
|---------------|----------------------------|
| Github: Redux Saga | https://github.com/redux-saga/redux-saga |
| Youtube: Understanding Generator Functions & Using Redux Saga | https://www.youtube.com/watch?v=o3A9EvMspig |
| Youtube: How to Make API Calls in Redux with redux-saga | https://www.youtube.com/playlist?list=PLw7fHewFA6OTyUnLiZ1HQvYdzjp9ARMQw |
| Scotch: Build A Media Library with React, Redux, and Redux-saga | https://scotch.io/tutorials/build-a-media-library-with-react-redux-and-redux-saga-part-1 |
| CodePen: Implementing AJAX with redux-saga | https://codepen.io/mentrie/pen/JKZEVa |
<br>
### Live Demo
https://stackblitz.com/edit/react-redux-saga-demo
<br><br>

![](https://raw.githubusercontent.com/zeckdude/code-references/master/img/react/redux-saga/a.jpg)

### Example

Step #1: Enable Redux Saga

```js
import { createStore, applyMiddleware } from 'redux';
import createSagaMiddleware from 'redux-saga';

import reducers from './reducers';
import sagas from './sagas';

// Create saga middleware
const sagaMiddleware = createSagaMiddleware();

// Create a store with the reducers and middleware
const store = createStore(reducers, applyMiddleware(sagaMiddleware));

// Run the Redux Saga middleware listeners
sagaMiddleware.run(sagas);
```

<br>

Step #2: A component calls an action creator

```js 
import { fetchPosts } from '../actions';

class PostsIndex extends Component {
  componentDidMount() {
    this.props.fetchPosts();
  }

  render() {
    ...
  }
}

export default connect(mapStateToProps, { fetchPosts })(PostsIndex);
```

<br>

Step #3: The action creator emits an action which only the sagas are listening for. This needs to be unique to the sagas since the reducers are listening as well and will catch the emitted action first if both the reducers and sagas are listening for the same action type.

```js 
export const types = {
  FETCH_POST: 'FETCH_POST',
  FETCH_POST_SUCCESS: 'FETCH_POST_SUCCESS'
};

export const fetchPosts = () => ({ type: types.FETCH_POSTS });

// If you need to send additional properties to the sagas, just include them in the object
// example: export const fetchPosts = id => ({ type: types.FETCH_POSTS, id });
```

<br>

Step #4: The main sagas file needs to be setup to run specific saga watcher which will listen for actions being emitted by the action creators

```js 
import 'regenerator-runtime/runtime';
import {
  watchFetchPosts
} from './PostsSagas';

// Root sagas
// Single entry point to start all sagas at once
export default function* rootSaga() {
  yield [
    watchFetchPosts()
  ];
}
```

<br>

Step #5: Create watcher and worker sagas. Watcher sagas are generator functions that listen for a specific action type being emitted. When it catches one, it will call the corresponding worker saga. A worker saga is a generator function which can perform a series to steps before ultimately dispatching a different unique action to the reducers to update the state.

```js 
import { call, put, takeEvery, takeLatest } from 'redux-saga/effects';
import axios from 'axios';
import { types } from '../actions';

const ROOT_URL = 'http://reduxblog.herokuapp.com/api';
const API_KEY = '?key=cseckler1234';

// Watcher saga
// Listen for an action and run the appropriate Worker saga
export function* watchFetchPost() {
  yield takeEvery(types.FETCH_POST, workFetchPost);
}

// Worker saga
// Respond to the actions that are caught by the watcher sagas
export function* workFetchPosts() {
  try {
    // Try to call the API
    const uri = `${ROOT_URL}/posts${API_KEY}`;
    // The call() method runs a function. Any arguments that the function needs to receive can be added as subsequent parameters.
    const response = yield call(axios.get, uri);
    // Example of additional arguments: const response = yield call(axios.post, uri, values);

    // Dispatch the action to the reducers when the response comes back
    yield put({
      type: types.FETCH_POSTS_SUCCESS,
      payload: response.data
    });
  } catch (error) {
    // Act on the error
    console.log('Request failed! Could not fetch posts.');
  }
}
```

<br>

Step #6: The reducer will the catch the action that was emitted from the saga and will update the state

```js 
import { mapKeys } from 'lodash';
import { types } from '../actions';

export default (state = {}, action) => {
  switch (action.type) {
    case types.FETCH_POSTS_SUCCESS:
      // Create a new state object that uses an AJAX request response and grabs the 'id' property from each object in the response to use as its key
      return mapKeys(action.payload, 'id');
  }

  return state;
};
```
