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
##### [if statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
```js
if(varA & varB) {
  return true;
} else {
  return false;
}
```

##### [return statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return)
```js
if(varA & varB) {
  return true;
}

return false;
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

#### Define function context using various methods
##### Common code for examples
```js
var utility = {
  getContext: function() {
    // Console out the function context
    console.log("Function context: ", this);
    
    // Display the arguments passed to the function by converting the array-like arguments object to an array, looping through its contents and console-ing out each argument
    Array.from(arguments).forEach(function (item, index) {
      console.log("The argument in position " + index + " is " + item);
    });
  }
}

var otherObject = {};

function otherFunction() {
  // whatever
}
```

##### [call()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)
*Call the getContext() method from the `utility` object and pass it varying contexts and variables(optional)*
```js
// When `this` gets used within the function, it refers to: 

// The `window` object
utility.getContext.call(this, "aaa", "bbb");

// The `otherObject` object
utility.getContext.call(otherObject, "ccc", "ddd");

// The `otherFunction` function object
utility.getContext.call(otherFunction, "eee", "fff");
```

##### [apply()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)
*Call the getContext() method from the `utility` object and pass it varying contexts and variables(optional)*
```js
// When `this` gets used within the function, it refers to: 

// The `window` object
utility.getContext.apply(this, ["aaa", "bbb"]);

// The `otherObject` object
utility.getContext.apply(otherObject, ["ccc", "ddd"]);

// The `otherFunction` function object
utility.getContext.apply(otherFunction, ["eee", "fff"]);
```

##### [bind()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)
*Copy a reference to the method into a variable and set the context for it as specified*
```js
// When `this` gets used within the function, it refers to: 

// The `window` object
utility.getContext.bind(this, "ggg", "hhh")();

// The `otherObject` object
utility.getContext.bind(otherObject, "ccc", "ddd")();

// The `otherFunction` function object
utility.getContext.bind(otherFunction, "eee", "fff")();
```

###### Example of bind on a click event's function callback
```js
// When a click event is performed, the context is the element that was clicked by default
document.getElementById("clickBtn").addEventListener("click", function(){
    console.log(this);
    // Returns the #clickBtn element
});

// When the click event is bound to a different specified context, that context becomes the value for `this` within the click event's function callback
document.getElementById("clickBtn").addEventListener("click", function(){
    console.log(this);
    // Returns: window object
}.bind(window));
```
