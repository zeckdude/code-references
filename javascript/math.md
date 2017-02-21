## Math

#### Get the square root of a number
##### [Math.sqrt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt)
```js
Math.sqrt(25);
// Returns: 5
```

<br>
___
<br>

#### Get the absolute value of a number
##### [Math.abs()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/abs)
```js
Math.abs(3);
// Returns: 3

Math.abs(-4.6);
// Returns: 4.6
```

<br>
___
<br>

#### Round a number to the nearest integer
##### [Math.round()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round)
```js
Math.round(4.5);
// Returns: 5

Math.round(4.499);
// Returns: 4
```

<br>
___
<br>

#### Round a number down to the nearest integer
##### [Math.floor()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor)
```js
Math.floor(4.2);
// Returns: 4

Math.floor(-4.2);
// Returns: -5
```

<br>
___
<br>

#### Round a number up to the nearest integer
##### [Math.ceil()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil)
```js
Math.ceil(4.2);
// Returns: 5

Math.ceil(-4.2);
// Returns: -4
```

<br>
___
<br>

#### Get the smallest number from a set of numbers
##### [Math.min()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/min)
```js
Math.min(1,2,3);
// Returns: 1

Math.min.apply(Math, [1,2,3]);
// Returns: 1
```

<br>
___
<br>

#### Get the largest number from a set of numbers
##### [Math.max()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max)
```js
Math.max(1,2,3);
// Returns: 3

Math.max.apply(Math, [1,2,3]);
// Returns: 3
```

<br>
___
<br>

#### Get a random number
##### [Math.random()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random)
```js
function getRandomIntInclusive(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
```

<br>
___
<br>

