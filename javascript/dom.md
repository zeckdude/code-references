## DOM

#### Get an element by ID
##### [getElementById()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById)
```js
document.getElementById("button-container");
// Returns: Reference to a matching Element object
```

##### [querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
```js
document.querySelector("#button-container");
// Returns: Reference to a matching Element object
```

<br>
#### Get all elements with a specified tag name
##### [getElementsByTagName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName)
```js
document.getElementsByTagName("p");
// Returns: Reference to all matching elements in an array-like object
```

##### [querySelectorAll()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
```js
document.querySelectorAll("p");
// Returns: Reference to all matching elements in an array-like object
```

<br>
#### Get all elements with a specified class name
##### [getElementsByClassName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName)
```js
document.getElementsByClassName("active");
// Returns: Reference to all matching elements in an array-like object
```

##### [querySelectorAll()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
```js
document.querySelectorAll(".active");
// Returns: Reference to all matching elements in an array-like object
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



