## Strings

#### Return the number of characters in a specified string
##### [length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
```js
var str = 'Blue Whale';
str.length; 
// Returns:  10
```

<br>
#### Get the specified character from a string
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
#### Combine the text of two or more strings and return a new string
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
#### Determine whether a string ends with the characters of another string
##### [endsWith() - ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith)
```js
var str = 'To be, or not to be, that is the question.';
str.endsWith('question.');
// Returns: true
```

<br>
#### Determine whether one string may be found within another string
##### [includes() - ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes)
```js
var str = 'To be, or not to be, that is the question.';
str.includes('To be');
// Returns: true
```

<br>
#### Return the index of the first occurrence of the specified substring within another string
##### [indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexof)
```js
var str = 'Blue Whale';
str.indexOf('Blue'); 
// Returns:  0

str.indexOf('Blute'); 
// Returns: -1

str.indexOf('Whale'); 
// Returns:  5
```

<br>
#### Return the index of the last occurrence of the specified substring within another string
##### [lastIndexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastindexof)
```js
var str = 'Blue Whale';
str.lastIndexOf('l'); 
// Returns:  8
```

<br>
#### Return a substring of another string
##### [substring()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring)
```js
var str = "There are four words";
str.substring(10, 14);
// Returns: "four"
```

##### [slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice)
```js
var str = "There are four words";
str.slice(10, 14);
// Returns: "four"
```

##### [substr()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr)
```js
var str = "There are four words";
str.substr(10, 4);
// Returns: "four"
```

<br>
#### Convert a string to uppercase
##### [toUpperCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase)
```js
var str = "George Wallace";
str.toUpperCase();
// Returns: "GEORGE WALLACE"
```

<br>
#### Convert a string to lowercase
##### [toLowerCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)
```js
var str = "George Wallace";
str.toLowerCase();
// Returns: "george wallace"
```

<br>
#### Replace a part of a string with another string 
##### [replace() - Basic](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
```js
var str = "Martin Jeffrey King";
str.replace("Jeffrey", "Luther");
// Returns: "Martin Luther King"
```

##### [replace() - Using a regular expression to match a pattern and function to alter the string string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
```js
var str = "310-456-4468";
str.replace(/[- ]/g, "."); // Look for dashes or spaces and replace with periods
// Returns: "310.456.4468"
```

```js
var str = "Jeff Jeromy Jackson";
str.replace(/(\w+) (\w+) (\w+)/g, function(match, firstName, middleName, lastName) { // Look for three words separated by spaces between the words and capture each of the words to use in the function.
  return firstName + " Jebediah " + lastName;
});
// Returns: "Jeff Jebediah Jackson"
```

