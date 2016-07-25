## Functions

<br>
#### Set default arguments for a function
##### [if statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
```js
function hello(name) {
  if(name === undefined) { name = "dude"; }
  return "What's up " + name;
}

hello("Jim");
// Returns: "What's up Jim"

hello();
// Returns: "What's up dude"
```

##### [OR operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators#Logical_OR)
```js
function hello(name) {
  return "What's up " + (name || "dude");
}

hello("Jim");
// Returns: "What's up Jim"

hello();
// Returns: "What's up dude"
```

<br>
#### Access unknown arguments added to a function call
##### [arguments](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
##### [Array.from()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from)
##### [Array.prototype.slice.call()](http://stackoverflow.com/a/7057017/83916)
```js
function doSomething() {
  // All arguments passed to a function are accessible using the `arguments` object
  arguments.length; // Returns: number of arguments
  arguments[2]; // Returns: 3rd argument

  // Since the `arguments` object is an array-like object, it must be converted to an array, to be able to perform array methods on it native array methods on it
  Array.from(arguments); // One way to convert it to an array
  Array.prototype.slice.call(arguments); // Another way to convert it to an array
  
  Array.from(arguments).forEach(function (item, index) {
    console.log("The argument in position " + index + " is " + item);
  });
}

doSomething(25, "blue", true, 62);
// Returns:
// The argument in position 0 is 25
// The argument in position 1 is blue
// The argument in position 2 is true
// The argument in position 3 is 62
```

##### [spread operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator)
```js
function doSomething(...passedArguments) {
  passedArguments.forEach(function (item, index) {
    console.log("The argument in position " + index + " is " + item);
  });
}

doSomething(25, "blue", true, 62);
// Returns:
// The argument in position 0 is 25
// The argument in position 1 is blue
// The argument in position 2 is true
// The argument in position 3 is 62
```

<br>
#### Access a part of all arguments passed to a function
##### [rest parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)
```js
// The rest parameter can be used as a wildcard placeholder. It's output will be placed inside an array.
function doSomething(a, b, ...c) {
  console.log(a);
  console.log(b);
  console.log(c);
}

doSomething(25, "blue", true, 62);
// Returns:
// 25
// blue
// [true, 62]
```

<br>
#### Pass array elements as arguments of a function call
##### [spread operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator)
```js
function doSomething(a, b, c) {
  console.log(a);
  console.log(b);
  console.log(c);
}

var arr = [25, "blue", true];
doSomething(...arr); // Equivalent to: doSomething(arr[0], arr[1], arr[2]);
// Returns:
// 25
// blue
// true
```

<br>
#### Cache function results by setting a property on the function
This is accomplished by using a practice known as *memoization* where past return values are saved as properties on the function, so that whenever the function is run, it will check if the cache to see if the function has already been run using the same arguments provided.
##### [memoization](https://www.sitepoint.com/implementing-memoization-in-javascript/)
```js
// Memoization when only one argument needs to be provided (Approach #1 - Using a function property)
function squareNum(n) {
  // Initialize the cache as an empty object if it doesn't already exist
  squareNum.cache = squareNum.cache || {};
  
  // Check to see if this value has already been saved in the cache
  if (!squareNum.cache[n]) {
    // If not then calculate the value and save it in the cache
    squareNum.cache[n] = n*n;
  }
  
  return squareNum.cache[n];
}

// Memoization when only one argument needs to be provided (Approach #2 - Using function closure)
var squareNum = (function() {
  var cache = {};
  
  function calculate(n) {
    var calculatedValue;
  
    if (n in cache) {
      calculatedValue = cache[n]
    } else {
      calculatedValue = n*n;
      cache[n] = calculatedValue;
    }
    
    return calculatedValue;
  }
  
  return calculate;
})();


// Memoization when multiple arguments are provided (Approach #1 - Using a function property)
function addition(a,b) {
  addition.cache = addition.cache || {};
  addition.cache[a] = addition.cache[a] || {};
  
  if (!addition.cache[a][b]) {
    addition.cache[a][b] = a+b;
  }
  
  return addition.cache[a][b];
}
```



