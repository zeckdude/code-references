## DOM

#### Select an element by ID
##### [getElementById()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById)
```js
document.getElementById("button-container");
// Returns: Reference to a matching Element object
```

<br>
#### Create an anchor tag string with the specified string as its name attribute
##### [anchor()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/anchor) 
```js
var str = 'Table of Contents';
str.anchor('table-contents');
// Returns: "<a name="table-contents">Table of Contents</a>"
```

<br>
#### Create an anchor tag string with the specified string as its href attribute
##### [link()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/link) 
```js
var str = 'Table of Contents';
str.link("https://developer.mozilla.org/");
// Returns: "<a href="https://developer.mozilla.org/">Table of Contents</a>"
```



