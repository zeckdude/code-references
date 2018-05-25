## Debugging

#### Typical flow debugging on command line
```js
// Start up the file in debug mode
node inspect <filename>.js

// Go to each statement
n

// Go to the first debugger statement in the code
c 

// Once on the line where the debugger statement is, go into repl mode so you can view the contents of variables
repl

// Now enter the name of the variable you want to see the contents of

// Exit out of repl mode
ctrl-c

// Exit out of debug mode
ctrl-c
ctrl-c
```

<br>

#### Start a node app from the command line in debug mode
```js
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
