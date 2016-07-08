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
#### Get the first matching element within a specified element
##### [Element.querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector)
```js
document.querySelector("#firstDiv").querySelector("#thirdPar");
// Returns: Reference to a matching Element object
```

##### [querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
```js
document.querySelector("#firstDiv #thirdPar");
// Returns: Reference to a matching Element object
```

<br>
#### Get all matching elements within a specified element
##### [Element.querySelectorAll()](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll)
```js
document.querySelector("#firstDiv").querySelectorAll("p");
// Returns: Reference to a matching Element object
```

##### [querySelectorAll()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
```js
document.querySelectorAll("#firstDiv p");
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
#### Get previous sibling of selected element
##### [Node.prevSibling](https://developer.mozilla.org/en-US/docs/Web/API/Node/prevSibling)
##### [Node.prevElementSibling](https://developer.mozilla.org/en-US/docs/Web/API/Node/prevElementSibling)
```js
document.querySelector("#description").prevSibling;
// Returns: Reference to the previous sibling, regardless of what it is

document.querySelector("#description").prevElementSibling;
// Returns: Reference to the previous sibling (Must be an element)
```

<br>
#### Get next sibling of selected element
##### [Node.nextSibling](https://developer.mozilla.org/en-US/docs/Web/API/Node/nextSibling)
##### [Node.nextElementSibling](https://developer.mozilla.org/en-US/docs/Web/API/Node/nextElementSibling)
```js
document.querySelector("#description").nextSibling;
// Returns: Reference to the next sibling, regardless of what it is

document.querySelector("#description").nextElementSibling;
// Returns: Reference to the next sibling (Must be an element)
```

<br>
#### Get parent element of selected element
##### [Node.parentNode](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode)
```js
document.querySelector("#description").parentNode;
// Returns: Reference to the parent element
```

<br>
#### Get all children elements of selected element
##### [Node.children](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/children)
```js
document.querySelector("#description").children;
// Returns: Reference to all children elements
```

<br>
#### Get first child element of selected element
##### [Node.firstElementChild](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/firstElementChild)
```js
document.querySelector("#description").firstElementChild;
// Returns: Reference to first child element
```

<br>
#### Get last child element of selected element
##### [Node.lastElementChild](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/lastElementChild)
```js
document.querySelector("#description").lastElementChild;
// Returns: Reference to last child element
```

<br>
#### Get element value
##### [Element.innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)
```js
document.querySelector("#description").innerHTML;
// Returns: String of the element's value
```

<br>
#### Set element value
##### [Element.innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)
```js
document.querySelector("#description").innerHTML = "New Value here";
// Returns: String of the element's value
```

<br>
#### Get element class value
##### [Element.getAttribute()](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)
```js
document.querySelector("#description").getAttribute("class");
// Returns: String of the element's `class` value
```

##### [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
```js
document.querySelector("#description").className;
// Returns: String of the element's `class` value
```

<br>
#### Set element class value (Overrides attribute value)
##### [Element.setAttribute](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute)
```js
document.querySelector("#description").setAttribute("class", "rounded");
```

##### [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
```js
document.querySelector("#description").className = "rounded";
// Returns: String of the element's `class` value
```

<br>
#### Add a new element class value (Adds to all other already existing classes)
##### [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
```js
document.querySelector("#description").className += " rounded";
// Add the specified class
```

##### [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
```js
document.querySelector("#description").classList.add('rounded');
// Add the specified class
```

<br>
#### Remove a element class value
##### [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
```js
document.querySelector("#description").classList.remove('rounded');
// Remove the specified class
```

##### [String.replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
```js
var element = document.querySelector("#secondPar");
var replaceClass = "selected";
element.className = element.className.replace(new RegExp('( |^)' + replaceClass + '( |$)', 'g'), ' ').trim();
// Remove the specified class
```

<br>
#### Toggle an element class value
##### [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
```js
document.querySelector("#description").classList.toggle('rounded');
// Show/hide the specified class
```

<br>
#### Check if an element has a specified class
##### [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
##### [String.indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)
```js
document.querySelector("#description").className.indexOf("selected") > -1;
// Returns: true
```

<br>
#### Get element attribute value
##### [Element.getAttribute()](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)
```js
document.querySelector("#description").getAttribute("href");
// Returns: String of the element's `href` value
```

<br>
#### Set element attribute value (Overrides attribute value)
##### [Element.setAttribute()](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute)
```js
document.querySelector("#description").setAttribute("href", "http://www.google.com");
```

<br>
#### Get the tag type of an element
##### [Element.tagName](https://developer.mozilla.org/en-US/docs/Web/API/Element/tagName)
```js
document.querySelector("#description").tagName;
// Returns: String of the tag type, e.g. "DIV"
```

<br>
#### Create an element in preparation of adding it to the DOM
##### [createElement()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement)
##### [createTextNode()](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTextNode)
##### [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)
```js
var newElement = document.createElement("p"); // Create a reference to a new element object
var newText = document.createTextNode("Hi there and greetings!"); // Create a new text node
newElement.appendChild(newText); // Append the new text node to the new element object
```

<br>
#### Append a newly created element to the DOM
##### [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)
```js
document.querySelector("#firstDiv").appendChild(newElement);
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



