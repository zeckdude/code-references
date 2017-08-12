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
*It is very important to assign a unique `key` prop to each dynamic child component so React has a reference to it (https://www.tutorialspoint.com/reactjs/reactjs_keys.htm)*
##### [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
```js
this.state.albums.map(album =>
  <AlbumDetail key={album.title} album={album} />
);
```

<br>

##### [forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/foreach)
```js
this.state.albums.forEach(album =>
  <AlbumDetail key={album.title} album={album} />
);
```
