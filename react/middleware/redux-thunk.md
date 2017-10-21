## redux-thunk

Redux Thunk middleware allows you to write action creators that return a function instead of an action. The function can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods dispatch and getState as parameters. It is useful for asynchronous requests made in the action, so it can delay sending the action until the response comes back.

#### Helpful Links
| Name | Link |
|---------------|----------------------------|
| Github: Redux Thunk | https://github.com/gaearon/redux-thunk |
| RallyCoding (Stephen Grider): Basics of Redux Thunk | https://www.youtube.com/watch?v=1QI-UE3-0PU |

### Example

Enable Redux Thunk

```js
import { createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk';
import rootReducer from './reducers/index';

const store = createStore(
  rootReducer,
  applyMiddleware(thunk)
);
```

<br>

Perform an asynchronous request within an action

```js
import axios from 'axios';

export const createPost = (values, callback) => {
  const request = axios.get('https://jsonplaceholder.typicode.com/posts');

  return dispatch =>
    request.then(

      // Success callback
      ({ data }) => {
        // Dispatching the action to the reducer
        dispatch({
          type: 'CREATE_POST',
          payload: data
        });
      },

      // Error callback
      error => {
        alert('The form could not send due to a system error');
      }
    );
};
```

<br>

Check a condition before dispatching an action

```js
export const incrementIfOdd => () {
  return (dispatch, getState) => {
    const { counter } = getState();

    if (counter % 2 === 0) {
      return;
    }

    dispatch({
      type: 'INCREMENT_COUNTER'
    });
  };
}
```
