## Glossary

#### Lexical scope
The regions in the source where we can refer to a variable by name without getting access errors<br>
```js
var name = 'jim';

function sayHello() {
  var timeOfDay = 'morning';
  alert(`Good ${timeOfDay} ${name}`); 
}

// The function has access to the `name` variable because it was created in the global scope
// It also has access to the `timeOfDay` variable because it was created in its own scope
sayHello();

// This part of the code has access to the `name` variable because it was created in the global scope
console.log(name);

// This part of the code does not have access to the `timeOfDay` variable because it was created in the sayHello() function scope
console.log(timeOfDay); // Uncaught ReferenceError: timeOfDay is not defined
```

<br>

#### Shallow copy
When you copy a variable and are still referring to the same place in memory. Any change to either of the variables will affect both of them.<br> 
```js 
var a = 1; 
var b = a; 
a === b // true
```

<br> 

<br>

#### Deep copy
When create a completely unrelated copy of an existing variable. Any change to either of the variables will not affect the other.<br> 
```js 
var a = 1; 
var b = a; 
a === b // true
```

<br> 


