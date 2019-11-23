## shouldComponentUpdate()

By default, when a component re-renders (due to changes to its props or local state), it will automatically re-render all of its children components as well. `shouldComponentUpdate()` can be used on the children components to determine when they should be re-rendered

Example of children components being re-rendered because of a state change on its ancestor:

https://stackblitz.com/edit/demo-react-descendants-render-problem

<br>

#### Using `shouldComponentUpdate()` to control when a component is re-rendered

Demo: https://stackblitz.com/edit/demo-react-class-component-shouldcomponentupdate

```js
import React, { Component } from "react";
import Child from "./Child";

export default class Parent extends Component {
  shouldComponentUpdate(nextProps, nextState) {
    if (nextProps.name !== this.props.name) {
      return true;
    }

    return false;
  }

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
