## Quick Reference



#### Import JS scripts with `defer`
```js
<script src="assets/scripts/app.js" defer></script>
```
Notes:
- It is used when page elements are needed to run the script
- Downloads the JS file right away (while page is parsing) but only execute the scripts after everything on the page has finished parsing
- Another approach is to add the script tag at the end of the body. This causes the JS content to only begin downloading when the page is finished parsing. Therefore using the script tag in the head with `defer` is preferred.

<br>

#### Import JS scripts with `async`
```js
<script src="assets/scripts/vendor.js" async></script>
```
Notes:
- Is used when the script contents don't rely on page contents
- Downloads the JS file right away (while page is parsing) and executes when downloaded

<br>


#### Coercing a truthy/falsy value to a boolean
```js
// Using double bang operator
!!"" // false
!!0 // false
!!null // false
!!NaN // false
!!undefined // false

!!"hello" // true
!!1 // true
!!{} // true
!![] // true

// Using the `Boolean()` method
Boolean("") // false
Boolean(0) // false
Boolean(null) // false
Boolean(NaN) // false
Boolean(undefined) // false

Boolean("hello") // true
Boolean(1) // true
Boolean({}) // true
Boolean([]) // true

```

<br>


#### Use logical OR operator to assign a default value
```js
const name = firstName || 'User';
```
Notes:
- The first truthy value is used. If neither are truthy, then the expression evaluates to undefined.

<br>


#### Use logical AND operator to check if a condition is true and if so, return a second value
```js
const name = isLoggedIn && 'Max';
```
Notes:
- If the first value is not truthy, then the expression evaluates to false;

<br>

#### Loops
```js
// Iterate n times
for (let i = 0; i < 3; i++) {
  // Do something 3 times
}

for (let i = 0; i < array.length; i++) {
 // Do something for every item in the array
}

// Iterate over the items in an array
for (const arrayItem of array) {
 // Do something for every item in the array
}

array.forEach(arrayItem => {
  // Do something for every item in the array
});

// Iterate over keys in object
for (const key in object) {
 // Access property values with `object[key]`
}

Object.keys(object).forEach(key => {
  // Do something with the key
});

Object.values(object).forEach(value => {
  // Do something with the value
});

Object.entries(object).forEach(([key, value]) => {
  // Do something with the key & value
});
```

<br>

#### Memory Heap
Where data is stored in system memory that it needs to access

<br>

#### Call Stack
A list of functions that have been called and need to be executed. Once they are executed, they are automatically removed from the call stack.

<br>

#### Memory Heap
Where data is stored in system memory that it needs to access

<br>

#### Primitive values
Values that are stored in memory and the variable holds the value itself. Therefore if a variable with a primitive value is assigned to another variable, the new variable makes a copy of the primitive value and stores it new.
- String
- Number
- Boolean
- null
- undefined
- Symbol

<br>

#### Reference values
Values that are stored in memory and the variable references the location in memory. Therefore if a variable with a reference value is assigned to another variable, the new variable references the same place in memory and any changes to either of the variables is reflected in both.
- Object
- Array
- Function

<br>

#### Function declaration
```js
function sayHello() {
  // Do something
}
```
Notes:
- Gets hoisted to the top of the file where it is initialized and declared, which means you can call it from anywhere in the file
- When used as the value of an object property or event listener, having the function name makes debugging easier because the function name will appear in the callstack (instead of showing as anonymous)
  ```js
  const person = {
    greet: function greet() {
      // Greet someone
    }
  };
  ```
<br>



#### Function expression
```js
const sayHello = function() {
  // Do something
}
```
Notes:
- Gets hoisted to the top of the file but as undefined. Therefore it can't be used until after it is declared.

<br>


#### Rest Parameters
```js
const getSum = (...numbers) => {
  return numbers.reduce((sum, number) => sum += number, 0);
}
```
Notes:
- Turns all arguments (that haven't already been destructured) into an array of values
- Useful when the number of arguments is unknown

<br>


#### Spread Operators
```js
// To create a new array using values from another array
const numbers1 = [1, 2, 3];
const numbers2 = [...numbers1, 4, 5, 6];

// To call a function that requires separate arguments using the array values
const numbers = [1, 2, 3]
getSum(...numbers);

// To create an object using key/value pairs from another object
const sedan = {
  doors: 4,
}
const passat = {
  ...sedan,
  manufacturer: 'Volkswagen',
}
```
Notes:
- Turns an array of values into separate values

<br>



