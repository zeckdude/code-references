## Arrays

#### Return the number of elements in an array
##### [length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length)
```js
var arr = [2, "George Rose", true];
arr.length; 
// Returns:  3
```

<br>
#### Loop through an array
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
#### Return the first index of a specified value in an Array
##### [indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
```js
var arr = [3, 7, 2, 7];
arr.indexOf(7);
// Returns:  1

arr.indexOf("George"); 
// Returns:  -1
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

