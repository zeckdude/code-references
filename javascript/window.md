## Window

#### Display an alert box
##### [alert()](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert)
```js
alert("Hello there!");
```

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
#### Navigate to URL
##### [location](https://developer.mozilla.org/en-US/docs/Web/API/Window/location)
```js
window.location = "http://www.somewhere.com";
// Navigates to new URL
```

<br>
#### Reload the current page
##### [location.reload()](https://developer.mozilla.org/en-US/docs/Web/API/Window/location)
```js
window.location.reload(true);
// Reloads the current page
```

