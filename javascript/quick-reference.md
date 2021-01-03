## Quick Reference



#### Import JS scripts with `defer`
```js
<script src="assets/scripts/app.js" defer></script>
```
Notes:
- It is used when page elements are needed to run the script
- Downloads the JS file right away (while page is parsing) but only execute the scripts after everything on the page has finished parsing
- Another approach is to add the script tag at the end of the body. This causes the JS content to only begin downloading when the page is finished parsing. Therefore using the script tag in the head with `defer` is preferred.

<br>

#### Import JS scripts with `async`
```js
<script src="assets/scripts/vendor.js" async></script>
```
Notes:
- Is used when the script contents don't rely on page contents
- Downloads the JS file right away (while page is parsing) and executes when downloaded

<br>


#### Coercing a truthy/falsy value to a boolean
```js
// Using double bang operator
!!"" // false
!!0 // false
!!null // false
!!NaN // false
!!undefined // false

!!"hello" // true
!!1 // true
!!{} // true
!![] // true

// Using the `Boolean()` method
Boolean("") // false
Boolean(0) // false
Boolean(null) // false
Boolean(NaN) // false
Boolean(undefined) // false

Boolean("hello") // true
Boolean(1) // true
Boolean({}) // true
Boolean([]) // true

```

<br>


#### Use logical OR operator to assign a default value
```js
const name = firstName || 'User';
```
Notes:
- The first truthy value is used. If neither are truthy, then the expression evaluates to undefined.

<br>


#### Use logical AND operator to check if a condition is true and if so, return a second value
```js
const name = isLoggedIn && 'Max';
```
Notes:
- If the first value is not truthy, then the expression evaluates to false;

<br>


#### Function declaration
```js
function sayHello() {
  // Do something
}
```
Notes:
- Gets hoisted to the top of the file and can be called from anywhere
- When used as the value of an object property or event listener, having the function name makes debugging easier

<br>



#### Function expression
```js
const sayHello = function() {
  // Do something
}
```
Notes:
- 

<br>



