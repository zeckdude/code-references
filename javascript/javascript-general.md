## JavaScript - General

[Logging and Debugging](logging-debugging.md)<br>
[Numbers](numbers.md)<br>
[Strings](strings.md)<br>
[Arrays](arrays.md)<br>
[Objects](objects.md)<br>
[DOM](dom.md)<br>
[Glossary](glossary.md)

### Common Scenarios

#### Short-hand Ways to check for a condition
##### [IF statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
```js
if(varA & varB) {
  return true;
} else {
  return false;
}
```

##### [not-not operator](http://www.sitepoint.com/javascript-double-negation-trick-trouble/)
```js
return !!(varA & varB)
```

##### [ternary operator](http://www.sitepoint.com/shorthand-javascript-techniques/#1iftrueelseshorthand)
```js
return (varA & varB) ? true : false;
```

<br>
#### Different Ways to check if a variable has a truthy value(not undefined, null, 0, NaN, "" or false) and return a value based on the result
##### [IF statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
```js
var message;
if(detailedMessage) {
  message = detailedMessage;
} else {
  message = genericMessage;
}
```

##### [switch()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)
```js
var message;
switch(detailedMessage) {
  case true:
    message = detailedMessage;
    break;
  case false:
    message = genericMessage;
    break;
}
```

##### [ternary operator](http://www.sitepoint.com/shorthand-javascript-techniques/#1iftrueelseshorthand)
```js
var message = detailedMessage ? detailedMessage : genericMessage;
```

##### [OR operator](https://addyosmani.com/blog/exploring-javascripts-logical-or-operator/)
```js
var message = detailedMessage || genericMessage;
```

<br>
#### Different Ways call different functions based on a condition
##### [IF statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
```js
if(age > 18) {
  drinkUp();
} else {
  goHome();
}
```

##### [ternary operator](http://www.sitepoint.com/shorthand-javascript-techniques/#1iftrueelseshorthand)
```js
(age >= 21 ? drinkUp : goHome)();
// OR
age >= 21 ? drinkUp() : goHome();
```


<br>
#### Defining function context using various methods
##### [call()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)
```js

```

##### [apply()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)
```js

```
