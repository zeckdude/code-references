## Props

#### Rules of Props
* Definition of props: A plain javascript object used to pass data to child components

<br>

#### Passing and receiving props
##### [Transferring Properties](https://www.kirupa.com/react/transferring_properties.htm)
*In parent component*
```js
import AlbumDetail from './AlbumDetail';

const Main = () => {
  return (
    <div>
      <AlbumDetail title={album.title} name={album.name} />
    </div>
  )
}
```

*In child components*
```js
// As a stateless function
const AlbumDetail = (props) => {
  return (
    <div>
      <h1>{props.title}</h1>
      <h2>{props.name}</h2>
    </div>
  )
}

// As a class component
class AlbumDetail extends React.Component {
  render(
    return (
      <div>
        <h1>{this.props.title}</h1>
        <h2>{this.props.name}</h2>
      </div>
    )
  )
}
```

<br>

#### Passing and receiving the contents of a component
##### [React This Props Children](https://learn.co/lessons/react-this-props-children)
*In parent component*
```js
import AlbumDetail from './AlbumDetail';

const Main = () => {
  return (
    <div>
      <AlbumDetail>
        Hey Hey Hey
      </AlbumDetail>
    </div>
  )
}
```

*In child components*
```js
const AlbumDetail = (props) => {
  return (
    <div>
      <h1>{props.children}</h1> // Outputs "Hey Hey Hey"
    </div>
  )
}
```
