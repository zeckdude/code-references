## Implementation

#### Guiding Principles of Redux
1. All state is stored in one location called the store (a.k.a. single source of truth).
2. State can only be changed by emitting an action which tells the store how to change the state.
3. All actions are processed by a reducer function, which returns a new value to changed the state in the store. They are considered "pure" functions because they do nothing but return a value based on their parameters. These are the rules to follow:
    * It should not make outside network or database calls.
    * Its return value depends solely on the values of its parameters
    * Its arguments should not be changed.
    * Using the same arguments, it should always return the same value
    

#### Steps to make Redux work in React

For the steps below, refer to these code samples:
```js
/***   reducers/PostsReducer.js - Update the state in the store with the payload that is provided   ***/
import { mapKeys } from 'lodash';
import { FETCH_POSTS, FETCH_POST, CREATE_POST, DELETE_POST } from '../actions';

export default (state = {}, action) => {
  switch (action.type) {
    case FETCH_POST:
      // Copy the current state and set a new property with a dynamic key value and the payload as the value
      return { ...state, [action.payload.data.id]: action.payload.data };
    case FETCH_POSTS:
      // Create a new state object that uses an AJAX request response and grabs the 'id' property from each object in the response to use as its key
      return mapKeys(action.payload.data, 'id');
    case CREATE_POST:
      // Copy the current state and set a new property with a dynamic key value and the payload as the value 
      return { ...state, [action.payload.id]: action.payload };
    case DELETE_POST:
      // Copy the current state and delete the property with the specified key
      var newState = { ...state };
      delete newState[action.payload.id];
      return newState;
  }

  return state;
};

```

```js
/***   reducers/index.js - Combine the reducers and define them as properties that will be exported   ***/

import { combineReducers } from 'redux';
import PostsReducer from './PostsReducer';
import SelectionReducer from './SelectionReducer';

// Exporting reducers to use in the app
export default combineReducers({
  posts: PostsReducer, // All reducers related to posts
  selectedPostId: SelectionReducer // Get the currently selected post ID by accessing the SelectionReducer
});
```

```js
/***   index.js - Initiate the app, wrap it in a <Provider> while passing it a reference to a new store while defining the reducers to create initial state   ***/
import React from 'react';
import { render } from 'react-dom';
import { Provider } from 'react-redux';
import { createStore } from 'redux';
import reducers from './reducers';
import PostsIndex from './components/PostsIndex';

const App = () => {
  // Create a global store that is using the specified reducers to get the state
  return (
    <Provider store={createStore(reducers)}>
      <div>
        <PostsIndex />
      </div>
    </Provider>
  );
};

render(<App/>, document.querySelector('#main'));
```

```js
/***   PostsIndex.js - Component that needs access to the store. It uses the connect() method to request specified state from the store and passes it in as props to the component, as well as to dispatch an action which will eventually set new state and re-render the component.   ***/

import { map as _map } from 'lodash';
import React, { Component } from 'react';
import { connect } from 'react-redux';
import { Link } from 'react-router-dom';
import { fetchPosts } from '../actions';

class PostsIndex extends Component {
  componentDidMount() {
    this.props.fetchPosts();
  }

  render() {
    console.log(this.props.posts);
  }
}

// Create a connection between the redux store and the component
// Take the global state and map specific state as props to pass to the component
const mapStateToProps = state => {
 return { 
   posts: state.posts 
 };
};

// The connect() helper method makes the properties in the returned
// object (from the mapStateToProps function) available in the render method as props
export default connect(mapStateToProps, { fetchPosts })(PostsIndex);
```

```js
/***   actions/index.js - Create the necessary action creators in one file. The action creator is a function with the purpose of creating an action. An action is a JS object that identifies a `type` property, which tells Redux which reducer to use as well as any other information that needs to be passed to the reducer.   ***/

export const selectLibrary = (libraryId) => {
  // Redux action
  // Actions are used to tell a reducer to update in a specific way
  // The type property is required
  return {
    type: 'select_library',
    payload: libraryId
  };
};

import axios from 'axios';

export const FETCH_POSTS = 'FETCH_POSTS';

const ROOT_URL = 'http://reduxblog.herokuapp.com/api';
const API_KEY = '?key=12345';

export const fetchPosts = () => {
  // Make AJAX request
  const request = axios.get(`${ROOT_URL}/posts${API_KEY}`);

  // By default, a Redux action will send immediately, but if the redux-promise middleware is added, it will wait for the AJAX request response and will then get the data out of the response to send to the reducer
  
  // Redux action
  // Actions are used to tell a reducer to update in a specific way
  // The type property is required
  return {
    type: FETCH_POSTS,
    payload: request
  };
  
   /*  // An alternate way to handle an AJAX request is to use the redux-thunk middlware. By returning a function, the redux-thunk middleware will wait for the AJAX response and will then provide a dispatch method in its argument to use in the then() block to dispatch the action to the reducer
     return dispatch => {
       return request.then(
         // Success callback
         ({ data }) => {
           callback();

           // Dispatching the action to the reducer
           dispatch({
             type: 'FETCH_POSTS',
             payload: data
           });
         },
         // Error callback
         error => {
           alert('The request could not be made due to a system error');
         }
       );
     };
     */
};
```

<br>

#### General Setup that needs to be in place before any flow can work 

<br>  

1. When app boots up, create a new redux store (a collection of state properties).<br>
   The store looks at the reducers that are defined and creates initial state properties based on the reducers specified.
   * Relevant code:
   
       ```js
       createStore(reducers)
       ```

<br>

2. Pass the store to the `<Provider>` component as a prop (the provider component aids in communication between React and Redux).<br>
  The provider component needs to be the outermost component element in the app so it can pass the various state properties to descendant components.
   * Relevant code:
   
       ```js
       <Provider store={createStore(reducers)}>
       ```

<br>

3. Create the necessary reducers as separate files
    * Relevant code:
   
       ```js
       // LibraryReducer.js
       import libraryData from './LibraryList.json';
       export default () => libraryData;
       
       // SelectionReducer.js
       export default (state = null, action) => {
          switch (action.type) {
            case 'select_library':
              return action.payload;
            default:
              return state;
          }
        };
       ```
       
<br>

2. Combine the reducers and define them as properties that will be exported
   * Relevant code:
   
       ```js
       export default combineReducers({
          libraries: LibraryReducer,
          selectedLibraryId: SelectionReducer
        });
       ```
    

3. Render the app to the screen including any descendant components within it.
   * Relevant code:
   
       ```js
       render(<App/>, document.querySelector('#main'));
       ```
       
<br>








       
5. Create the necessary action creators in one file.
   * Relevant code:
   
       ```js
       export const selectLibrary = (libraryId) => {
          return {
            type: 'select_library',
            payload: libraryId
          };
        };
       ```
       
       
 <br>
 
![](https://raw.githubusercontent.com/zeckdude/code-references/master/img/react/react-redux/5.png)
 
<br>

#### Flow #1: An component needs access to specific state in the store 

<br>

1. Any components that need access to the store uses the connect() method to pass the specified state property to the component.
     The connect() method has access to the store within the `<Provider>` component and can request specific state properties to pass to another component as props.
   * Relevant code:
   
       ```js
       class PostsIndex extends Component {
          render() {
            console.log(this.props.posts);
          }
       }
        
       // Grab the posts property from the store and provide it to the component as a prop
       const mapStateToProps = state => {
         return { posts: state.posts };
       };

       export default connect(mapStateToProps)(LibraryList);
       ```
       
 #### Flow #2: An action in a component updates the state in the store 
 
 <br>

1. Any components that needs to update the store uses the connect() method to dispatch an action to the reducers.
   * Relevant code:
   
       ```js
       import { fetchPosts } from '../actions';

       // The connect() method connects a component to the redux store. It creates a new component using the component specified and adds extra functionality related to redux with it.
       // There are two ways that an action can be emitted from within the component.
       
       // #1 - Using an object containing the action creator
       // The action creator must be imported into the file and defined as the second argument to connect()
       export default connect(null, { fetchPosts: fetchPosts })(LibraryList);
       
       // #2 - Using a function that returns a function to dispatch the action
       const mapDispatchToProps = dispatch => {
         return bindActionCreators({ fetchPosts: fetchPosts }, dispatch);
       };
       export default connect(mapStateToProps, mapDispatchToProps)(PostsIndex);
       ```
 
 
