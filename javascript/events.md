## Events

#### Listen for page readiness
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
```js
// When the markup and DOM has been fully parsed
document.addEventListener("DOMContentLoaded", theDomHasLoaded, false);

function theDomHasLoaded(e) {
    // Perform operation
}

// When the page has fully loaded, including images, stylesheets, scripts, and other external resources
window.addEventListener("load", pageFullyLoaded, false);

function pageFullyLoaded(e) {
    // Perform operation
}
```

#### Add single event listener
*Listen for the specified event on the specified element and then run the specified function*
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) using these possible [event types](https://developer.mozilla.org/en-US/docs/Web/Events)
##### [mouse events](https://www.kirupa.com/html5/mouse_events_in_javascript.htm)
##### [keyboard events](https://www.kirupa.com/html5/keyboard_events_in_javascript.htm)
```js
button.addEventListener("click", callback);
```

<br>
___
<br>

#### Add multiple event listeners to one event for one element
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
```js
['click', 'mouseover'].forEach(function(event){
  button.addEventListener(event,callback,false);
});
```

<br>
___
<br>

#### Add event listener to one event for multiple elements
The process of applying the event listener on the parent element is known as *Event Delegation*. It is useful to keep memory usage down, is more efficient, reduces code bloat, and allows dynamically created elements to use previously defined event listeners.
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
##### [article - kirupa.com](https://www.kirupa.com/html5/handling_events_for_many_elements.htm)
##### [article - davidwalsh.name](https://davidwalsh.name/event-delegate) 
```js
var parent = document.querySelector("#buttonsDiv");
parent.addEventListener("click", onClickBtn, false);

// e.target: Returns the element that started the event, which in this case is the button that was clicked
// e.currentTarget: Returns the element which the event was attached to, which in this case is the #buttonsDiv element which is in the ancestor tree above the clicked element
```

**Approach #1**
```js
// Targets any element below the parent element
function onClickBtn(e) {
  if (e.target !== e.currentTarget) {
    // Perform operation
  }
  e.stopPropagation();
}
```

**Approach #2**
```js
// Targets any element that has the specified classname in the ancestor tree
function onClickBtn(e) {
  if (e.target && e.target.classList.contains("active")) {
	// Perform operation
  }
}
```

**Approach #3**
```js
// Targets any element that has the specified tag and classname in the ancestor tree
function onClickBtn(e) {
  if (e.target && e.target.matches("a.active")) {
	// Perform operation
  }
}
```

<br>
___
<br>

#### Remove single event listener
##### [removeEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener)
*In order to remove an event listener after adding it, you cannot use an anonymous function when you add the listener initially*
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
```js
addEventListener("keypress", function(event){
  console.log("You pressed the " + event.key + " character");
  // Returns (e.g. when the user presses the "Space" key): "You pressed the Space character"
});
```

<br>
___
<br>

#### Stop the default behavior of an event
##### [preventDefault()](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault)
```js
button.addEventListener("click", function(event){
  event.preventDefault();
  // Prevents the link redirect to occur
});
```

<br>
___
<br>

#### Force the event listener to propogate in either direction
![Event Propogation] (https://github.com/zeckdude/code-references/blob/master/img/javascript/event_propogation_kirupa.png)<br>
*(Source: Kirupa.com)*<br>
##### [addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) - [video](https://www.kirupa.com/html5/event_capturing_bubbling_javascript.htm)
The third argument passed to the `addEventListener()` method specifies if the event should:
 * Propogate upwards (Bubbling): When the event fires on the element clicked on first, then propogates up the document tree, firing an event on each parent element until it reaches the root node. Defined by the boolean `false`. This is the default setting, so it is not necessary to include this argument usually.
 * Propogate downwards (Capturing): When the event fires on the root element first, then propogates down the document tree, firing an event on each child element until it reaches the target element that was clicked on. Defined by the boolean `true`.
```js
// Propogate upwards (Bubbling)
button.addEventListener("click", function(event){
  // Perform operations here
}, false);

// Propogate downwards (Capturing)
button.addEventListener("click", function(event){
  // Perform operations here
}, true);
```

<br>
___
<br>

#### Stop an event from propogating
##### [stopPropogation()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/stopPropogation)
```js
button.addEventListener("click", function(event){
  event.stopPropogation();
}, false);
```

