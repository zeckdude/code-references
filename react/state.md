## State

#### Rules of State
* Definition of state: A plain javascript object used to record dynamic data that can be changed
* When we need to update what a component shows, call `this.setState()`
* Only change state with `setState()`, never assign anything to `this.state` directly (unless setting the initial state values)
* If you need to use `setState()` to update a flag based on its previous value, pass `setState()` a function that returns an object and references `prevState` instead of `this.state`, since `this.state` isn't reliable as it may be updated asynchronously (see below)

<br>

#### Set initial state values
##### [Set a property of the component in the constructor method - ES6](https://stackoverflow.com/a/30668609/83916)
```js
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { /* initial state */
      orders: [] 
    };
  }
}
```

<br>

##### [Set a static property on the component using property initializers - ES7](https://babeljs.io/blog/2015/06/07/react-on-es6-plus#property-initializers)
```js
class MyComponent extends React.Component {
  state = { /* initial state */
    orders: [] 
  };
}
```

<br>

##### [getInitialState() - ES5](https://stackoverflow.com/a/30668609/83916)
```js
var MyComponent = React.createClass({
  getInitialState() {
    return { /* initial state */
      orders: []
    };
  },
});
```

<br>

#### Set state values after initialization
##### [setState()](https://facebook.github.io/react/docs/react-component.html#setstate)
##### [Using a function in `setState` instead of an object](https://medium.com/@shopsifter/using-a-function-in-setstate-instead-of-an-object-1f5cfd6e55d1)
```js
this.setState({ orders: orders });

// Using destructuring
this.setState({ orders });

// If you need to use `setState()` to update a flag based on its previous value, pass `setState()` a function that returns an object and references `prevState` instead of `this.state`, since `this.state` isn't reliable as it may be updated asynchronously
// Instead of
// this.setState({ animationIsActive: !this.state.animationIsActive });
// Use this
this.setState((prevState, props) => {
  return {
    animationIsActive: !prevState.animationIsActive
  };
});
```
