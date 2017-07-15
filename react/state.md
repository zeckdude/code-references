## State

#### Setting initial state
##### [Setting a property of the component in the constructor method - ES6](https://stackoverflow.com/a/30668609/83916)
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

##### [Setting a static property on the component using property initializers - ES7](https://babeljs.io/blog/2015/06/07/react-on-es6-plus#property-initializers)
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
