## Components

#### Different types of components

##### [Functional component](functional-component.md)

With state

- Can be used instead of class components since it can use hooks to track local state and lifecycle changes
- Used for dynamic sources of data
- Handles any data that might change (fetching data, user events, etc)
- Knows when it gets rendered (useful for fetching data)

Without state

- Used for presenting static data
- Can't handle fetching data
- Easy to write
- Does not keep local state
- Easy to re-use
- Easy to test against

##### [Class component](class-component.md)

- Older & outdated way to keep track of state or lifecycle methods for a component
- Used for dynamic sources of data
- Handles any data that might change (fetching data, user events, etc)
- Knows when it gets rendered (useful for fetching data)
- More code to write

<br>

#### Render the top level component to the screen

##### [ReactDOM.render()](https://facebook.github.io/react/docs/react-dom.html#render)

```js
import ReactDOM from "react-dom";
ReactDOM.render(<Root />, document.querySelector("#main"));

// Using destructuring
import { render } from "react-dom";
render(<Root />, document.querySelector("#main"));
```

<br>

#### Render multiple child components within a component

_It is very important to [assign a unique `key` prop to each dynamic child component](https://www.tutorialspoint.com/reactjs/reactjs_keys.htm) so React has a reference to it_

##### [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

```js
this.state.albums.map(album => <AlbumDetail key={album.title} album={album} />);
```
