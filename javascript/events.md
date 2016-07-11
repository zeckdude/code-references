## Events

#### Add single event listener
*Listen for the specified event on the specified element and then run the specified function*
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) using these possible [event types](https://developer.mozilla.org/en-US/docs/Web/Events)
```js
button.addEventListener("click", callback);
```

<br>
___
<br>

#### Add multiple event listeners
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
```js
['click', 'mouseover'].forEach(function(event){
  button.addEventListener(event,callback,false);
});
```

<br>
___
<br>

#### Remove single event listener
##### [removeEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener)
```js
button.removeEventListener("click", callback);
```

<br>
___
<br>

#### Get the event type performed
##### [type](https://developer.mozilla.org/en-US/docs/Web/API/Event/type)
```js
button.addEventListener("click", function(event){
  console.log(event.type);
  // Consoles out: "click"
});
```

<br>
___
<br>

#### Get the element that the event was performed on
##### [target](https://developer.mozilla.org/en-US/docs/Web/API/Event/target)
```js
button.addEventListener("click", function(event){
  console.log(event.target);
  // Returns a reference to the node of the element which the event was performed on
});
```

<br>
___
<br>

#### Get the keyboard key that was pressed
##### [keypress event type](https://developer.mozilla.org/en-US/docs/Web/Events/keypress)
##### [key](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key)
##### [String.fromCharCode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode)
```js
addEventListener("keypress", function(event){
  console.log("You pressed the " + event.key + " character");
  // Returns (e.g. when the user presses the "Space" key): "You pressed the Space character"
});
```

