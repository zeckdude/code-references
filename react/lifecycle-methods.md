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
            }
        ```
2. [`componentWillMount()`](https://facebook.github.io/react/docs/react-component.html#componentwillmount)
    * Last step directly before the component is added to the DOM
    * Since the component has not been rendered to the screen, no operations involving the DOM can be performed here
3. [`render()`](https://facebook.github.io/react/docs/react-component.html#render)
    * Adds the component to the DOM
    * This step is required
    * Define JSX here
    * Do not modify component state here
    * If nothing should be rendered, then return `null` or `false`
4. [`componentDidMount`](https://facebook.github.io/react/docs/react-component.html#componentdidmount)
    * Run directly after a component is added to the DOM
    * AJAX requests should be performed here since it is guaranteed that there's a component to update.
    * Any other operations that require the component to be added to the DOM should be performed here
    
<br>

#### When an instance of a component has had its state or props changed, thereby triggering a re-render
##### [Updating](https://facebook.github.io/react/docs/react-component.html#updating)
1. [`componentWillReceiveProps()`](https://facebook.github.io/react/docs/react-component.html#componentwillreceiveprops)
2. [`shouldComponentUpdate()`](https://facebook.github.io/react/docs/react-component.html#shouldcomponentupdate)
3. [`componentWillUpdate()`](https://facebook.github.io/react/docs/react-component.html#componentwillupdate)
4. [`render()`]()
    * Refer to `render()` definition above
5. [`componentDidUpdate()`](https://facebook.github.io/react/docs/react-component.html#componentdidupdate)
