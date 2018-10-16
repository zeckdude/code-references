## Useful methods

#### Useful Node Methods

| Method | Purpose
|---------------|----------------------------------------|
| [__filename](https://github.com/zeckdude/code-references/blob/master/node/useful-methods.md#get-the-absolute-filepath-of-the-current-file) | Get the absolute filepath of the current file |
| [path.parse()](https://github.com/zeckdude/code-references/blob/master/node/useful-methods.md#get-the-absolute-filepath-of-the-current-file) | Parse a filepath to get various sections as convenient properties |
| [fs.readdir()](https://github.com/zeckdude/code-references/blob/master/node/useful-methods.md#list-out-the-contents-of-a-directory) | List out the contents of a directory |
| [emitter.emit & emitter.on](https://github.com/zeckdude/code-references/blob/master/node/useful-methods.md#list-out-the-contents-of-a-directory) | Emit and listen for an event |
| [Create a basic http server]() | Create a basic http server |
<br>

#### Get the absolute filepath of the current file
##### [__filename](https://nodejs.org/api/modules.html#modules_filename)
```js
console.log(__filename);

/*
Returns:
/Users/chris.seckler/Documents/sites/learning/node-mosh/second-app'
*/
```

<br>

#### Parse a filepath
##### [path.parse()](https://nodejs.org/dist/latest-v8.x/docs/api/path.html#path_path_parse_path)
```js
const path = require('path');
const pathObj = path.parse('/Users/chris.seckler/Documents/sites/learning/node-mosh/second-app/app.js');
console.log(pathObj);

/*
Returns:
{ 
  root: '/',
  dir: '/Users/chris.seckler/Documents/sites/learning/node-mosh/second-app',
  base: 'app.js',
  ext: '.js',
  name: 'app' 
}
*/
```

<br>

#### List out the contents of a directory
##### [fs.readdir()](https://nodejs.org/api/fs.html#fs_fs_readdir_path_options_callback)
```js
const fs = require('fs');
const files = fs.readdir('./', (error, files) => {
  if (error) { console.log('Error', error); }
  else { console.log('Result', files); }
})
```

<br>

#### Emit and listen for an event
##### [emitter.emit()](https://nodejs.org/api/events.html#events_emitter_emit_eventname_args)
##### [emitter.on()](https://nodejs.org/api/events.html#events_emitter_on_eventname_listener)
```js
const EventEmitter = require('events');
const emitter = new EventEmitter();

// Create a listener
emitter.on('messageLogged', (eventArguments) => console.log('Listener called with arguments', eventArguments));

// Emit an event
emitter.emit('messageLogged', {
  id: 1,
  url: 'http://www.google.com'
});
```

<br>

#### Create a basic http server
##### [http.createServer()](https://nodejs.org/api/http.html#http_http_createserver_options_requestlistener)
##### [response.write()](https://nodejs.org/api/http.html#http_response_write_chunk_encoding_callback)
##### [response.end()](https://nodejs.org/api/http.html#http_response_end_data_encoding_callback)
```js
const http = require('http');
const server = http.createServer((req, res) => {
  if (req.url === '/') {
    res.write('Hello World');
    res.end();
  }

  if (req.url === '/api/courses') {
    res.write(JSON.stringify([1, 2, 3]));
    res.end();
  }
});

server.listen(3000);
console.log('Listening on port 3000...');
```
