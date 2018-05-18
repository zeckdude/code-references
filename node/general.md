## General

#### Useful NPM packages

| Package Name | Purpose | Notes |
|---------------|----------------------------------------|----------------------------------------------------------|
| [yargs](https://www.npmjs.com/package/yargs) | Yargs helps you build interactive command line tools, by parsing arguments and generating an elegant user interface. | *None* |
| [nodemon](https://www.npmjs.com/package/nodemon) | Nodemon will watch the files in the directory in which nodemon was started, and if any files change, nodemon will automatically restart your node application. | For use during development of a node.js based application. Should be installed globally. |
<br>

#### Get the command entered into the command line
##### [process.argv](https://nodejs.org/docs/latest/api/process.html#process_process_argv)
```js
const command = process.argv[2];
```

<br>
