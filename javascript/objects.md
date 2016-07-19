## Objects

#### Notes
When an object is created, it automatically inherits pre-defined properties and methods that exist on the `Object` object from which it extends. Every object has a `__proto__` property, which is a pointer to the object from which it extended. When drilling down into it, it is possible to see the properties and methods that are available via inheritance. The object that is being referenced by the `__proto__` property is known as a **prototype object**. Inherited properties and methods are passed to their children via the **prototype chain**.

##### Create an instance of an object using [Object.create()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create)
```js
var person = {
  getName: function() {
    return this.firstName + " " + this.lastName;
  }
};

// Create an instance of the person object
var jeff = Object.create(person);

// Assign values to the newly created object
jeff.firstName = "Jeff";
jeff.lastName = "Jordan";

// Another way to instantiate the new object using Object.create()
var jeff = Object.create(person, {
  firstName: { value: "Jeff" },
  lastName: { value: "Jordan" }
});
```

##### Create an instance of an object using a constructor function and the [new keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new)
```js
function Person() = {
  getName: function() {
    return this.firstName + " " + this.lastName;
  }
};

// Create an instance of the person object
var jeff = new Person();

// Assign values to the newly created object
jeff.firstName = "Jeff";
jeff.lastName = "Jordan";
```



#### Copy an object
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

<br>
#### Determine if an object contains a specified property
##### [in operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in)
```js
var obj = { num: 1, str: "hello", bool: true }
"str" in obj;
// Returns: true
```

##### [non-identity operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Non-identity_strict_inequality_(!))
```js
var obj = { num: 1, str: "hello", bool: true }
obj.str !== undefined;
// Returns: true
```

<br>
#### Determine if an object contains a specified property (not inherited)
##### [hasOwnProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)
```js
var obj = { num: 1, str: "hello", bool: true }
obj.hasOwnProperty("str");
// Returns: true
```

<br>
#### Loop through properties of an object
##### [for in loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)
```js
var obj = { num: 1, str: "hello", bool: true }
for (var prop in obj) {
  console.log("obj." + prop + " = " + obj[prop]);
}
// Displays in the console:
"obj.num = 1"
"obj.str = hello"
"obj.bool = true"

// To only affect the properties of the object that are not inherited, use the hasOwnProperty() method within the loop iteration
for (var prop in obj) {
  if (obj.hasOwnProperty(prop)) {
    console.log("obj." + prop + " = " + obj[prop]);
  }
}
```

<br>
#### Remove a property from an object
##### [delete operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete)
```js
var obj = { num: 1, str: "hello", bool: true }
delete obj.str;
// Returns (if the removal was succesful): true
// Contains: {num: 1, bool: true}
```
