## Arrow Functions

#### Using Default Parameters
##### [Default parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)
```js
// If the `name` argument isn't provided, then use the default parameter
const announceName = (name = 'the dude') => {alert("Hello I'm " + name + "!")};
announceName();
// Alerts: Hello I'm the dude!
announceName('Chris');
// Alerts: Hello I'm Chris!
```
