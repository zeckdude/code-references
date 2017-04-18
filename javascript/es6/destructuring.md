## Destructuring

#### Destructuring an Array
##### [Destructuring Assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
*Convenient way of assigning array values to variables*
```js
// Destructuring an array. Each value in the array are assigned to the provided variable names. The last one is an example of using a default value.
let relatives = ['Gloria', 'Andy', 'Anton'];
let [wife, brother, father, mother = 'Mine'] = relatives;
console.log(wife, brother, father, mother);
// Outputs: Gloria Andy Anton Mine
```

<br>

#### Destructuring an Object
##### [Destructuring Assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
*Convenient way of assigning object properties to variables*
```js
let relatives = {
  wife: 'Gloria',
  brother: 'Andy',
  father: 'Anton',
  mother: 'Mine'
};
    
// Destructuring an object using specific properties in the object that are assigned to the provided variable names.
let { wife: wifey, brother: bro, father: pops } = relatives;
console.log(wifey, bro, pops);
// Outputs: Gloria Andy Anton

// Destructuring an object using specific properties in the object that use their property names as their variable names
let {wife, brother, father, mother} = relatives;
console.log(wife, brother, father, mother);
// Outputs: Gloria Andy Anton Mine
```

<br>

#### Example of using descructuring on function arguments (when an object is provided)
```js
// Assign the specified properties to variables with the same name. Also shows a parameter that has a default value.
function makeSound({ species = 'animal', sound }) {
  console.log('The ' + species + ' says ' + sound + '!');
}

makeSound({
  weight: 23,
  sound: 'woof'
});

// Outputs: The animal says woof!
```
