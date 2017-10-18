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
##### [Understanding Deep and Shallow Copy in Javascript](https://we-are.bookmyshow.com/understanding-deep-and-shallow-copy-in-javascript-13438bad941c)
When you create a completely unrelated copy of an existing variable. Any change to either of the variables will not affect the other.<br> 

```js 
// Deep copy an array
var carBrands = ['Toyota', 'VW', 'BMW'];

// Different ways to deep copy an array
var autoCompanies = carBrands.slice();
var autoCompanies = [ ...carBrands ];
var autoCompanies = _.cloneDeep(carBrands); // lodash

autoCompanies === carBrands // false
```

```js 
// Deep copy an object
var car = { color: 'green', height: 10, isTruck: false };

// Different ways to deep copy an object
var whip = Object.assign({}, car);
var whip = { ...car };
var whip = _.cloneDeep(car) // lodash

whip === car // false
```

<br> 


