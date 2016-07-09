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

