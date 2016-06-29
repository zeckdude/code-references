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

In order to avoid clashing with other variables in the global scope that are defined elsewhere, wrap all code in an anonymous self-executing function. This will keep all variables declared within it in the function's scope as opposed to the global scope.

```js
(function() {
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
2. As a method of an object
  * The context is the object owning the method
3. As a method of a constructor
  * The context is the newly created object instance, made via the constructor function.
4. Via `apply()` or `call()`
  * The context is whatever object we supply to the `apply()` or `call()` methods as the first argument.

```js
// Named function created on the window object (top-level)
function firstFunction() { return this; }

// Since the function is that the top-level, it is a method of the window object, so therefore the function context is the window object
console.log(firstFunction() === window); // true


// Object method 
var firstObject = {
  secondFunction: function() { return this; }
};

// Since the method belongs to the firstObject object, the function context is firstObject
console.log(firstObject.secondFunction() === firstObject); // true


// Method on a constructor
function Constructor() {
  this.thirdFunction = function() { return this; };
}
var instance = new Constructor();

// Since the method is created using a constructor, function context is the object instance that was created
console.log(instance.thirdFunction() === instance); // true


// Defining the context using apply() or call()
// Example here
```
