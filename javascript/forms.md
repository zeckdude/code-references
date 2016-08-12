## Forms

#### Select a form by the name attribute
##### [querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
```js
document.querySelector("[name=search]");
// Returns: Reference to a matching Element object
```

##### [Document.forms](https://developer.mozilla.org/en-US/docs/Web/API/Document/forms)
```js
document.forms["search"];
// Returns: Reference to a matching Element object
```

<br>
___
<br>

#### Select a form field by the name attribute
##### [querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
```js
var form = document.querySelector("[name=search]");
var input = form.querySelector("[name=searchBox]");
// Returns: Reference to a matching Element object
```

##### [Document.forms](https://developer.mozilla.org/en-US/docs/Web/API/Document/forms)
```js
var form = document.forms["search"];
var input = form["search"];
// Returns: Reference to a matching Element object
```

<br>
___
<br>

