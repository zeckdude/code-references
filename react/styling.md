## Styling

Styling is a bit different in React.js than in traditional web development. It involves creating an object with rules that are passed to the component for which they should be applied.

#### Style a component using a JS object (most common way)
```js
const MyComponent = (props) => {
  return (
    <div>
      <p style={styles.textStyle}>{props.name}</p>
    </div>
  );
};

const styles = {
  textStyle: {
    fontSize: 25
  }
};
```
