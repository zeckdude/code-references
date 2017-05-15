## Numbers

#### Convert a string containing non-numeric characters to a integer number 
##### [parseInt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
```js
var str = "10px";
window.parseInt(str); // The argument must be a string that begins with numeric characters
// Returns:  10
```

<br>

#### Convert a string containing non-numeric characters to a float number 
##### [parseFloat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)
```js
var str = "10.5 miles";
window.parseFloat(str); // The argument must be a string that begins with numeric characters
// Returns:  10.5
```

<br>

#### Convert a string to a number
##### [Number()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number#Convert_numeric_strings_to_numbers)
```js
var str = "5";
Number(str);
// Returns: 5
```
