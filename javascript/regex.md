## Regular Expressions

#### Resources for using regex in JS
| Name | Link |
|---------------|------------------------------|
| Nettuts - Using Regex in JavaScript | http://code.tutsplus.com/tutorials/you-dont-know-anything-about-regular-expressions-a-complete-guide--net-7869 |
| Sitepoint - Regular Expressions in JavaScript | https://www.sitepoint.com/expressions-javascript/ |
| Javscript.info - Regular expressions in JavaScript | http://javascript.info/tutorial/regular-expressions-javascript |

<br>
___
<br>

#### Create a regular expression using literal notation
##### [RegExp literal notation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
```js
var pattern = /\w+ing/;
```

<br>
___
<br>

#### Create a new instance of the `RegExp` object
##### [RegExp](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp)
```js
var pattern = new RegExp("\w+ing");
```

<br>
___
<br>

#### Determine if the specified string matches a pattern
##### [RegExp.test()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test)
```js
var str = "winning";
/\w+ing/.test(str);
// Returns: true
```

<br>
___
<br>

#### Find matches of a pattern on a string
##### [RegExp.exec()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec)
```js
var str = "winning";
/\w+ing/.exec(str);
// Returns: ["winning"]

var str = "winner";
/\w+ing/.exec(str);
// Returns: null
```

##### [String.match()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match)
```js
var str = "winning";
str.match(/\w+ing/);
// Returns: ["winning"]

var str = "winner";
str.match(/\w+ing/);
// Returns: null
```

<br>
___
<br>

#### Convert a string to an array based on a pattern
##### [String.split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
```js
var str = "Hello World    from JavaScript!";
str.split(/\s+/);
// Returns: ["Hello", "World", "from", "JavaScript!"]
```

<br>
___
<br>

#### Replace a part of a string (based on a pattern) with another string
##### [String.replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
```js
var str = "310-456-4468";
str.replace(/[- ]/g, "."); // Look for dashes or spaces and replace with periods
// Returns: "310.456.4468"
```

<br>
___
<br>

#### Return the index of the first occurrence of the specified substring within another string (based on a pattern)
##### [String.search()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/search)
```js
var str = 'Blue Whale';
str.search('Blue'); 
// Returns:  0

str.search('Blute'); 
// Returns: -1

str.search('Whale'); 
// Returns:  5
```
