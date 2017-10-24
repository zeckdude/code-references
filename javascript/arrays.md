## Arrays

#### Quick Reference Notes

| Property | Purpose | Notes |
|---------------|----------------------------------------|----------------------------------------------------------|
| [forEach()](https://github.com/zeckdude/code-references/blob/master/javascript/arrays.md#foreach) | Iterate over an array | *None* |
| [map()](https://github.com/zeckdude/code-references/blob/master/javascript/arrays.md#map---video) | Iterate over an array while performing a function on each value | Returns ALL altered array values as a new array |
| [reduce()](https://github.com/zeckdude/code-references/blob/master/javascript/arrays.md#reduce---video) | Iterate over an array while combining each result to return a single value | Useful for operations like adding together all values in an array |
| [filter()](https://github.com/zeckdude/code-references/blob/master/javascript/arrays.md#filter---video) | Iterate over an array while checking if each value passes a specified condition | Returns ONLY the values that meet the condition as a new array |
| [every()](https://github.com/zeckdude/code-references/blob/master/javascript/arrays.md#every) | Test if all elements in an array match a condition | *None* |
| [find() - ES6](https://github.com/zeckdude/code-references/blob/master/javascript/arrays.md#find) | Return the first element in an array that matches a condition | *None* |
| [findIndex() - ES6](https://github.com/zeckdude/code-references/blob/master/javascript/arrays.md#findindex) | Return the index of the first element that matches a specified value (or condition) in an Array | *None* |
| [some() - ES6](https://github.com/zeckdude/code-references/blob/master/javascript/arrays.md#some-1) | Determine if any element in an array matches a condition | *None* |
| [includes() - ES6](https://github.com/zeckdude/code-references/blob/master/javascript/arrays.md#includes---es6) |Determine whether a value is in an array | *None* |



#### Return the number of elements in an array
##### [length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length)
```js
var arr = [2, "George Rose", true];
arr.length; 
// Returns:  3
```

<br>

#### Detect an array 
*(http://www.shamasis.net/2011/08/infinite-ways-to-detect-array-in-javascript/)*

##### [isArray()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray)
```js
var arr = [1,2,3];
Array.isArray(arr);
// Returns: true
```

##### [constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/constructor)
```js
var arr = [1,2,3];
arr.constructor === Array;
// Returns: true
```

##### [instanceof operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof)
```js
var arr = [1,2,3];
arr instanceof Array;
// Returns: true
```

##### [toString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toString)
```js
var arr = [1,2,3];
Object.prototype.toString.call(arr) == "[object Array]";
// Returns: true
```

<br>

#### Loop through values of an array
##### [foreach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
```js
var arr = [2, "George Rose", true];
arr.forEach(function (item, index) {
  console.log("The element in position " + index + " is " + item);
});
// Displays in the console (only first loop iteration shown):  "The element in position 0 is 2"
```

##### [for()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
```js
var arr = [2, "George Rose", true];
for(var index = 0; index < arr.length; index++) {
  console.log("The element in position " + index + " is " + arr[index]);
}
// Displays in the console (only first loop iteration shown):  "The element in position 0 is 2"
```

<br>

#### Return the index of the first element that matches a specified value (or condition) in an Array
##### [indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
```js
var arr = [3, 7, 2, 7];
arr.indexOf(7);
// Returns:  1

arr.indexOf("George"); 
// Returns:  -1
```

##### [findIndex()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)
```js
var arr = [3, 7, 2, 7];

arr.findIndex(function(element){
  return element === 7;
}); 
// Returns: 1

arr.findIndex(function(element){
  return element === "George";
}); 
// Returns: -1
```

<br>

#### Add one or more elements to the beginning of an array
##### [unshift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)
```js
var arr = [2, "George Rose", true];
arr.unshift(42, "Harley Quinn");
// Returns (the new number of elements in the array):  5
// Contains: [42, "Harley Quinn", 2, "George Rose", true]
```

<br>

#### Add one or more elements at a specified position of an array
##### [splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
```js
var arr = [2, "George Rose", true];
arr.splice(2, 0, "Taylor", "Harley");
// Returns (the elements that were removed - Empty array since we only added elements):  []
// Contains: [2, "George Rose", "Taylor", "Harley", true]
```

<br>

#### Add one or more elements to the end of an array
##### [push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
```js
var arr = [2, "George Rose", true];
arr.push(42, "Harley Quinn");
// Returns (the new number of elements in the array):  5
// Contains: [2, "George Rose", true, 42, "Harley Quinn"]
```

<br>

#### Remove the first element of an array
##### [shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)
```js
var arr = ["Jim", "George", "Bob"];
arr.shift();
// Returns (the element that was removed): "Jim"
// Contains: ["George", "Bob"]
```

<br>

#### Remove one or more elements at a specified position of an array
##### [splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
```js
var arr = [2, "George Rose", true, "Jet"];
arr.splice(1, 2);
// Returns (the elements that were removed): ["George Rose", true]
// Contains: [2, "Jet"]
```

<br>

#### Remove the last element of an array
##### [pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)
```js
var arr = ["Jim", "George", "Bob"];
arr.pop();
// Returns (the element that was removed): "Bob"
// Contains: ["Jim", "George"]
```

<br>

#### Extract a specified number of elements from the end of an array
##### [slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
```js
var arr = ["Jim", "George", "Bob"];
arr.slice(-2);
// Returns (the elements that were extracted): ["George", "Bob"]
// Contains (Original array remains untouched): ["Jim", "George", "Bob"]

var arr = ["Jim", "David", "Jeff", "Mike"];
arr.slice(1,-1);
// Returns (the elements that were extracted): ["David", "Jeff"]
// Contains (Original array remains untouched): ["Jim", "David", "Jeff", "Mike"]
```

<br>

#### Convert an array to a string separated by a specified character(s)
##### [join()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
```js
var arr = ["Jim", "George", "Bob"];
arr.join(", ");
// Returns: "Jim, George, Bob"
```

<br>

#### Reverse the order of the elements in an array
##### [reverse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)
```js
var arr = ["Jim", "George", "Bob"];
arr.reverse();
// Returns: ["Bob", "George", "Jim"]
```

<br>

#### Sort the elements of an array alphabetically
##### [sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
```js
var arr = ["Jim", "George", "Bob"];

// Ascending Order
arr.sort();
// Returns: ["Bob", "George", "Jim"]

// Descending Order
arr.sort().reverse();
// Returns: ["Jim", "George", "Bob"]
```

<br>

#### Sort the elements of an array numerically
##### [sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
```js
var arr = [1, 64, 22, 138];

// Ascending Order
arr.sort(function(a, b){return a-b});
// Returns: [1, 22, 64, 138]

// Descending Order
arr.sort(function(a, b){return b-a});
// Returns: [138, 64, 22, 1]
```

<br>

#### Determine whether a value is in an array
##### [includes() - ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)
```js
var arr = ["Jim", "George", "Bob"];
arr.includes("George");
// Returns: true
```

##### [indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
```js
var arr = ["Jim", "George", "Bob"];
arr.indexOf("George") >= 0;
// Returns: true
```

##### [some()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)
```js
var arr = ["Jim", "George", "Bob"];
arr.some(function(name){
  return name === "George";
}); 
// Returns: true
```

<br>

#### Extract a part of an array into its own array
##### [slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
```js
var arr = [2, "George Rose", true, 55];
arr.slice(1,3);
// Returns (the elements that were extracted): ["George Rose", true]
// Contains (Original array remains untouched): [2, "George Rose", true, 55]

var arr = [2, "George Rose", true, 55];
arr.slice(-3);
// Returns (the elements that were extracted): ["George Rose", true, 55]
// Contains (Original array remains untouched): [2, "George Rose", true, 55]
```

<br>

#### Filter a set of elements out of an array and into its own array
##### [filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) - [video](https://www.youtube.com/watch?v=BMUiFMZr7vk)
```js
var people = [
  { name: "George", age: 32 },
  { name: "Lindsay", age: 24 },
  { name: "Mike", age: 15 },
];

var adults = people.filter(function(people){
  return people.age >= 18;
});
// Returns: [{ name: "George", age: 32 }, { name: "Lindsay", age: 24 }]
```

##### [for()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
```js
var people = [
  { name: "George", age: 32 },
  { name: "Lindsay", age: 24 },
  { name: "Mike", age: 15 },
];

var adults = [];
for (var i = 0; i < people.length; i++) {
  if (people[i].age > 18) {
    adults.push(people[i]);
  }
}
// Returns: [{ name: "George", age: 32 }, { name: "Lindsay", age: 24 }]
```

##### [foreach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
```js
var people = [
  { name: "George", age: 32 },
  { name: "Lindsay", age: 24 },
  { name: "Mike", age: 15 },
];

var adults = [];
people.forEach(function (person) {
  if (person.age > 18) {
    adults.push(person);
  }
});
// Returns: [{ name: "George", age: 32 }, { name: "Lindsay", age: 24 }]
```

<br>

#### Transform array elements and save them into a new array
##### [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) - [video](https://www.youtube.com/watch?v=bCqtb-Z5YGQ)
```js
var people = [
  { name: "George", age: 32 },
  { name: "Lindsay", age: 24 },
  { name: "Mike", age: 15 },
];

var adultCheck = people.map(function(person){
  var continuation = (person.age >= 18) ? "of age" : "under-age";
  return person.name + " is " + continuation;
});
// Returns: ["George is of age", "Lindsay is of age", "Mike is under-age"]
```

##### [map() using arrow functions - ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
```js
var people = [
  { name: "George", age: 32 },
  { name: "Lindsay", age: 24 },
  { name: "Mike", age: 15 },
];

var personAges = people.map((person) => person.age);
// Equivalent to:
var personAges = people.map(function(person){
  return person.age;
});
// Returns: [32, 24, 15]
```

##### [for()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
```js
var people = [
  { name: "George", age: 32 },
  { name: "Lindsay", age: 24 },
  { name: "Mike", age: 15 },
];

var adultCheck = [];
for (var i = 0; i < people.length; i++) {
  var continuation = (people[i].age >= 18) ? "of age" : "under-age";
  adultCheck.push(people[i].name + " is " + continuation);
}
// Returns: ["George is of age", "Lindsay is of age", "Mike is under-age"]
```

##### [foreach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
```js
var people = [
  { name: "George", age: 32 },
  { name: "Lindsay", age: 24 },
  { name: "Mike", age: 15 },
];

var adultCheck = [];
people.forEach(function (person) {
  var continuation = (person.age >= 18) ? "of age" : "under-age";
  adultCheck.push(person.name + " is " + continuation);
});
// Returns: ["George is of age", "Lindsay is of age", "Mike is under-age"]
```

<br>

#### Return the first element in an array that matches a condition
##### [find()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
```js
var inventory = [
  {name: 'apples', quantity: 2},
  {name: 'bananas', quantity: 0},
  {name: 'cherries', quantity: 5}
];

inventory.find(function(fruit){
  return fruit.name === 'cherries';
});
// Returns: { name: 'cherries', quantity: 5 }
```

##### [for()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
```js
var inventory = [
  {name: 'apples', quantity: 2},
  {name: 'bananas', quantity: 0},
  {name: 'cherries', quantity: 5}
];

for (var i = 0; i < inventory.length; i++) {
  if (inventory[i].name === 'cherries') {
    var cherries = inventory[i];
    break;
  }
}
// Returns: { name: 'cherries', quantity: 5 }
```

<br>

#### Test if any element in an array matches a condition
##### [some()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)
```js
var numbers = [12, 5, 8, 1, 4];
numbers.some(function(element){
  return element > 10;
}); 
// Returns: true
```

##### [some() using arrow functions - ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
```js
var numbers = [12, 5, 8, 1, 4];
numbers.some(element => element > 10);
// Returns: true
```

##### [for()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
```js
var numbers = [12, 5, 8, 1, 4];
var numbersCheck = false;

for (var i = 0; i < numbers.length; i++) {
  if (numbers[i] > 10) {
    numbersCheck = true;
    break;
  }
}
// Returns: true
```

<br>

#### Test if all elements in an array match a condition
##### [every()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)
```js
var numbers = [12, 54, 18, 130, 44];
numbers.every(function(element){
  return element > 10;
}); 
// Returns: true
```

##### [every() using arrow functions - ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
```js
var numbers = [12, 54, 18, 130, 44];
numbers.every(element => element > 10); 
// Returns: true
```

##### [for()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
```js
var numbers = [12, 55, 18, 130, 44];
var numbersCheck;

for (var i = 0; i < numbers.length; i++) {
  if (numbers[i] > 10) {
    numbersCheck = true;
  } else {
    numbersCheck = false;
    break;
  }
}
// Returns: true
```

<br>

#### Return the sum of all values in an array
##### [reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) - [video](https://www.youtube.com/watch?v=Wl98eZpkp-c)
```js
var numbers = [1, 10, 20, 50, 100];
numbers.reduce(function(sum, number){
  return sum + number;
});
// Returns: 181
```

##### [for()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
```js
var numbers = [1, 10, 20, 50, 100];
var sum = 0;

for (var i = 0; i < numbers.length; i++) {
  sum += numbers[i];
}
// Returns: 181
```

##### [foreach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
```js
var numbers = [1, 10, 20, 50, 100];
var sum = 0;

numbers.forEach(function (number) {
  sum += number;
});
// Returns: 181
```

<br>

#### Combine two arrays 
*Think about memory usage before deciding which approach to use - https://davidwalsh.name/combining-js-arrays*

##### [concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)
```js
var arr1 = [1, 2];
var arr2 = [3, 4];

// Using this method does not overwrite `arr1` (More memory used)
var arr3 = arr1.concat(arr2); // Equivalent to: [arr1[0], arr1[1], arr2[0], arr2[1]];
// Returns: [1, 2, 3, 4]
```

##### [spread operator - ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_operator)
```js
var arr1 = [1, 2];
var arr2 = [3, 4];

// Using this method does not overwrite `arr1` (More memory used)
var arr3 = [...arr1, ...arr2]; // Equivalent to: [arr1[0], arr1[1], arr2[0], arr2[1]];
// Returns: [1, 2, 3, 4]
```

##### [Array.prototype.push.apply()](https://davidwalsh.name/merge-arrays-javascript)
```js
var arr1 = [1, 2];
var arr2 = [3, 4];

// Using this method overwrites `arr1` (Less memory used)
Array.prototype.push.apply(arr1, arr2); // Equivalent to: [arr1[0], arr1[1], arr2[0], arr2[1]];
// Returns: [1, 2, 3, 4]
```

