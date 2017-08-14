##  Lifecycle methods

#### When an instance of a component is being created and inserted into the DOM
##### [Mounting](https://facebook.github.io/react/docs/react-component.html#mounting)
1. [`constructor()`](https://facebook.github.io/react/docs/react-component.html#constructor)
    * Called before the component is added to the DOM
    * Initial state should be initialized here
    * When using an ES6 class to create the component, `super()` needs to be called within the constructor before any other code is added. This will make sure the code from the extended component gets run first without being overriden.
      * Example: 
          ```js
            constructor(props) {
              super(props);
              this.state = {
                color: props.initialColor
              };
            }```
2. `componentWillMount()`
3. `render()`
4. `componentDidMount()`
