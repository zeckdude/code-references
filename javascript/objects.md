## Objects

#### Copy an array
##### [Object.create()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create)
```js
// Create a reference to another object
var firstObject = { num: 1 }
var secondObject = firstObject;
secondObject.num = 99; // Since the secondObject refers to the same object as firstObject, the num property is changed in both objects
console.log(firstObject); // Returns { num: 99 }   
console.log(secondObject); // Returns { num: 99 } 

// Make a copy of the specified object including all its properties
var thirdObject = Object.create(firstObject);
thirdObject.num = 1000;
console.log(firstObject); // Returns { num: 99 }   
console.log(secondObject); // Returns { num: 99 }
console.log(thirdObject); // Returns { num: 1000 }
```
