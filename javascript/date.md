## Date

#### Alternatives to using the `Date` object
*The `Date` object can be a bit difficult to use, so there are some libraries that make things a lot easier*

| Library  | Notes  |
|---------------|--------|
| [Moment.js](http://momentjs.com/) | Preferred library  |
| [Datejs](http://www.datejs.com/) | *None*   |

<br>

___

<br>

#### Create a new instance of the Date object
##### [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
```js
// Instance using the current date and time
var now = new Date();

// Instance using a specified date and time (Can be supplied in a variety of ways)
var birthday = new Date(1983, 3, 9, 3, 24, 0); // Preferred format for consistency (Months start counting at zero)
var birthday = new Date('1983 04 09');
var birthday = new Date('09 April 1983');
var birthday = new Date('April 09, 1983 03:24:00');
var birthday = new Date(418694400);
```

<br>
___
<br>

#### Get day of the week
##### [getDay()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getDay)
```js
birthday.getDay();
// Returns (days start counting at zero) (Tuesday): 1
```

<br>
___
<br>

#### Get day of the month
##### [getDate()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getDate)
```js
birthday.getDate();
// Returns: 9
```

<br>
___
<br>

#### Get month
##### [getMonth()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getMonth)
```js
birthday.getMonth();
// Returns (months start counting at zero) (April): 3
```

<br>
___
<br>

#### Get year
##### [getFullYear()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getFullYear)
```js
birthday.getFullYear();
// Returns: 1983
```

<br>
___
<br>

#### Update the day of the month
##### [setDate()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setDate)
```js
// Set the day of the month to 11
birthday.setDate(11);
```

<br>
___
<br>

#### Update the month
##### [setMonth()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setMonth)
```js
// Set the month to November (months start counting at zero)
birthday.setMonth(10);
```

<br>
___
<br>

#### Update the year
##### [setFullYear()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/setFullYear)
```js
// Set the year to 1988
birthday.setFullYear(1988);
```

