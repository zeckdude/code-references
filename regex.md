### RegEx

**Test Regular Expression Patterns:** [https://regex101.com](https://regex101.com)<br>
**Learn and find documentation:** [http://regexone.com](http://regexone.com)
**Using Regex in JavaScript:** [http://code.tutsplus.com/tutorials/you-dont-know-anything-about-regular-expressions-a-complete-guide--net-7869](http://code.tutsplus.com/tutorials/you-dont-know-anything-about-regular-expressions-a-complete-guide--net-7869)

**Flags**<br>

| Abbreviation  | Meaning                                                                                           |
|---------------|---------------------------------------------------------------------------------------------------|
| `g`             | global. All matches                                                                               |
| `i`             | insensitive. Case insensitive match (ignores case of [a-zA-Z])                                    |
|               |                                                                                                   |

<br>

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

*Match any substring that doesn't begin with a specified character followed by other characters*
```js
[^b]og

// Matches: hog OR dog
// Doesn't Match: bog
```

<br>

*Match any substring that has characters between a range of numbers*
```js
[0-6]+

// Matches: 1234
// Doesn't Match: 897
```

<br>

*Match any substring that has any alphanumeric characters within it*
```js
[\w]+
[A-Za-z0-9_]+

// Matches: george_12
// Doesn't Match: @#$%
```

<br>

*Match any substring with a specified number of repetitions of a specified character or range of characters*<br>
In this case, it is looking for any repetitions of at least 2 or more of the character "o"
```js
o{2,}
```

<br>

*Match any characters that are repeated*<br>
https://regex101.com/r/cF6iI3/1<br>
This way it will include all characters following each other that match the criteria and put them within the same match
```js
\d+
// Matches: 12345
```

<br>

*Match any characters that are optional*<br>
https://regex101.com/r/rW2cE2/1
```js
files?
// Matches: file OR files
```


