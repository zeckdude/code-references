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

<br>

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
import placeImage from './src/assets/barbados.jpg';


const MyComponent = (props) => {
  return (
    <View>
    
      // Image with a fixed height/width
      // Use a filepath to get the image
      <Image 
        style={{ height: 50, width: 50 }} // It is absolutely necessary to provide a width/height in order for the image to appear
        source={{ uri: props.image_filename }}
      />
      
      // Image with 100% width
      // Use an imported image from a relative location 
      <Image 
        style={fullWidthImageStyles}
        source={placeImage}
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
##### [*See example of code*](https://snack.expo.io/SkOWpL1Ff)

<br >

##### [ScrollView](https://facebook.github.io/react-native/docs/scrollview.html)
*Enable scroll functionality on a View. Used instead of a View component. Only use this for a view that is known to be a limited area. For adding a scrollable view to a list that may grow, use [`<FlatList>`](https://github.com/zeckdude/code-references/blob/master/react/react-native/component.md#flatlist).*
```js
import { ScrollView } from 'react-native';

const AlbumList = () => {
  return (
    <ScrollView>
      ...
    </ScrollView>
  );
}
```
##### [*See example of code*](https://snack.expo.io/Sk8-7vyYG)

<br>


##### [FlatList](https://facebook.github.io/react-native/docs/flatlist.html)
*Provides a scrollbar to a list of data. It uses lazy loading to only show data for the viewing area and loads in more when scrolled making it much more performant than [`<ScrollView>`](https://github.com/zeckdude/code-references/blob/master/react/react-native/component.md#scrollview).*
```js
import { FlatList, View } from 'react-native';

const AlbumList = () => {
  return (
    <FlatList 
      data={albums}
      renderItem={(info) => (
        <View>
          {info.item.value}
        </View>
      )}
    />
  );
}
```
##### [*See example of code*](https://snack.expo.io/S132Ts1tz)

<br>

##### [Linking](https://facebook.github.io/react-native/docs/linking.html)
*Create a link that opens the browser and takes the user to the specified URL*
```js
import { Text, Linking } from 'react-native';

const myComponent = () => {
  return (
    <Text onPress={() => Linking.openURL('http://www.google.com')}>
        Go to Google
    </Text>
  );
}
```
##### [*See example of code*](https://snack.expo.io/BJScM4JKM)
