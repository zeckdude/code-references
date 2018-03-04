## Touch Events
Unlike React on a browser, not every component has a touch event in React Native. In order to make components react to a touch event, the component must be wrapped within any of the following components that has a touch event supported.

**Note:** Any of the Touchable components only support only child component. If you wish to have multiple components handle the same touch event, wrap them in a single `<View>` component as the child of the Touchable component.

#### Add a touch event with no visual feedback
If you need to handle a tap gesture but you don't want any feedback to be displayed, use `<TouchableWithoutFeedback>`
##### [TouchableWithoutFeedback](https://facebook.github.io/react-native/docs/touchablewithoutfeedback.html)
```js
import { TouchableWithoutFeedback, View } from 'react-native';

const MyComponent = () => {
  return (
    <TouchableWithoutFeedback>
      <View>
        ... // Any components placed within this View component will respond to the touch event
      </View>
    </TouchableWithoutFeedback>  
  );
};
```

<br>

#### Add a touch event which briefly lowers the opacity of its child components
Used to provide feedback by reducing the opacity of the button, allowing the background to be seen through while the user is pressing down
##### [TouchableOpacity](https://facebook.github.io/react-native/docs/touchableopacity.html)
```js
import { TouchableOpacity, View } from 'react-native';

const MyComponent = () => {
  return (
    <TouchableOpacity>
      <View>
        ... // Any components placed within this View component will respond to the touch event
      </View>
    </TouchableOpacity>  
  );
};
```

<br>

#### Add a touch event which briefly darkens the background of its child components
##### [TouchableHighlight](https://facebook.github.io/react-native/docs/touchablehighlight.html)
```js
import { TouchableHighlight, View } from 'react-native';

const MyComponent = () => {
  return (
    <TouchableHighlight>
      <View>
        ... // Any components placed within this View component will respond to the touch event
      </View>
    </TouchableHighlight>  
  );
};
```

<br>

#### Add a touch event which shows default Android touch animation
Only on Androidm, it will display ink surface reaction ripples that respond to the user's touch
##### [TouchableNativeFeedback](https://facebook.github.io/react-native/docs/touchablenativefeedback.html)
```js
import { TouchableNativeFeedback, View } from 'react-native';

const MyComponent = () => {
  return (
    <TouchableNativeFeedback>
      <View>
        ... // Any components placed within this View component will respond to the touch event
      </View>
    </TouchableNativeFeedback>  
  );
};
```
