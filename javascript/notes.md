### JavaScript Theory

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

#### Testing
##### Good tests exhibit three important charisteristics:

1. *Repeatability* - Test results should be highly reproducible. They should always produce the exact same results.
2. *Simplicity* - Tests should strive to remove as much HTML markup, CSS, or JavaScript as possible without interrupting the intent of the test case.
3. *Independence* - Avoid making the results from one test dependant upon another.

<br>

##### The assertion
The most important part of a unit-testing framework is its assertion method, usually named `assert()`, which takes a value - an expression whose premise is *asserted* (checked if it is `true`) - and a description that describes the purpose of the assertion. If the value evaluates to `true`, the assertion passes; otherwise it's considered a failure. The associated message is usually logged with an appropriate pass/fail indicator.
<br>
##### Example `assert()` function
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

#### Functions as first-class objects
The capabilities listed below are common to all objects in JavaScript and functions are no exception. Any object that shares these is known as a *first-class object*.

1. Can be created via literals.
2. Can be assigned to variables, array entries, and properties of other objects.
3. Can be passed as arguments to functions.
4. Can be returned as function results
5. Can possess properties that can be dynamically created and assigned.

#### Declaring Functions
1. Declaring a function at the top-level makes it a method of the global (`window`) object.
2. Declaring a function within an object makes it a method of the object within which it was declared.
3. Declaring a function within a constructor makes it a method of the object that is invoked when calling the `new` keyword with the constructor function name, i.e. `var toyota = new Car()`.
