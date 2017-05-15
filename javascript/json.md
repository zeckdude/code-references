## JSON

#### Convert a JS object to JSON format
##### [JSON.stringify()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)
```js
var obj = {
  name: "Zack",
  age: 23
};

JSON.stringify(obj);
// Returns in JSON format (one line): {"name":"Zack","age":23}

JSON.stringify(obj, null, 2);
// Returns in JSON format (pretty print): 
// {
// 	"name": "Zack",
// 	"age": 23
// }
```

<br>

#### Convert a JSON object to JS format
##### [JSON.parse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)
```js
var json = '{"name": "Zack","age": 23}';
JSON.parse(json);
// Returns in JS format: {"name":"Zack","age":23}
```
