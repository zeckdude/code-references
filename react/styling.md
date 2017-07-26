## Styling

Styling is a bit different in React.js than in traditional web development. It involves creating an object with rules that are passed to the component for which they should be applied.

#### Style a component using a JS object (most common way)
```js
import { View, Text } from 'react-native';

const MyComponent = (props) => {
  return (
    <View>
      <Text style={styles.textStyle}>{props.name}</Text>
    </View>
  );
};

const styles = {
  textStyle: {
    fontSize: 25
  }
};
```
