## Spread Operator

#### Pass elements of an array as arguments to a function
##### [Spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator)
```js
function addNumbers(a, b, c) {
  return a + b + c;
}
let numbers = [1, 10, 99];
addNumbers(...numbers);
// Returns: 110
```

<br> 

#### Add the elements of an existing array into a new array
##### [Spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator)
```js
let numbers = [1, 10, 99];
let moreNumbers = [...numbers, -30, 44];
console.log(moreNumbers);
// Outputs: [1, 10, 99, -30, 44]
```

<br> 

#### Combine two arrays
##### [Spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator)
```js
let numbers = [1, 10, 99];
let anotherNumberList = [68, 3, 72, 9];
let evenMoreNumbers = [...numbers, ...anotherNumberList]; // Same as numbers.concat(anotherNumberList)
console.log(evenMoreNumbers);
// Outputs: [1, 10, 99, 68, 3, 72, 9]
```

<br> 

#### Copy an array
##### [Spread syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator)
```js
let numbers = [1, 2, 3];
let numbers2 = [...numbers]; // Same as numbers.slice() which copies an array instead of referencing the previous array
// Contains: [1, 2, 3] // Separate new array
```
