## Components

#### Render the top level component to the device
##### [ReactNative.AppRegistry.registerComponent()](https://facebook.github.io/react-native/docs/appregistry.html#registercomponent)
```js
import ReactNative from 'react-native';
ReactNative.AppRegistry.registerComponent('app-name', () => App);

// Using destructuring
import { AppRegistry } from 'react-dom';
AppRegistry.registerComponent('app-name', () => App);
```
