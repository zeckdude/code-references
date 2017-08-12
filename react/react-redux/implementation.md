## Implementation

#### Steps to make Redux work in React

For the steps below, refer to these code samples:

    ```js
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

2. 
<br>
