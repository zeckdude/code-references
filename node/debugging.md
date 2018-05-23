## Debugging


#### Start a node app from the command line in debug mode
```
node inspect <filename>.js
// Using nodemon so that you can make changes in the code and it will re-run the app in inspect mode
nodemon inspect <filename>.js
```

<br>

#### View a specified number of lines around the current breakpoint
```js
list(10)
```

<br>

#### Go to next statement in the code
```js
next
// Alternative shorthand
n
```

<br>

#### Continue to the end of the script (or the next debugger statement)
```js
c
```

<br>

#### Set a debugger statement within the code for the debug mode to stop on
```js
const person = {
  name: 'Chris'
};

debugger;
person.name = 'Jeff';
```

<br>

#### Get into REPL (read-evaluate-print-loop) mode to see values in code
```js
repl
```

<br>
