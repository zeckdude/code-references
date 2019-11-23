## React.memo()

By default, when a component re-renders (due to changes to its props or local state), it will automatically re-render all of its children components as well. The `React.memo()` HOC can be used on a component to automatically determine when it should be re-rendered based on changes to its own state or props being passed to it. Only use this if there is a performance issue and don't just add it on all components, since that's usually not necessary.

Example of children components being re-rendered because of a state change on its ancestor:

https://stackblitz.com/edit/demo-react-descendants-render-problem

<br>

#### Using `React.memo` to control when a component is re-rendered

Demo: https://stackblitz.com/edit/demo-react-functional-component-memo

```js
import React, { Component, memo } from "react";
import Child from "./Child";

function Parent({ name }) {
  console.log("Parent Component renders");
  return (
    <div>
      I'm the parent component and my name is {name}
      <hr />
      <Child name="Jefferson" />
    </div>
  );
}

export default memo(Parent);
```
