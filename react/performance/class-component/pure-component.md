## React.PureComponent()

By default, when a component re-renders (due to changes to its props or local state), it will automatically re-render all of its children components as well. The `React.PureComponent` class can be used on the children components to automatically determine when they should be re-rendered based on changes to its own state or props being passed to it. This is the preferred approach over `shouldComponentUpdate()` but since class-based components are not being used that much anymore, hooks are doing the same thing for functional stateful components. Only use this if there is a performance issue and don't just add it on all components, since that's usually not necessary.

Example of children components being re-rendered because of a state change on its ancestor:

https://stackblitz.com/edit/demo-react-descendants-render-problem

<br>

#### Using `React.PureComponent` to control when a component is re-rendered

Demo: https://stackblitz.com/edit/demo-react-class-component-pure-component

```js
import React, { PureComponent } from "react";
import Child from "./Child";

export default class Parent extends PureComponent {
  // Since no prop or local state has changed, the component is not being re-rendered
  render() {
    console.log("Parent Component renders");
    return (
      <div>
        I'm the parent component and my name is {this.props.name}
        <hr />
        <Child name="Jefferson" />
      </div>
    );
  }
}
```
