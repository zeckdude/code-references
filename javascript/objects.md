## Objects

#### Notes
When an object is created, it automatically inherits pre-defined properties and methods that exist on the object from which it was instantiated(via a constructor or Object.create()) as well as on the `Object` object from which every object extends. Every object has a `__proto__` property, which is a pointer to the object from which it extended. When drilling down into it, it is possible to see the properties and methods that are available via inheritance. The object that is being referenced by the `__proto__` property is known as a **prototype object**. Inherited properties and methods are passed to their children via the **prototype chain**.

##### Guidelines to follow
1. Constructors should be used to deal with initialization.
2. Prototypes should contain shared properties and methods that remain constant.
3. To differentiate an instance's properties from the prototype's properties (which it inherits), the desired properties need to be assigned on the instance itself.

<br>
___
<br>

#### Create an instance of an object using `Object.create()` 
##### [Object.create()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create).
*The object that gets created inherits all properties and methods within its prototype chain. If properties or methods on any objects, that it inherits from, changes then those will change for this object as well.*
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

<br>
___
<br>

#### Create an instance of an object using a constructor function
##### [new keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new)
*The object that gets created gets all properties and methods from the constructor function at the time of its creation, but if any properties or methods are added to the constructor function at a later time, the new object does not inherit those. It will only inherit properties and methods that are added to the constructor's prototype object.*
```js
// Constructor function. The properties and methods defined within it are added to the instance when it gets created.
function Person(salutation) {
  this.getName = function() {
    return salutation + " " + this.firstName + " " + this.lastName;
  };
};

// Create an instance of the person object
var jeff = new Person("Mr.");

// Assign values to the newly created object
jeff.firstName = "Jeff";
jeff.lastName = "Jordan";
```

<br>
___
<br>

#### Add a property or method to the constructor's prototype object
*Any properties and methods that are added to the prototype object are automatically inherited by any instances based on the constructor.*
```js
function Person() {
  // Add initialization properties and methods
};

Person.prototype.introduceMyself = function() {
  return "Hello, I am " + this.getName();
}
Person.prototype.profession = "Web Developer";
```

<br>
___
<br>

#### Check if an object is an instance of a specified object
##### [instanceof](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof) 
```js
function Person() {
  // Add initialization properties and methods
};
var jeff = new Person();

jeff instanceof Person
// Returns: true
```

<br>
___
<br>

#### Determine the instance's constructor function's name
##### [obj.constructor.name](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/name#Examples)
```js
function Person() {
  // Add initialization properties and methods
};
var jeff = new Person();

jeff.constructor.name
// Returns: "Person"
```

<br>
___
<br>

#### Determine if a property belongs to the instance or is inherited
##### [obj.hasOwnProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)
```js
function Person() {
  // Add initialization properties and methods
};
var jeff = new Person();
Person.prototype.greet = function(){
  return "Hello!";
};
jeff.firstName = "Jeffrey";

jeff.hasOwnProperty("firstName"); // Property was defined on the instance
// Returns: true
jeff.hasOwnProperty("greet"); // Property was defined on the prototype object for the constructor
// Returns: false
```

<br>
___
<br>

#### Overwrite prototype properties for a specified instance
```js
function Person() {
  // Add initialization properties and methods
};
Person.prototype.profession = "Web Developer";
var jeff = new Person();

jeff.profession; // Displays the `profession` property as defined on the constructor's prototype object
// Returns: "Web Developer"

jeff.profession = "Software Development Engineer"; // Changes the `profession` property on the specified instance 
jeff.profession;
// Returns: "Software Development Engineer"
```

<br>
___
<br>

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
___
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
___
<br>

#### Determine if an object contains a specified property (not inherited)
##### [hasOwnProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)
```js
var obj = { num: 1, str: "hello", bool: true }
obj.hasOwnProperty("str");
// Returns: true
```

<br>
___
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
___
<br>

#### Remove a property from an object
##### [delete operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete)
```js
var obj = { num: 1, str: "hello", bool: true }
delete obj.str;
// Returns (if the removal was succesful): true
// Contains: {num: 1, bool: true}
```
