### RegEx

*Match any first three characters followed by a single period*
```js
...\.

// Matches: cat. OR 896. OR ?=+.
// Doesn't Match: abc1
```

<br>

*Match any string that begins with any of a set of specified characters followed by other characters*
```js
[cmf]an

// Matches: can OR man OR fan
// Doesn't Match: pan
```

<br>

*Match any string that doesn't begin with a specified character followed by other characters*
```js
[^b]og

// Matches: hog OR dog
// Doesn't Match: bog
```


