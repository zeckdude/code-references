## State

#### Rules of State
* Definition of state: A plain javascript object used to record dynamic data that can be changed
* When we need to update what a component shows, call `this.setState()`
* Only change state with `setState()`, never assign anything to `this.state` directly (unless setting the initial state values)
* If you need to use `setState()` to update a flag based on its previous value, pass `setState()` a function that returns an object and references `prevState` instead of `this.state`, since `this.state` isn't reliable as it may be updated asynchronously (see below)
* Don't mutate the state when updating it

<br>

#### Quick Reference Notes

| Purpose | Notes |
|---------------|----------------------------------------------------------|
| [Set initial state values](https://github.com/zeckdude/code-references/blob/master/react/state.md#set-initial-state-values) | *None* |
| [Set state values after initialization](https://github.com/zeckdude/code-references/blob/master/react/state.md#set-state-values-after-initialization) | *None* |
| [Add an item to an array in state](https://github.com/zeckdude/code-references/blob/master/react/state.md#add-an-item-to-an-array-in-state) | *None* |
| [Remove an item at a specific index from an array in state](https://github.com/zeckdude/code-references/blob/master/react/state.md#remove-an-item-at-a-specific-index-from-an-array-in-state) | *None* |
| [Remove all items with a specified value from an array in state](https://github.com/zeckdude/code-references/blob/master/react/state.md#remove-all-items-with-a-specified-value-from-an-array-in-state) | *None* |
| [Update all items with a specified value from an array in state](https://github.com/zeckdude/code-references/blob/master/react/state.md#update-all-items-with-a-specified-value-from-an-array-in-state) | *None* |
| Merge an array in state with another array | *None* |
| [Update or add a property of/to an object in state](https://github.com/zeckdude/code-references/blob/master/react/state.md#update-a-property-of-an-object-in-state) | *None* |
| [Merge the properties of an object to an object in state](https://github.com/zeckdude/code-references/blob/master/react/state.md#merge-the-properties-of-an-object-to-an-object-in-state) | *None* |
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

<br>

#### Add an item to an array in state
##### [setState()](https://facebook.github.io/react/docs/react-component.html#setstate)
##### [concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)
##### [spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
##### Supplying an object to `setState()`
```js
// Concat
this.setState({
  people: this.state.people.concat('Bob');
});

// Spread syntax
this.setState({
  people: [...this.state.people, 'Bob']
});
```
##### [Supplying a function to `setState()`](https://medium.com/@shopsifter/using-a-function-in-setstate-instead-of-an-object-1f5cfd6e55d1)
```js
// Concat
this.setState((prevState) => {
  return {
    people: prevState.people.concat('Bob')
  };
});

// Spread syntax
this.setState((prevState) => {
  return {
    people: [...prevState.people, 'Bob']
  };
});
```

<br>

##### [immutability-helper: update()](https://github.com/kolodny/immutability-helper)
```js
this.setState((prevState) => {
  return {
    people: update(prevState.people, {$push: ['Bob']})
  };
});
```

<br>


#### Remove an item at a specific index from an array in state
##### [spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
##### [slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
```js
const index = 2;
this.setState((prevState) => {
  return {
    people: [...prevState.people.slice(0, index), ...prevState.people.slice(index + 1)]
  };
});
```

<br>

##### [concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)
```js
const index = 2;
this.setState((prevState) => {
  return {
    people: [...prevState.people.slice(0, index), ...prevState.people.slice(index + 1)]
  };
});
```

<br>

##### [filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
```js
const index = 2;
this.setState((prevState) => {
  return {
    people: prevState.people.filter((person, personIndex) => personIndex !== index)
  };
});
```

<br>

##### [immutability-helper: update()](https://github.com/kolodny/immutability-helper)
```js
const index = 2;
this.setState((prevState) => {
  return {
    people: update(prevState.people, {$splice: [[index, 1]]})
  };
});
```

<br>

#### Remove all items with a specified value from an array in state
##### [filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
```js
const name = 'Jimmy';
this.setState(prevState => {
  return {
    people: prevState.people.filter(person => person !== name)
  };
});
```

<br>

#### Update all items with a specified value from an array in state
##### [filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
```js
this.setState(prevState => {
  return {
    people: prevState.people.map(name => {
      if (name === 'Jimmy') {
        return 'Bob';
      }
      return name;
    })
  };
});
```

<br>

#### Update or add a property of/to an object in state
##### [spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
```js
this.setState(prevState => {
  return {
    person: { ...prevState.person, age: 25 }
  };
});
```

<br>

##### [Object.assign()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)
```js
this.setState(prevState => {
  return {
    person: Object.assign({}, prevState.person, { age: 25 })
  };
});
```

<br>

##### [immutability-helper: update()](https://github.com/kolodny/immutability-helper)
```js
this.setState((prevState) => {
  return {
    person: update(prevState.person, {
      age: { $set: 25 }
    })
  };
});
```

<br>

#### Merge the properties of an object to an object in state
##### [spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
```js
const chrisAttributes = {
  weight: 165,
  isFromCalifornia: true
};
this.setState(prevState => {
  return {
    person: { 
      ...prevState.person, 
      ...chrisAttributes
    }
  };
});
```

<br>

##### [Object.assign()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)
```js
const chrisAttributes = {
  weight: 165,
  isFromCalifornia: true
};
this.setState(prevState => {
  return {
    person: Object.assign({}, prevState.person, chrisAttributes)
  };
});
```
