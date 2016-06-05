# JavaScript

[Logging and Debugging](logging-debugging.md)<br>
[Numbers](numbers.md)<br>
[Strings](strings.md)<br>
[Arrays](arrays.md)<br>
[Objects](objects.md)<br>
[DOM Manipulation](dom-manipulation.md)<br>
[Glossary](glossary.md)

### Common Scenarios

##### Short-hand Ways to check for a condition
*Using an if statement*
```
if(varA & varB) {
  return true;
} else {
  return false;
}
```

*Using the not-not operator* <br>
(http://www.sitepoint.com/javascript-double-negation-trick-trouble/)
```
return !!(varA & varB)
```

*Using the ternary operator* <br>
(http://www.sitepoint.com/shorthand-javascript-techniques/#1iftrueelseshorthand)
```
return (varA & varB) ? true : false;
```

<br>
##### Different Ways to check if a variable has a truthy value(not undefined, null, 0, NaN, "" or false) and return a value based on the result

*Using an if statement*
```
var message;
if(detailedMessage) {
  message = detailedMessage;
} else {
  message = genericMessage;
}
```

*Using a switch statement* <br>
(http://www.w3schools.com/js/js_switch.asp)
```
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

*Using the ternary operator* <br>
(http://www.sitepoint.com/shorthand-javascript-techniques/#1iftrueelseshorthand)
```
var message = detailedMessage ? detailedMessage : genericMessage;
```

*Using the logical OR operator* <br>
(https://addyosmani.com/blog/exploring-javascripts-logical-or-operator/)
```
var message = detailedMessage || genericMessage;
```

