## Arrow Functions

#### Using Arrow Functions
##### [Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
*Convenient way of writing functions*
```js
// Traditional function
const addNumbers = function(number1, number2) {
  return number1 + number2;
};

// Shorthand arrow function (only when the function contents is only one line)
const addNumbers = (number1, number2) => number1 + number2;

// Shorthand arrow function (only when there is only one argument)
const halfNumber = number1 => number1 / 2;

// Regular arrow function (used when the function contents is more than one line)
const addNumbers = (number1, number2) => {
  return number1 + number2;
};

// Regular arrow function (used when there are no arguments)
const greet = () => {
  console.log('Hello');
};
```
