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
// Returns: http://www.example.com?something=whoknows

// Get Hostname
window.location.hostname
// Returns: http://www.example.com?something=whoknows
```

