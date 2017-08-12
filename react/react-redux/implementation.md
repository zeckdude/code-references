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

import { render } from 'react-dom';
import { Provider } from 'react-redux';
import { createStore } from 'redux';
import reducers from './reducers';

const App = () => {
  // Create a global store that is using the specified reducers to get the state
  return (
    <Provider store={createStore(reducers)}>
      <div>
        <WelcomeMessage />
      </div>
    </Provider>
  );
};

render(<App/>, document.querySelector('#main'));
```
    
1. When app boots up, create a new redux store (a collection of state properties)
   * Relevant code example:
   
       ```js
       createStore(reducers)
       ```

2. 
<br>
