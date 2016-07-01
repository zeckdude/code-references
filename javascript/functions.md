## Functions

#### Access unknown arguments added to a function call
##### [arguments](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
##### [Array.from()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from)
##### [Array.prototype.slice.call()](http://stackoverflow.com/a/7057017/83916)
```js
function doSomething() {
  // All arguments passed to a function are accessible using the `arguments` object
  arguments.length; // Returns: number of arguments
  arguments[2]; // Returns: 3rd argument

  // Since the `arguments` object is an array-like object, it must be converted to an array, to be able to perform array methods on it native array methods on it
  Array.from(arguments); // One way to convert it to an array
  Array.prototype.slice.call(arguments); // Another way to convert it to an array
  
  Array.from(arguments).forEach(function (item, index) {
    console.log("The argument in position " + index + " is " + item);
  });
}

doSomething(25, "blue", true, 62);
// Returns:
// The argument in position 0 is 25
// The argument in position 1 is blue
// The argument in position 2 is true
// The argument in position 3 is 62
```
