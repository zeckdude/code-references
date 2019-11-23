## Class Component

##### [Class component](class-component.md)

- Older & outdated way to keep track of state or lifecycle methods for a component
- Used for dynamic sources of data
- Handles any data that might change (fetching data, user events, etc)
- Knows when it gets rendered (useful for fetching data)
- More code to write

<br>

#### Writing a component

#### Using a class component

Demo: https://stackblitz.com/edit/demo-react-class-component

```js
import React, { Component } from "react";

export default class Counter extends Component {
  state = {
    count: this.props.initialCount
  };

  componentDidMount() {
    console.log("This only runs when the component mounts");
  }

  componentDidUpdate(prevProps, prevState) {
    console.log("This method runs whenever the component re-renders");

    if (this.state.count !== prevState.count) {
      console.log("This runs when the count property on state changes");
    }
  }

  decrementCount = () => {
    this.setState((state, props) => ({
      count: state.count - 1
    }));
  };

  incrementCount = () => {
    this.setState((state, props) => ({
      count: state.count + 1
    }));
  };

  render() {
    return (
      <>
        {this.props.name} count: {this.state.count}
        <button
          onClick={() =>
            this.setState({ ...this.state, count: this.props.initialCount })
          }
        >
          Reset
        </button>
        {/* Use the function callback when changing a state value based on its previous value in order to guarantee that the value is accurate */}
        <button onClick={this.decrementCount}>-</button>
        <button onClick={this.incrementCount}>+</button>
      </>
    );
  }
}

Counter.defaultProps = {
  count: 0,
  name: "demo"
};
```

<br>

#### How to bind `this` to be used in methods of a class-based component

##### [Use Arrow Function in Render](https://medium.freecodecamp.org/react-binding-patterns-5-approaches-for-handling-this-92c651b5af56#dbb4)

_Convenient and easy to read, but is worse for performance because a new function is called every time the component re-renders_

```js
class Username extends Component {
  handleClick(e) {
    console.log(this.props); // `this` is now the component itself
  }

  render() {
    return <SomeComponent onClick={handleClick} />;
  }
}
```

<br>

##### [Use Arrow Function in Class Property - stage-2 feature](https://medium.freecodecamp.org/react-binding-patterns-5-approaches-for-handling-this-92c651b5af56#f45f)

_Best for code maintainability, readability and performance, but it is a stage-2 feature so it will require certain settings to be enabled in Babel._

```js
class Username extends Component {
  handleClick = () => {
    // call this function from render
    // and this.whatever in here works fine.
  };

  render() {
    return <SomeComponent onClick={handleClick()} />;
  }
}
```
