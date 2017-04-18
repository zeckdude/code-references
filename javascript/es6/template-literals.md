## Template Literals

#### Insert variables into a string without concatenation
##### [Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
```js
// Template literals allow for expressions (variables or other operations such as calculations) to be inserted into strings without needing concatenation
let name = 'Chris';
let greeting = `Hello ${name},
                how are you?`;
console.log(greeting);
// Outputs: Hello Chris,
// how are you?
```
