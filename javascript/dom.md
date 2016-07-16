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
___
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
___
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
___
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
___
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
___
<br>

#### DOM Traversal Methods illustrated

![Kirupa - Traversing methods] (https://github.com/zeckdude/code-references/blob/master/img/javascript/kirupa_traversing_1.png)<br>
*(Source: kirupa.com)* 

<br>

![Kirupa - Traversing methods] (https://github.com/zeckdude/code-references/blob/master/img/javascript/kirupa_traversing_2.png)<br>
*(Source: kirupa.com)* 

<br>
___
<br>

#### Get previous sibling of selected element
##### [Node.prevSibling](https://developer.mozilla.org/en-US/docs/Web/API/Node/prevSibling)
##### [Node.previousElementSibling](https://developer.mozilla.org/en-US/docs/Web/API/NonDocumentTypeChildNode/previousElementSibling)
```js
document.querySelector("#description").prevSibling;
// Returns: Reference to the previous sibling, regardless of what it is

document.querySelector("#description").previousElementSibling;
// Returns: Reference to the previous sibling (Must be an element)
```

<br>
___
<br>

#### Get next sibling of selected element
##### [Node.nextSibling](https://developer.mozilla.org/en-US/docs/Web/API/Node/nextSibling)
##### [Node.nextElementSibling](https://developer.mozilla.org/en-US/docs/Web/API/NonDocumentTypeChildNode/nextElementSibling)
```js
document.querySelector("#description").nextSibling;
// Returns: Reference to the next sibling, regardless of what it is

document.querySelector("#description").nextElementSibling;
// Returns: Reference to the next sibling (Must be an element)
```

<br>
___
<br>

#### Get parent element of selected element
##### [Node.parentNode](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode)
```js
document.querySelector("#description").parentNode;
// Returns: Reference to the parent element
```

<br>
___
<br>

#### Get all children elements of selected element
##### [Node.children](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/children)
```js
document.querySelector("#description").children;
// Returns: Reference to all children elements
```

<br>
___
<br>

#### Get first child element of selected element
##### [Node.firstChild](https://developer.mozilla.org/en-US/docs/Web/API/Node/firstChild)
##### [Node.firstElementChild](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/firstElementChild)
```js
document.querySelector("#description").firstChild;
// Returns: Reference to the first child, regardless of what it is

document.querySelector("#description").firstElementChild;
// Returns: Reference to first child element
```

<br>
___
<br>

#### Get last child element of selected element
##### [Node.lastChild](https://developer.mozilla.org/en-US/docs/Web/API/Node/lastChild)
##### [Node.lastElementChild](https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/lastElementChild)
```js
document.querySelector("#description").lastChild;
// Returns: Reference to the last child, regardless of what it is

document.querySelector("#description").lastElementChild;
// Returns: Reference to last child element
```

<br>
___
<br>

#### Get element tags with value
##### [Element.outerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/outerHTML)
```js
document.querySelector("#description").outerHTML;
// Returns: String of the element's tags with value, e.g. "<p id="description">Hello there</p>"
```

<br>
___
<br>

#### Get element value
##### [Node.textContent](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent)
```js
document.querySelector("#description").textContent;
// Returns: String of the element's value
```

##### [Element.innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)
```js
document.querySelector("#description").innerHTML;
// Returns: String of the element's value
```

<br>
___
<br>

#### Set element value
##### [Node.textContent](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent)
```js
document.querySelector("#description").textContent = "New Value here";
```

##### [Element.innerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)
```js
document.querySelector("#description").innerHTML = "New Value here";
```

<br>
___
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
___
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
___
<br>

#### Add a new element class value (Adds to all other already existing classes)
*Comprehensive Function: http://stackoverflow.com/a/18492076/83916*

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
___
<br>

#### Remove a element class value
*Comprehensive Function: http://stackoverflow.com/a/18492076/83916*

##### [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
```js
document.querySelector("#description").classList.remove('rounded');
// Remove the specified class
```

##### [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
##### [String.replace()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
```js
var element = document.querySelector("#secondPar");
var replaceClass = "selected";
element.className = element.className.replace(new RegExp('( |^)' + replaceClass + '( |$)', 'g'), ' ').trim();
// Remove the specified class
```

<br>
___
<br>

#### Toggle an element class value
##### [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
```js
document.querySelector("#description").classList.toggle('rounded');
// Add/remove the specified class
```

<br>
___
<br>

#### Check if an element has a specified class
*Comprehensive Function: http://stackoverflow.com/a/18492076/83916*

##### [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
##### [String.indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)
```js
document.querySelector("#description").className.indexOf("selected") > -1;
// Returns: true
```

##### [Element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
##### [String.test()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/test)
```js
var replaceClass = "selected";
(new RegExp('( |^)' + replaceClass + '( |$)', 'g')).test(document.querySelector("#secondPar").className);
// Returns: true
```

##### [Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
```js
document.querySelector("#description").classList.contains('rounded');
// Returns: true
```

<br>
___
<br>

#### Get element attribute value
##### [Element.getAttribute()](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)
```js
document.querySelector("#description").getAttribute("href");
// Returns: String of the element's `href` value
```

<br>
___
<br>

#### Set element attribute value (Overrides attribute value)
##### [Element.setAttribute()](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute)
```js
document.querySelector("#description").setAttribute("href", "http://www.google.com");
```

<br>
___
<br>

#### Get the tag type of an element
##### [Element.tagName](https://developer.mozilla.org/en-US/docs/Web/API/Element/tagName)
```js
document.querySelector("#description").tagName;
// Returns: String of the tag type, e.g. "DIV"
```

<br>
___
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
___
<br>

#### Prepend a newly created element to the DOM
##### [Node.insertBefore()](https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore)
```js
document.querySelector("#firstDiv").insertBefore(newElement, document.querySelector("#firstDiv").firstChild);
```

##### [Element.insertAdjacentHTML()](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML)
```js
document.querySelector("#firstDiv").insertAdjacentHTML('afterbegin', newElement.outerHTML);
```

<br>
___
<br>

#### Append a newly created element to the DOM
##### [Node.appendChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild)
```js
document.querySelector("#firstDiv").appendChild(newElement);
```

##### [Element.insertAdjacentHTML()](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML)
```js
document.querySelector("#firstDiv").insertAdjacentHTML('beforeend', newElement.outerHTML);
```

##### [Node.insertBefore()](https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore)
```js
document.querySelector("#firstDiv").insertBefore(newElement, null);
```

<br>
___
<br>

#### Add a newly created element to the DOM directly before the specified element
##### [Element.insertAdjacentHTML()](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML)
```js
document.querySelector("#firstPar").insertAdjacentHTML('beforebegin', newElement.outerHTML);
```

<br>
___
<br>

#### Add a newly created element to the DOM directly after the specified element
##### [Element.insertAdjacentHTML()](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML)
```js
document.querySelector("#firstPar").insertAdjacentHTML('afterend', newElement.outerHTML);
```

<br>
___
<br>

#### Remove an element from the DOM
##### [Node.removeChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild)
```js
document.querySelector("#firstPar").parentNode.removeChild(document.querySelector("#firstPar"));
```

<br>
___
<br>

#### Replace an element in the DOM
##### [Element.outerHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/outerHTML)
```js
document.querySelector("#firstPar").outerHTML = newElement.outerHTML
```

##### [Node.replaceChild()](https://developer.mozilla.org/en-US/docs/Web/API/Node/replaceChild)
```js
document.querySelector("#firstPar").parentNode.replaceChild(newElement, document.querySelector("#firstPar"));
```

<br>
___
<br>

#### Hide an element
##### [HTMLElement.style](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
```js
document.querySelector("#firstPar").style.display = "none";
// Hides the element
```

<br>
___
<br>

#### Show an element
##### [HTMLElement.style](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
```js
document.querySelector("#firstPar").style.display = "";
// Shows the element
```

<br>
___
<br>

#### Set styles on an element
##### [HTMLElement.style](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
```js
// Set multiple elements at the same time (Will overwrite all other set styles)
document.querySelector("#firstPar").style.cssText = "color: blue; font-size: 24px;";

// Set multiple elements at the same time (Will overwrite all other set styles)
document.querySelector("#firstPar").setAttribute("style", "color: blue; font-size: 24px;");

// Set a single CSS rule (Will not overwrite OTHER set styles)
document.querySelector("#firstPar").style.border = "1px solid black";
document.querySelector("#firstPar").style.color = "red";
```

<br>
___
<br>

#### Create an anchor tag string with the specified string as its name attribute
##### [anchor()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/anchor) 
```js
var str = 'Table of Contents';
str.anchor('table-contents');
// Returns: "<a name="table-contents">Table of Contents</a>"
```

<br>
___
<br>

#### Create an anchor tag string with the specified string as its href attribute
##### [link()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/link) 
```js
var str = 'Table of Contents';
str.link("https://developer.mozilla.org/");
// Returns: "<a href="https://developer.mozilla.org/">Table of Contents</a>"
```



