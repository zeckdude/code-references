### DOM

##### Select an element and save it into a variable
*Select the element with the matching ID*
```js
var buttonContainer = document.getElementById("button-container");
```

##### Create an anchor tag with the specified string as its contents
##### [anchor()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/anchor) 
```js
var linkText = 'Table of Contents';
linkText.anchor('table-contents');
// Returns: <a name="table-contents">Table of Contents</a>
```

##### Create an anchor tag with the specified string as its contents
##### [link()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/link) 
```js
var linkText = 'Table of Contents';
var linkUrl = 'https://developer.mozilla.org/';
linkText.link(linkUrl);
// Returns: <a href="https://developer.mozilla.org/">Table of Contents</a>
```



