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
var input = form["searchBox"];
// Returns: Reference to a matching Element object
```

##### [form.elements](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)
```js
var form = document.forms["search"];
var input = form.elements["searchBox"];
// Returns: Reference to a matching Element object
```

<br>
___
<br>

#### Reset all form fields back to their initial values specified in the HTML
##### [reset()](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reset)
```js
var form = document.forms["search"];
form.reset();
// Resets all form fields for the specified form
```

<br>
___
<br>

#### Set the action attribute on a form
##### [form.action](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/action)
```js
var form = document.forms["search"];
form.action = "/alt/search";
// Sets the action attribute for the specified form
```

<br>
___
<br>

#### Perform an action when a form field is focused on
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
```js
var form = document.forms["search"];
var input = form["searchBox"];
input.addEventListener('focus', function() {
  // Perform action
}, false);
// Perform an action when the form field becomes active
```

<br>
___
<br>

#### Perform an action when a form field is blurred
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
```js
var form = document.forms["search"];
var input = form["searchBox"];
input.addEventListener('blur', function() {
  // Perform action
}, false);
// Perform an action when the form field stops being active
```

<br>
___
<br>

#### Perform an action when a form field value has been changed and is no longer in focus
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
```js
var form = document.forms["search"];
var input = form["searchBox"];
input.addEventListener('change', function() {
  // Perform action
}, false);
// Perform an action when the form field's value has been changed and the field is no longer in focus
```

<br>
___
<br>

#### Perform an action when a form is submitted
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
```js
var form = document.forms["search"];
form.addEventListener('submit', function(e) {
  e.preventDefault();
  // Perform action
}, false);
// Perform an action when the form is submitted
```

<br>
___
<br>

#### Get the value of an input field
##### [input.value](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
```js
var form = document.forms["search"];
var input = form["searchBox"];
input.value;
// Returns: The value of the input field
```

<br>
___
<br>

#### Set the value of an input field
##### [input.value](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
```js
var form = document.forms["search"];
var input = form["searchBox"];
input.value = "A new value";
// Sets: The value of the input field
```

<br>
___
<br>
