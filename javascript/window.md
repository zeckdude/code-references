## Window

#### Display an alert box
##### [alert()](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert)
```js
alert("Hello there!");
```

<br>
___
<br>

#### Display a confirm box and capture user selection
##### [confirm()](https://developer.mozilla.org/en-US/docs/Web/API/Window/confirm)
```js
if (confirm("Would you like to proceed?")) {
  // Action to perform if user selects `OK`
} else {
  // Action to perform if user selects `Cancel`
}
```

<br>
___
<br>

#### Get location details
##### [location](https://developer.mozilla.org/en-US/docs/Web/API/Window/location)
```js
// Get full URL
window.location.href
// Returns: "http://www.example.com?something=whoknows"

// Get query string
window.location.search
// Returns: "?something=whoknows"

// Get basename with Protocol 
window.location.origin
// Returns: "http://www.example.com"

// Get Hostname
window.location.hostname
// Returns: "www.example.com"

// Get Protocol
window.location.protocol
// Returns: "http:"
```

<br>
___
<br>

#### Navigate to URL
##### [location](https://developer.mozilla.org/en-US/docs/Web/API/Window/location)
```js
window.location = "http://www.somewhere.com";
// Navigates to new URL
```

<br>
___
<br>

#### Reload the current page
##### [location.reload()](https://developer.mozilla.org/en-US/docs/Web/API/Window/location)
```js
window.location.reload(true);
// Reloads the current page
```

<br>
___
<br>

#### Perform an operation after a specified period of time
##### [setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers/setTimeout) - [video](https://www.youtube.com/watch?v=zucCjXApXOU)
##### [clearTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers/clearTimeout) - [video](https://www.youtube.com/watch?v=zucCjXApXOU)
```js
var timeID = window.setTimeout(function(){
  // Perform an operation
}, 3000);
// Performs an operation after 3 seconds (3000 milliseconds)

window.clearTimeout(timeID);
// Cancels the setTimeout() function that was set, specified by the `timeID` identifier
```

<br>
___
<br>

#### Perform an operation repeatedly with a specified delay between each repeat
##### [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers/setInterval) - [video](https://www.youtube.com/watch?v=zucCjXApXOU)
##### [clearInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowTimers/clearInterval) - [video](https://www.youtube.com/watch?v=zucCjXApXOU)
```js
var timeID = window.setInterval(function(){
  // Perform an operation
}, 3000);
// Performs an operation every 3 seconds (3000 milliseconds)

window.clearInterval(timeID);
// Cancels the setInterval() function that was set, specified by the `timeID` identifier
```
