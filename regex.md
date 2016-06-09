### RegEx

**Test Regular Expression Patterns:** https://regex101.com<br>
**Learn and find documentation:** http://regexone.com<br>
**Detailed Documentation:** https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx<br>
**Using Regex in JavaScript:** http://code.tutsplus.com/tutorials/you-dont-know-anything-about-regular-expressions-a-complete-guide--net-7869

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

<br>

*Match any characters that start with the given characters*<br>
https://regex101.com/r/sX0dS4/1
```js
^Why hello there
```

<br>

*Match any characters that start with the given characters and end after the given characters*<br>
https://regex101.com/r/qA3uQ6/1<br>
Needs to be an exact match for the entire string
```js
^Why hello there$
// Matches: Why hello there
// Doesn't Match: Why hello there Bob
```

<br>

*Capture any characters that are surrounded by parantheses*<br>
https://regex101.com/r/nA7pY9/2<br>
```js
^(.+).pdf$
// Matches: file_07241999.pdf
// Doesn't Match: testfile_fake.pdf.tmp
```

<br>

*Capture any characters that match either option*<br>
https://regex101.com/r/zL9rT6/1<br>
```js
I love (cats|dogs)
// Matches: I love cats OR I love dogs
// Doesn't Match: I love logs OR I love cogs
```

<br>

*Match various ways to enter a US phone number and capture the area code, first 3 numbers, and the last 4 numbers*<br>
https://regex101.com/r/nU7jN6/1<br>
```js
[\(1]?\s?(\d{3})\)?[-\s]?([\d]{3})[-\s]?([\d]{4})
```

<br>

*Find a match where the given substring is found anywhere within another string, and then capture the whole string*<br>
https://regex101.com/r/fX2dO2/1<br>
```js
((?:.*)(ling)(?:.*))
// Matches: linguist OR klingon OR sailing
// Doesn't Match: linting
```

<br>

*Match various ways to enter an email address and capture the username, domain name with domain type, and the domain type by itself*<br>
https://regex101.com/r/sX5oW9/1<br>
```js
([\w\.\+\d]+)@([\w\.]+(?:\.([\w]{2,3})))
```

