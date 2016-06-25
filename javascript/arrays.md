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
##### [foreach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
```js
var arr = [2, "George Rose", true];
arr.forEach(function (item, index) {
  console.log("The element in position " + index + " is " + item);
});
// Displays in the console (only first loop iteration shown):  "The element in position 0 is 2"
```

##### [for](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
```js
var arr = [2, "George Rose", true];
for(var index = 0; index < arr.length; index++) {
  console.log("The element in position " + index + " is " + arr[index]);
}
// Displays in the console (only first loop iteration shown):  "The element in position 0 is 2"
```

<br>
#### Add one or more elements to the beginning of an array
##### [unshift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)
```js
var arr = [2, "George Rose", true];
arr.unshift(42, "Harley Quinn");
// Returns (the new number of elements in the array):  5
// Contains: [42, "Harley Quinn", 2, "George Rose", true]
```

<br>
#### Add one or more elements at a specified position of an array
##### [splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
```js
var arr = [2, "George Rose", true];
arr.splice(2, 0, "Taylor", "Harley");
// Returns (the elements that were removed - Empty array since we only added elements):  []
// Contains: [2, "George Rose", "Taylor", "Harley", true]
```

<br>
#### Add one or more elements to the end of an array
##### [push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
```js
var arr = [2, "George Rose", true];
arr.push(42, "Harley Quinn");
// Returns (the new number of elements in the array):  5
// Contains: [2, "George Rose", true, 42, "Harley Quinn"]
```



<br>
#### Remove the first element of an array
##### [shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)
```js
var arr = ["Jim", "George", "Bob"];
arr.shift();
// Returns (the element that was removed): "Jim"
// Contains: ["George", "Bob"]
```

<br>
#### Remove one or more elements at a specified position of an array
##### [splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
```js
var arr = [2, "George Rose", true, "Jet"];
arr.splice(1, 2);
// Returns (the elements that were removed): ["George Rose", true]
// Contains: [2, "Jet"]
```

<br>
#### Remove the last element of an array
##### [pop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)
```js
var arr = ["Jim", "George", "Bob"];
arr.pop();
// Returns (the element that was removed): "Bob"
// Contains: ["Jim", "George"]
```




