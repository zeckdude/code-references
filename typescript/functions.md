## Functions

#### Specify the return type
##### [Functions](https://www.typescriptlang.org/docs/handbook/functions.html)
```js
function returnMyName(): string {
  // return 34; // results in an error as the function expects to return a string
  return 'Chris';
}

function sayHello(): void {
  // return 'Wassup'; // results in an error as the function expects to return nothing
  alert('Chris');
}
```

#### Specify the argument type
##### [Functions](https://www.typescriptlang.org/docs/handbook/functions.html)
```js
function multiply(value1: number, value2: number) {
  return value1 * value2;
}
// console.log(multiply('seven', 3)); // results in an error as the function expects only numbers as its argument types
console.log(multiply(7, 3));
```
