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

#### Get the contents of a file on the server
##### [fs.readFileSync](https://nodejs.org/docs/latest/api/fs.html#fs_fs_readfilesync_path_options)
```js
// Get the contents of JSON file
const notesString = fs.readFileSync('notes.json');

// Convert JSON string to JS object
const notes = JSON.parse(notesString);
```

<br>

#### Create/Overwrite a file on the server
##### [fs.writeFileSync](https://nodejs.org/docs/latest/api/fs.html#fs_fs_writefilesync_file_data_options)
```js
const note = {
  title: 'Some title',
  body: 'Some body'
};

// Convert JS object to JSON string
const noteString = JSON.stringify(note);

// Write the JSON string to JSON file
fs.writeFileSync('notes.json', noteString);
```

<br>
