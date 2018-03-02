## Styling

Styling is a bit different in React Native than in React. It involves using the Stylesheet API and supplying it an object with rules that are passed to the component for which they should be applied.

#### Style a component using the [`Stylesheet`](https://facebook.github.io/react-native/docs/stylesheet.html) API
```js
const MyComponent = (props) => {
  return (
    <View style={styles.container}>
      <Text>Enter Something</Text>
      <TextInput
        style={{width: 300}}
      />
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    paddingTop: 50,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'flex-start',
  },
});
```

**Note:** You could still define styles using a regular object as in React, but [it is less performant and has other downsides](https://stackoverflow.com/questions/39907915/is-there-a-need-to-use-stylesheet-create).

For a cheatsheet on available options for common React Native components, see the [React Native Styling Cheat Sheet](https://github.com/vhpoet/react-native-styling-cheat-sheet/blob/master/README.md) 
