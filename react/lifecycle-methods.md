##  [Lifecycle methods](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/lifecycle_methods_overview.html)

![Lifecycle Methods Diagram](https://pasteboard.co/GFD1P74.png)

#### Birth/Mounting phase: When an instance of a component is being created and inserted into the DOM
##### [Mounting](https://facebook.github.io/react/docs/react-component.html#mounting)
1. [`constructor()`](https://facebook.github.io/react/docs/react-component.html#constructor)
    * Called before the component is added to the DOM.
    * Initial state should be initialized here.
    * When using an ES6 class to create the component, `super()` needs to be called within the constructor before any other code is added. This will make sure the code from the extended. component gets run first without being overriden.
      * Example: 
          ```js
            constructor(props) {
              super(props);
              this.state = {
                color: props.initialColor
              };
            }
        ```
    * **More Info: [Initialization & Construction](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/birth/initialization_and_construction.html)**
2. [`componentWillMount()`](https://facebook.github.io/react/docs/react-component.html#componentwillmount)
    * Last step directly before the component is added to the DOM.
    * Since the component has not been rendered to the screen, no operations involving the DOM can be performed here.
    * **More Info: [Pre-mounting with componentWillMount()](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/birth/premounting_with_componentwillmount.html)**
3. [`render()`](https://facebook.github.io/react/docs/react-component.html#render)
    * Adds the component to the DOM.
    * This step is required.
    * Define JSX here.
    * Do not modify component state here.
    * If nothing should be rendered, then return `null` or `false`.
    * **More Info: [Component render()](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/birth/component_render.html)**
4. [`componentDidMount()`](https://facebook.github.io/react/docs/react-component.html#componentdidmount)
    * Run directly after a component is added to the DOM.
    * AJAX requests should be performed here since it is guaranteed that there's a component to update.
    * Any other operations that require the component to be added to the DOM should be performed here.
    * **More Info: [Post-mount with componentDidMount()](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/birth/post_mount_with_component_did_mount.html)**
    
<br>

#### Growth/Update phase: When an instance of a component has had its state or props changed, thereby triggering a re-render
##### [Updating](https://facebook.github.io/react/docs/react-component.html#updating)
1. [`componentWillReceiveProps()`](https://facebook.github.io/react/docs/react-component.html#componentwillreceiveprops)
    * Run when a component instance's props have possibly changed.
    * This is only run when props are updated and not on initial component intialization.
    * This step can be used be used to update state based on the prop changes.
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
    * Run before a component instance is re-rendered.
    * Return `false` from this method to stop React from re-rendering the component. This may be useful when a prop or state has been changed that you deem not to be important enough for a re-render. The default behavior of a component is to re-render on every prop or state change.
      * Example:
          ```js
          shouldComponentUpdate(nextProps, nextState) {
            return this.props.engagement !== nextProps.engagement || this.state.input !== nextState.input;
          }
          ```
    * If this method returns `false`, none of the later lifecycle methods will be run for this update event.
    * **More Info: [Using shouldComponentUpdate()](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/update/using_should_component_update.html)**
3. [`componentWillUpdate()`](https://facebook.github.io/react/docs/react-component.html#componentwillupdate)
    * Run directly before new props are rendered or new state is updated.
    * Use this step to perform operations based on the new prop or state changes.
    * You can not call `this.setState()` here. Use `componentWillReceiveProps()` instead to do that.
    * **More Info: [Tapping into componentWillUpdate()](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/update/tapping_into_componentwillupdate.html)** 
4. [`render()`]()
    * Refer to `render()` definition above.
5. [`componentDidUpdate()`](https://facebook.github.io/react/docs/react-component.html#componentdidupdate)
   * Similar to `componentDidMount()`.
   * Run directly after a component is added to the DOM.
   * Any other operations that require the component to be added to the DOM should be performed here.
     * Example:
         ```js
         componentDidUpdate(prevProps, prevState) {
          // Example: Update a third-party library chart only if the data has changed
          if (prevProps.data !== this.props.data) {
            this.chart = c3.load({
              data: this.props.data
            });
          }
        }
         ```
    * **More Info: [Post-Render with componentDidUpdate()](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/update/postrender_with_componentdidupdate.html)**
    
<br>

#### Death/Unmount phase: When an instance of a component is destroyed
##### [Unmounting](https://facebook.github.io/react/docs/react-component.html#unmounting)
1. [`componentWillUnmount()`](https://facebook.github.io/react/docs/react-component.html#componentwillunmount)
    * Run directly before a component is removed from the DOM and destroyed.
    * Any cleanup operations should be performed here, such as:
      * Cancel network requests
      * Clean up any DOM elements that were created in `componentDidMount()`
      * Remove event listeners associated with the component
        * Example:
            ```js
            componentWillUnmount() {
              window.removeEventListener('resize', this.resizeListener);
            }
            ```
    * **More Info: [Using componentWillUnmount()](https://developmentarc.gitbooks.io/react-indepth/content/life_cycle/death_unmounting_indepth.html)**
