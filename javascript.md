# JavaScript

### Common Scenarios

##### Different Ways to check for equality
*Using an if statement*
```
if(varA && varB) {
  return true;
} else {
  return false;
}
```

*Using the not-not operator (http://www.sitepoint.com/javascript-double-negation-trick-trouble/)*
```
return !!(varA && varB)
```

*Using the ternary operator (http://www.sitepoint.com/shorthand-javascript-techniques/#1iftrueelseshorthand)*
```
return (varA && varB) ? true : false;
```

