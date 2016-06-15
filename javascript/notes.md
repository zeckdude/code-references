### JavaScript Theory

##### Collecting performance information
Using [`Date().getTime()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime):
```js
var start = new Date().getTime();
for (var n = 0; n < maxCount; n++) {
  /* perform operation to be measured */
}
var elapsed = new Date().getTime() - start;
console.log("Measured Time:", elapsed);
```

<br>

Using [`performance.now()`](https://developer.mozilla.org/en-US/docs/Web/API/Performance/now) (more accurate count):
```js
var start = performance.now();
for (var n = 0; n < maxCount; n++) {
  /* perform operation to be measured */
}
var elapsed = (performance.now() - start).toFixed(4) + ' seconds';
console.log("Measured Time:", elapsed);
```
