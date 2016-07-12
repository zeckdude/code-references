## JSDoc

#### Documenting which parameters a function accepts
##### [tag - @param](http://usejsdoc.org/tags-param.html)
###### [multiple types](http://usejsdoc.org/tags-param.html#multiple-types-and-repeatable-parameters)
```js
/**
 * @param {(string|string[])} name - User's name, or an array of names
 */
```
###### [any type](http://usejsdoc.org/tags-param.html#multiple-types-and-repeatable-parameters)
```js
/**
 * @param {*} name - User's name
 */
```

<br>
___
<br>

#### Documenting a parameter's properties
##### [tag - @param](http://usejsdoc.org/tags-param.html#parameters-with-properties)
```js
/**
 * Assign the project to an employee.
 *
 * @param {Object} employee - The employee who is responsible for the project.
 * @param {string} employee.name - The name of the employee.
 * @param {string} employee.department - The employee's department.
 */
Project.prototype.assign = function(employee) {
    // ...
};
```

<br>
___
<br>

#### Documenting optional parameters
##### [tag - @param](http://usejsdoc.org/tags-param.html#optional-parameters-and-default-values)
```js
/**
 * Greet the user
 *
 * @param {string} [name] - Name of person to say hello to
 * @returns {string} Greeting
 */
function hello(name) {
  name = name || "visitor";
  alert("Hello " + name + "!");
}
```

<br>
___
<br>

#### Documenting an unknown number of parameters
##### [tag - @param](http://usejsdoc.org/tags-param.html#multiple-types-and-repeatable-parameters)
```js
/**
 * Return the sum of all numbers passed to the function
 *
 * @param {...number} num - A positive or negative number.
 */
function sum(num) {
    var i = 0, n = arguments.length, t = 0;
    for (; i < n; i++) {
        t += arguments[i];
    }
    return t;
}
```

<br>
___
<br>

#### Returning a value from a function
##### [tag - @returns](http://usejsdoc.org/tags-returns.html)
```js
/**
 * Greet the user
 *
 * @param {string} name - Name of person to say hello to
 * @returns {string} Greeting
 */
function hello(name) {
  return "Hello "+name +"!";
}
```

<br>
___
<br>

#### Identifying a function as a constructor
##### [tag - @constructor](http://usejsdoc.org/tags-constructor.html)
```js
/**
 * Create a new book
 *
 * @constructor
 * @param {string} title - The title of the book.
 * @param {string} author - The author of the book.
 */
function Book(title, author) {
  // ...
}

var book = new Book("The Da Vinci Code", "Dan Brown");
```

