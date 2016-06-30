## Console
[Chrome Console Documentation](https://developer.chrome.com/devtools/docs/console-api)

<br>
#### Return any of the last five selected DOM elements in the Elements tab
##### [console selectors](https://developer.chrome.com/devtools/docs/commandline-api#0-4)
```js
$0 // Last element selected
$1 // Second to last element selected
$2 // Third to last element selected
$3 // Fourth to last element selected
$4 // Fifth to last element selected
```

<br>
#### Return the first matched element on the page
##### [console selectors](https://developer.chrome.com/devtools/docs/commandline-api#selector)
```js
$('p') // Equivalent to document.querySelector('p') or document.getElementsByTagName('p')[0]
```

<br>
#### Return an array of all matched elements on the page
##### [console selectors](https://developer.chrome.com/devtools/docs/commandline-api#selector_1)
```js
$$('p') // Equivalent to document.querySelectorAll('p') or document.getElementsByTagName('p')
```

<br>
#### Log the value of a variable to the console
##### [console.log()](https://developer.mozilla.org/en-US/docs/Web/API/Console/log)
```js
var num = 2;
console.log("The value of num is", num);
// Logs to the console: The value of num is 2
```

<br>
#### Style a log message
##### [console.log()](https://developer.mozilla.org/en-US/docs/Web/API/Console/log) 
```js
console.log('%cBlue! %cRed!', 'color: blue;', 'color: red;');
// Logs to the console:
```
![Style log message example](img/console/console_log_styling.png)

<br>
#### Log the properties of an object to the console
##### [console.dir()](https://developer.mozilla.org/en-US/docs/Web/API/Console/dir) 
```js
var str = new String("hello");
console.dir(str);
// Logs to the console:
```
![console.dir() example](img/console/console_dir.png)

<br>
#### Display the contents of an array (must contain multiple arrays or objects) in a table
##### [console.table()](https://developer.mozilla.org/en-US/docs/Web/API/Console/table) 
```js
var people = [
  ["John", "Smith"], 
  ["Jane", "Doe"], 
  ["Emily", "Jones"]
];
console.table(people);
// Logs to the console:
```
![console.table() example](img/console/console_table1.png)

```js
var people = [
  { name: "John Smith", age: 25 },
  { name: "Jane Doe", age: 66 },
  { name: "Emily Jones", age: 14 }
];
console.table(people);
// Logs to the console:
```
![console.table() example](img/console/console_table2.png)

```js
var people = [
  { name: "John Smith", age: 25, weight: 160 },
  { name: "Jane Doe", age: 66, weight: 110 },
  { name: "Emily Jones", age: 14, weight: 105 }
];
console.table(people, ["name", "weight"]); // If restricting to only one specific column, a string with the property name works
// Logs to the console:
```
![console.table() example](img/console/console_table3.png)

<br>
#### Group log messages
##### [console.group()](https://blog.mariusschulz.com/2014/11/25/advanced-javascript-logging-using-console-group) 
```js
console.group("URL Details");
console.log("Scheme: HTTPS")
console.log("Host: example.com");
console.groupEnd();
// Logs to the console:
```
![console.group() example](img/console/console_group1.png)

```js
// Collapse the group by default
console.groupCollapsed("URL Details");
console.log("Scheme: HTTPS")
console.log("Host: example.com");
console.groupEnd();
// Logs to the console:
```
![console.group() example](img/console/console_group2.png)

```js
console.group("URL Details");   
console.log("Scheme: HTTPS")
console.log("Host: example.com");

// Nested group
console.group("Query String Parameters");
console.log("foo: bar")
console.log("value: 42");
console.groupEnd();

console.groupEnd();
// Logs to the console:
```
![console.group() example](img/console/console_group2.png)

<br>
#### Clear the console
##### [console.clear()](https://developer.mozilla.org/en-US/docs/Web/API/Console/clear) 
```js
console.clear();
// Alternatively, the alias clear() or the keyboard shortcut Cmd-K will clear the console also
```

<br>
#### Set a counter
##### [console.count()](https://developer.mozilla.org/en-US/docs/Web/API/Console/count) 
```js
console.count("page load");
// Logs to the console:
```
![console.count() example](img/console/console_count.png)

<br>
#### Copy a string representaton of the specified object
##### [copy()](https://developer.chrome.com/devtools/docs/commandline-api#copyobject) 
```js
copy($0);
```

<br>
#### Open the elements tab and select the element/function specified
##### [inspect()](https://developer.chrome.com/devtools/docs/commandline-api#inspectobjectfunction) 
```js
inspect($0); // Displays the selected element in the elements tab
inspect(runCar); // Opens the Sources panel when the function is called
```

<br>
#### Set a breakpoint to break when the specified function is called
##### [debug()](https://developer.chrome.com/devtools/docs/commandline-api#debugfunction) 
```js
debug(runCar);
```

<br>
#### Logs a message when the specified function is called and which arguments are passed into it
##### [monitor()](https://developer.chrome.com/devtools/docs/commandline-api#monitorfunction) 
```js
function accelerateCar(speed, distance) { 
  // Do something here 
}
monitor(accelerateCar);
accelerateCar(160, 200);
// Displays to the console: function accelerateCar called with arguments: 160, 200
```

<br>
#### Set a breakpoint at a specified position in the code process
##### [debugger](https://developers.google.com/web/tools/chrome-devtools/debug/breakpoints/add-breakpoints?hl=en#create-manual-breakpoints) 
```js
debugger; // Add to the code where the breakpoint should occur
```




