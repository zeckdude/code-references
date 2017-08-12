## Implementation

#### Steps to make Redux work in React
1. When app boots up, redux creates a new store (a collection of state properties)

    ```js
    import { render } from 'react-dom';

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

<br>
