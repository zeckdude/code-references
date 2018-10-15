## Useful methods

#### Useful Node Methods

| Method | Purpose
|---------------|----------------------------------------|----------------------------------------------------------|
| [path.parse()]() | Parse a filepath to get various sections as convenient properties |
<br>

#### Parse a filepath
##### [path.parse()](https://nodejs.org/dist/latest-v8.x/docs/api/path.html#path_path_parse_path)
```js
const path = require('path');
const pathObj = path.parse('/Users/chris.seckler/Documents/sites/learning/node-mosh/second-app/app.js');
console.log(pathObj);
// Returns:
// { 
//   root: '/',
//   dir: '/Users/chris.seckler/Documents/sites/learning/node-mosh/second-app',
//   base: 'app.js',
//   ext: '.js',
//   name: 'app' 
// }
```
