## Arrow Functions

#### Traditional function
```js
// Compare other arrow syntax examples to this
const addNumbers = function(number1, number2) {
  return number1 + number2;
};
```

<br>

#### Arrow Functions - when the function contents is only one line
##### [Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
```js
const addNumbers = (number1, number2) => number1 + number2;
```

<br>

#### Arrow Functions - when the function contents is more than one line
##### [Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
```js
const addNumbers = (number1, number2) => {
  return number1 + number2;
};
```

<br>

#### Arrow Functions - when there is only one argument
##### [Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
```js
const halfNumber = number1 => number1 / 2;
```

<br>

#### Arrow Functions - when there are no arguments
##### [Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
```js
const greet = () => {
  console.log('Hello');
};
```
