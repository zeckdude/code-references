### Strings

##### Get the specified character from a string
##### [charAt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt)
```js
var str = "hello";
str.charAt(4);
// Returns: "o"
```

##### [Treat the string as an array-like object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Character_access)
```js
var str = "hello";
str[4];
// Returns: "o"
```
<br>
##### Combine the text of two or more strings and return a new string
##### [concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat)
```js
var hello = 'Hello, ';
var greeting = hello.concat('Kevin', ' have a nice day.');
// Returns: "Hello, Kevin have a nice day."
```

##### [Using the addition operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript#Operators)
```js
var hello = 'Hello, ';
var greeting = hello + 'Kevin' + ' have a nice day.';
// Returns: "Hello, Kevin have a nice day."
```

<br>
##### Determines whether a string ends with the characters of another string
##### [endsWith() - ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith)
```js
var str = 'To be, or not to be, that is the question.';
str.endsWith('question.');
// Returns: true
```





