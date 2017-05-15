## JavaScript Theory

#### Collecting performance information
Using [`Date().getTime()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime):
```js
var maxCount = 100000;
var start = new Date().getTime();
for (var n = 0; n < maxCount; n++) {
  /* perform operation to be measured */
}
var elapsed = new Date().getTime() - start;
console.log("Measured Time:", elapsed + " milliseconds");
```

<br>

Using [`performance.now()`](https://developer.mozilla.org/en-US/docs/Web/API/Performance/now) (more accurate count):
```js
var maxCount = 100000;
var start = performance.now();
for (var n = 0; n < maxCount; n++) {
  /* perform operation to be measured */
}
var elapsed = (performance.now() - start).toFixed(4);
console.log("Measured Time:", elapsed + " milliseconds");
```

<br>

Using [`console.time()`](https://blog.mariusschulz.com/2013/11/22/measuring-execution-times-in-javascript-with-consoletime):
```js
var maxCount = 100000;
console.time("Measured Time");
for (var n = 0; n < maxCount; n++) {
  /* perform operation to be measured */
}
console.timeEnd("Measured Time");
```

<br>

#### Testing
##### Good tests exhibit three important charisteristics:

1. *Repeatability* - Test results should be highly reproducible. They should always produce the exact same results.
2. *Simplicity* - Tests should strive to remove as much HTML markup, CSS, or JavaScript as possible without interrupting the intent of the test case.
3. *Independence* - Avoid making the results from one test dependant upon another.

<br>

##### The assertion
The most important part of a unit-testing framework is its assertion method, usually named `assert()`, which takes a value - an expression whose premise is *asserted* (checked if it is `true`) - and a description that describes the purpose of the assertion. If the value evaluates to `true`, the assertion passes; otherwise it's considered a failure. The associated message is usually logged with an appropriate pass/fail indicator.

<br>

##### Example `assert()` function - Results displayed in browser
**JS:**
```js
function assert(value, desc) {
  // Create new "li" DOM object and save it in a variable
  var li = document.createElement("li");
  
  // Assign a specific class to the "li" object depending if the test evaluates truthy or falsy
  li.className = value ? "pass" : "fail";
  
  // Add the content for the "li" object
  li.appendChild(document.createTextNode(desc));
  
  // Find the #results list and append the new "li" object to it
  document.getElementById("results").appendChild(li)
}

window.onload = function(){
  assert(true, "The test passed");
  assert(false, "The test failed");
};
```

**CSS:**
```css
#results li.pass { color: green; }
#results li.fail { color: red; }
```

**HTML:**
```html
<ul id="results"></ul>
```

<br>

##### Example `assert()` functions - Results displayed in console

```js
function assert(val, desc) {
  return val ? console.log(desc) : console.log(false);
}
```

```js
function assert(value, description) {
  var result = value ? "pass" : "fail";
  console.log(result + ' - ' +  description); 
};
```

<br>

#### Functions
##### Functions as first-class objects
The capabilities listed below are common to all objects in JavaScript and functions are no exception. Any object that shares these is known as a *first-class object*.

1. Can be created via literals.
2. Can be assigned to variables, array entries, and properties of other objects.
3. Can be passed as arguments to functions.
4. Can be returned as function results
5. Can possess properties that can be dynamically created and assigned.

<br>

##### Declaring Functions
Some things to keep in mind when declaring functions:

1. Declaring a function at the top-level makes it a method of the global (`window`) object.
2. Declaring a function within an object makes it a method of the object within which it was declared.
3. Declaring a function within a constructor makes it a method of the object that is invoked when calling the `new` keyword with the constructor function name, i.e. `var toyota = new Car()`.
4. All functions have a property named `name` that stores the function's name as a string. Functions with no name possess this property as an empty string.
5. Functions can either be declared as a named function, i.e. `function isOpen() {}`, or as an anonymous function, i.e. `var isRunning = function() {}`

```js
// Named function created on the window object (top-level)
function firstFunction() { return true; }

// The name property is the name of the function
console.log(firstFunction.name); // "firstFunction"


// Anonymous function that is assigned to a variable
var secondFunction = function() { return true; }

// Since it is an anonymous function, the name property is an empty string
console.log(secondFunction.name); // ""

// Named function assigned to a window property
window.thirdFunction = function fourthFunction() { return true; }

// The name comes from the function literal and not from the name of the variable to which it is assigned
console.log(thirdFunction.name); // "fourthFunction"
```

<br>

##### Scope within a function
Some things to keep in mind when declaring variables and functions within a function:

1. Variables within a function are accessible (in scope) from their point of declaration until the end of the function
2. Inner named functions are accessible (in scope) anywhere within the enclosing function. This is known as *hoisting*.
  * Function hoisting only applies to function declarations (named functions), i.e. `function startCar() {...}` and not for function expressions, i.e. `var startCar = function(){...}`. For a detailed explanation, visit: http://adripofjavascript.com/blog/drips/variable-and-function-hoisting
  
<br>

In order to avoid clashing with other variables in the global scope that are defined elsewhere, wrap all code in an anonymous self-executing function, a.k.a. an [immediately invoked function expression (IIFE)](https://www.kirupa.com/html5/immediately_invoked_function_expressions_iife.htm). This will keep all variables declared within it in the function's scope as opposed to the global scope. <br><br>
Use [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) (`"use strict;"`) to make the code more secure by throwing errors when the following conditions exist:

1. Using a variable, without declaring it (which would normally create a global variable)
2. Deleting a variable
3. Using duplicate parameter names
4. Writing to a read-only property
5. Deleting an undeletable property
6. Using the string "arguments" as a variable name

```js
(function() {
  "use strict";
  // Put code here
})();
```

<br>

##### Native function parameters
There are a few native function parameters which are useful:

1. `arguments` - A collection of all passed arguments to the function
  * Since this is an *array-like* object, it is accessible using bracket notation, e.g. `arguments[2]`, and has an `arguments.length` property, but lacks other methods accessible to actual arrays. 
  * To convert it to an array, use: `Array.from(arguments)` or `Array.prototype.call(arguments)`
2. `this` - The reference to the object upon which the function is invoked, a.k.a. the *function context*

<br>

##### Creating a constructor
A constructor function makes it much easier to create multiple objects that conform to the same pattern. Follow these guidelines when creating a constructor function:

1. The constructor function is named as a noun and describes the object that gets created when the constructor is invoked. it should begin with an uppercase character, i.e. `Car()`
2. Methods within the constructor function start with a verb that describes what they do and are camelCase, i.e. `accelerate()` or `openDoor()`

##### Example of a constructor function
```js
function Car() {
  this.accelerate = function() { console.log("Driving faster"); };
  this.openDoor = function() { console.log("Opening door"); };
}

var passat = new Car();
```

<br>

##### Invoking Functions
There are several different ways to invoke a function. Depending on which way the function is invoked, the *function context* is determined.

1. As a top-level function.
  * The context is the global object since all top-level functions are actually methods of the global object (`window`).
  
    ```js
    function firstFunction() { return this; }
    
    // Since the function is at top-level, it is a method of the window object, so therefore the function context is the window object
    console.log(firstFunction() === window); // true
    ```
      
2. As a method of an object
  * The context is the object owning the method
  
    ```js
    var firstObject = {
      secondFunction: function() { return this; }
    };
    
    // Since the method belongs to the firstObject object, the function context is firstObject
    console.log(firstObject.secondFunction() === firstObject); // true
    ```
    
3. As a method of a constructor
  * The context is the newly created object instance, made via the constructor function.
  
    ```js
    function Constructor() {
      this.thirdFunction = function() { return this; };
    }
    var instance = new Constructor();

    // Since the method is created using a constructor, function context is the object instance that was created
    console.log(instance.thirdFunction() === instance); // true
    ```
    
4. Via `apply()` or `call()`
  * The context is whatever object we supply to the `apply()` or `call()` methods as the first argument.
  * When using `apply()`, the second argument is an array with values to pass to the invoked function.
  * When using `call()`, all arguments after the first one are values to pass to the invoked function.
  
    ```js
    // Simple function to add all scores together
    function updateScore() {
      for (var i = 0; i < arguments.length; i++) {
        this.score += arguments[i];
      }
      return this.score;
    }
    
    // Simple object that will serve as the context for the `apply()` and `call()` function invokations
    var game = {
      name: "Soccer",
      score: 0
    }
    
    // Using `apply()`
    updateScore.apply(game, [1, 2, 3, 4]);
    
    // Using `call()`
    updateScore.call(game, 1, 2, 3, 4);
    
    console.log(game.score); // Returns: 10
    ```
    
<br>

##### Binding Functions
When you bind a function, you are copying a reference to a method and setting a new context. NOTE: `bind()` returns a function, and not the result of the method having been run. 

```js
function doubleScore() {
  this.score *= 2;
}

function Game() {
  this.score = 1;
  this.double = doubleScore.bind(this); // A copy to the method referenced by `doubleScore()`, but specifying the instance of the constructor as the context
  this.printScore = function() {
    console.log(this.score);
  }
}

var game = new Game();
game.score = 3;
game.printScore(); // Consoles out: 3
game.double();
game.printScore(); // Consoles out: 6

```

<br>

##### Closure
###### [Detailed Explanation](https://www.kirupa.com/html5/closures_in_javascript.htm)
Closure is a newly created function (which was returned from another function) that also contains its variable context. In other words, it is when a function returns an inner function, which still retains a reference to variables that are defined within its outer function that it relies on.<br>

<br>

![Closure - Gray Area] (https://github.com/zeckdude/code-references/blob/master/img/javascript/gray_area_kirupa.png)<br>
*Closure is the area where functions and variable scope intersect (Source: Kirupa.com)*<br>

<br>

![Closure explained in an image] (https://github.com/zeckdude/code-references/blob/master/img/javascript/definition_closure_kirupa.png)<br>
*Good representation of closure (Source: Kirupa.com)*

<br>

Example #1:<br>
```js
// Function to convert a temperature to another
function convertTemp(fromTempName, toTempName) {
  // Common numbers needed to perform conversion calculations 
  // Notice they are outside of the function being returned, yet they are still accessible by the inner function that gets returned when called from outside of this function, due to closure
  var a = 1.8;
  var b = 32;
  
  // Return the inner function
  return function(fromTemp){
    if (fromTempName === 'celsius' && toTempName === 'fahrenheit') {
      return fromTemp * a + b;
    }
    
    if (fromTempName === 'fahrenheit' && toTempName === 'celsius') {
      return (fromTemp - b) / a;
    }
  }
}

celsiusToFahrenheit = convertTemp('celsius', 'fahrenheit');
fahrenheitToCelsius = convertTemp('fahrenheit', 'celsius');

celsiusToFahrenheit(30); 
// Returns 86;

fahrenheitToCelsius(86); 
// Returns 30;
```

<br>

Example #2:<br>
```js
// Function to iterate a count every time the inner function is called from outside of this function
function counter(start){
  i = start;
  return function() {
   // Due to closure, each time the variable `count` (which has a reference to this inner function) is called, it is able to access the value of i from the last time the function was called and then iterate it.
   return i++;
  }
}

// Start a counter at 1
var count = counter(1);

count();
// Returns: 1

count();
// Returns: 2
```

