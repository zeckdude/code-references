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

#### Common React Native Components
##### [View](https://facebook.github.io/react-native/docs/view.html)
```js
import { View } from 'react-native';

const MyComponent = () => {
  return (
    <View>
      ... // The View component acts as a container and is similar to the `div` tag in HTML
    </View>  
  );
};
```

<br>

##### [Text](https://facebook.github.io/react-native/docs/text.html)
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

<br>

##### [Image](https://facebook.github.io/react-native/docs/image.html)
```js
import { View, Image } from 'react-native';


const MyComponent = (props) => {
  return (
    <View>
    
      // Image with a fixed height/width
      <Image 
        style={{ height: 50, width: 50 }} // It is absolutely necessary to provide a width/height in order for the image to appear
        source={{ uri: props.image_filename }}
      />
      
      // Image with 100% width
      <Image 
        style={fullWidthImageStyles}
        source={{ uri: props.image_filename }}
      />
    </View>  
  );
};

// Strange combination of styles necessary to get the 100% width image to appear
const fullWidthImageStyles = {
  width: null,
  height: 300,
  flex: 1
};
```

<br >

##### [ScrollView](https://facebook.github.io/react-native/docs/scrollview.html)
*Enable scroll functionality on a View. Used instead of a View component.*
```js
import { AppRegistry, View, ScrollView } from 'react-native';

const AlbumList = () => {
  return (
    <ScrollView>
      ...
    </ScrollView>
  );
}

const App = () => (
  <View style={{ flex: 1 }}> // Add `flex: 1` on the outermost parent element to eliminate strange rendering issues
    <AlbumList />
  </View>
);

AppRegistry.registerComponent('myApp', () => App);

```

