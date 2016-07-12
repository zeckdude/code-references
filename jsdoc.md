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
```
