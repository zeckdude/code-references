## DOM

#### Select an element by ID
##### [getElementById()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById)
```js
document.getElementById("button-container");
// Returns reference to a matching Element object
```

#### Create an anchor tag string with the specified string as its name attribute
##### [anchor()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/anchor) 
```js
var linkText = 'Table of Contents';
linkText.anchor('table-contents');
// Returns: "<a name="table-contents">Table of Contents</a>"
```

#### Create an anchor tag string with the specified string as its href attribute
##### [link()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/link) 
```js
var linkText = 'Table of Contents';
var linkUrl = 'https://developer.mozilla.org/';
linkText.link(linkUrl);
// Returns: "<a href="https://developer.mozilla.org/">Table of Contents</a>"
```



