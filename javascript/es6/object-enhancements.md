## Object Enhancements

#### Shorthand technique to assign object properties keys that have the same name as the variable that is assigned to its value 
##### [Object initializer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#New_notations_in_ECMAScript_2015)
```js
let name = 'Chris';
let age = 34;

// Traditional technique 
let obj = { 
  name: name,
  age: age
};

// Shorthand technique 
let obj = { name, age };

```

<br>

#### Shorthand technique of declaring a method on an object
##### [Method definitions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions)
```js
// Traditional technique 
let obj = { 
  greet: function() {
    alert('hello');
  }
};

// Shorthand technique 
let obj = { 
  greet() {
    alert('hello');
  }
};

```

<br>
