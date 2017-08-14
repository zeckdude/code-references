## Implementation

#### Steps to make Redux work in React

For the steps below, refer to these code samples:
```js
/***   reducers/LibraryReducer.js - Get a JSON object and export it   ***/

import libraryData from './LibraryList.json';

// Return the data from the JSON file. In a real app, this would be a JSON response from an API call.
export default () => libraryData;
```

```js
/***   reducers/index.js - Define the reducers that will be exported   ***/

import { combineReducers } from 'redux';
import LibraryReducer from './LibraryReducer';

// Exporting reducers to use in the app
export default combineReducers({
  libraries: LibraryReducer
});
```

```js
/***   index.js - Initiate the app, wrap it in a <Provider> while passing it a reference to a new store while defining the reducers to create initial state   ***/
import React from 'react';
import { render } from 'react-dom';
import { Provider } from 'react-redux';
import { createStore } from 'redux';
import reducers from './reducers';
import LibraryList from './components/LibraryList';

const App = () => {
  // Create a global store that is using the specified reducers to get the state
  return (
    <Provider store={createStore(reducers)}>
      <div>
        <LibraryList />
      </div>
    </Provider>
  );
};

render(<App/>, document.querySelector('#main'));
```

<br>

```js
/***   LibraryList.js - Component that needs access to the store. It uses the connect() method to request specified state from the store and passes it in as props to the component.    ***/

import React, { Component } from 'react';
import { connect } from 'react-redux';

class LibraryList extends Component {
  render() {
    console.log(this.props.libraries);
  }
}

// Create a connection between the redux store and the component
  // Take the global state and map specific state as props to pass to the component
  const mapStateToProps = state => {
    return { libraries: state.libraries };
  };

  // The connect() helper method makes the properties in the returned
  // object (from the mapStateToProps function) available in the render method as props
  export default connect(mapStateToProps)(LibraryList);
```

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

3. Render the app to the screen including any descendant components within it.
   * Relevant code:
   
       ```js
       render(<App/>, document.querySelector('#main'));
       ```
       
<br>

4. Any components that need access to the store uses the connect() method to pass the specified state property to the component.
     The connect() method has access to the store within the <Provider> component and can request specific state properties to pass to another component as props.
   * Relevant code:
   
       ```js
       class LibraryList extends Component {
          render() {
            console.log(this.props);
          }
        }

        const mapStateToProps = state => {
          return { libraries: state.libraries };
        };

        export default connect(mapStateToProps)(LibraryList);
       ```
