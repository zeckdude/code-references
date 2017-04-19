## Functions

#### Specify the return type
##### [Functions](https://www.typescriptlang.org/docs/handbook/functions.html)
```js
function returnMyName(): string {
  // return 34; // results in an error as the function expects to return a string
  return 'Chris';
}

// Using a non-named anonymous function (with ES6 arrow function syntax)
let returnMyName: () => string = () => 'Chris';

function sayHello(): void {
  // return 'Wassup'; // results in an error as the function expects to return nothing
  alert('Chris');
}

// Using a non-named anonymous function (with ES6 arrow function syntax)
let sayHello: () => void = () => {
    alert('Chris')
};
```

<br>

#### Specify the argument type
##### [Functions](https://www.typescriptlang.org/docs/handbook/functions.html)
```js
function multiply(value1: number, value2: number) {
  return value1 * value2;
}

// console.log(multiply('seven', 3)); // results in an error as the function expects only numbers as its argument types
console.log(multiply(7, 3));
```

<br>

#### Specify both the argument and return type
##### [Functions](https://www.typescriptlang.org/docs/handbook/functions.html)
```js
function multiply(value1: number, value2: number): number {
  return value1 * value2;
}

// Using a non-named anonymous function (with ES6 arrow function syntax)
let multiply: (value1: number, value2: number) => number = (value1: number, value2: number) => value1 * value2;
```

<br>

#### Specify the exact type of makeup of a function that can be stored in a variable
##### [Functions](https://www.typescriptlang.org/docs/handbook/functions.html)
```js
function multiply(value1: number, value2: number) {
  return value1 * value2;
}
function sayHello(): void {
  alert('Chris');
}

let storedFunction: (val1: number, val2: number) => number;
// storedFunction = sayHello; // results in an error as the variable expects its value to be a function with two number arguments and a return type of a number. Note: the argument names (val1 and val2 in the example) don't matter.
storedFunction = multiply;
```
