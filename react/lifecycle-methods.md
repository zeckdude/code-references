##  [Lifecycle methods](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/introduction.html)

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
    * Run when a component instance's props have possibly changed
    * This is only run when props are updated and not on initial component intialization
    * This step can be used be used to update state based on the prop changes
    * React has a difficult time determining if props have been changed and may therefore be run when props have not actually changed. Because of that, it is important to compare the before and after props value.
      * Example:
          ```js
          componentWillReceiveProps(nextProps) {
            if (this.props.percent !== nextProps.percent) {
              this.setState({ loaded: true });
            }
          }
          ```
    * **More Info: [Updating and componentWillReceiveProps()](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/update/component_will_receive_props.html)**
2. [`shouldComponentUpdate()`](https://facebook.github.io/react/docs/react-component.html#shouldcomponentupdate)
    * Run before a component instance is re-rendered
    * Return `false` from this method to stop React from re-rendering the component. This may be useful when a prop or state has been changed that you deem not to be important enough for a re-render. The default behavior of a component is to re-render on every prop or state change.
      * Example:
          ```js
          shouldComponentUpdate(nextProps, nextState) {
            return this.props.engagement !== nextProps.engagement || this.state.input !== nextState.input;
          }
          ```
3. [`componentWillUpdate()`](https://facebook.github.io/react/docs/react-component.html#componentwillupdate)
4. [`render()`]()
    * Refer to `render()` definition above
5. [`componentDidUpdate()`](https://facebook.github.io/react/docs/react-component.html#componentdidupdate)
