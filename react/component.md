## Components

#### Different types of components
##### [Functional stateless component](https://medium.com/@npverni/how-to-declare-react-components-in-2017-2a90d9f7984c)
* Used for presenting static data
* Can't handle fetching data
* Easy to write

##### [Class component](https://medium.com/@npverni/how-to-declare-react-components-in-2017-2a90d9f7984c)
* Used for dynamic sources of data
* Handles any data that might change (fetching data, user events, etc)
* Knows when it gets rendered (useful for fetching data)
* More code to write

<br>

#### Writing a Component
##### [Using a functional stateless component](https://javascriptplayground.com/blog/2017/03/functional-stateless-components-react/)
```js
// ES5
const Username = function(props) {
  return (
    <p>The logged in user is: {props.username}</p>
  )
}

// ES6 varieties
  // Using fat-arrow syntax
  const Username = (props) => {
    return (
      <p>The logged in user is: {props.username}</p>
    )
  }

  // Using fat-arrow syntax w/ destructuring
  const Username = ({ username }) => {
    return (
      <p>The logged in user is: {username}</p>
    )
  }

  // Using fat-arrow syntax w/ destructuring on one line
  const Username = ({ username }) => <p>The logged in user is: {username}</p>
```

<br>

##### [Using React.createClass()](https://javascriptplayground.com/blog/2017/03/functional-stateless-components-react/)
```js
const Username = React.createClass({
  render() {
    return (
      <p>The logged in user is: {this.props.username}</p> // The render() method within a react component via a class has the correct context for `this`
    )
  }
})
```

<br>

##### [Using an ES6 class](https://javascriptplayground.com/blog/2017/03/functional-stateless-components-react/)
```js
class Username extends React.Component {
  render() {
    return (
      <p>The logged in user is: {this.props.username}</p> // The render() method within a react component via a class has the correct context for `this`
    )
  }
}
```

<br>

#### Render the top level component to the screen
##### [ReactDOM.render()](https://facebook.github.io/react/docs/react-dom.html#render)
```js
import ReactDOM from 'react-dom';
ReactDOM.render(<Root/>, document.querySelector('#main'));

// Using destructuring
import { render } from 'react-dom';
render(<Root/>, document.querySelector('#main'));
```

<br>

#### Render multiple child components within a component
*It is very important to [assign a unique `key` prop to each dynamic child component](https://www.tutorialspoint.com/reactjs/reactjs_keys.htm) so React has a reference to it*
##### [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
```js
this.state.albums.map(album =>
  <AlbumDetail key={album.title} album={album} />
);
```

<br>

##### [forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/foreach)
```js
this.state.albums.forEach((album, index) =>
  <AlbumDetail key={"album-" + index} album={album} />
);
```

<br>

#### How to bind `this` to be used in methods of a class-based component
##### [Bind in Render](https://medium.freecodecamp.org/react-binding-patterns-5-approaches-for-handling-this-92c651b5af56#b389)
*Convenient and easy to read, but is worse for performance because a new function is called every time the component re-renders*
```js
class Username extends React.Component {
  handleClick() {
    console.log(this.props); // `this` is now the component itself
  }

  render() {
    return (
      <SomeComponent onClick={this.handleClick.bind(this)} />
    )
  }
}
```

<br>

##### [Use Arrow Function in Render](https://medium.freecodecamp.org/react-binding-patterns-5-approaches-for-handling-this-92c651b5af56#dbb4)
*Convenient and easy to read, but is worse for performance because a new function is called every time the component re-renders*
```js
class Username extends React.Component {
  handleClick() {
    console.log(this.props); // `this` is now the component itself
  }

  render() {
    return (
      <SomeComponent onClick={e => handleClick(e)} />
    )
  }
}
```

<br>

##### [Bind in Constructor](https://medium.freecodecamp.org/react-binding-patterns-5-approaches-for-handling-this-92c651b5af56#e3d6)
*Requires the binding to be added to the constructor which is a bit tedious, but is better for performance because a new function isn't called every time the component re-renders*
```js
class Username extends React.Component {
  constructor(props) {
    super(props);
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    console.log(this.props); // `this` is now the component itself
  }

  render() {
    return (
      <SomeComponent onClick={() => this.handleClick()} />
    )
  }
}
```

<br>

##### [Use Arrow Function in Class Property - stage-2 feature](https://medium.freecodecamp.org/react-binding-patterns-5-approaches-for-handling-this-92c651b5af56#f45f)
*Best for code maintainability, readability and performance, but it is a stage-2 feature so it will require certain settings to be enabled in Babel.*
```js
class Username extends React.Component {
  handleClick = () => {
    // call this function from render 
    // and this.whatever in here works fine.
  };

  render() {
    return (
      <SomeComponent onClick={handleClick()} />
    )
  }
}
```

<br>

##### [Use react-autobind package](https://www.npmjs.com/package/react-autobind)
*Requires installing & importing package, but makes code much cleaner*
```js
import autoBind from 'react-autobind';

class Username extends React.Component {
  constructor(props) {
    super(props);
    // autoBind(this); // Automatically binds all methods of the class
    autoBind(this, 'handleClick', 'anotherMethod'); // Automatically binds specified methods of the class
  }

  handleClick() {
    console.log(this.props); // `this` is now the component itself
  }

  render() {
    return (
      <SomeComponent onClick={() => this.handleClick()} />
    )
  }
}
```
