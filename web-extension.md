## Web Extension Development

### Required files
#### manifest.json 
This file serves as a settings file for the extension<br /><br />
Common properties:<br />
- _manifest_version_: Version number for the manifest file. Each version has different requirements of what an extension must follow and it determines the other properties in this file.
- _name_: The name of the extension
- _version_: The version number of the extension
- _content_scripts_: A variable amount of scripts that target specific URL's (or URL patterns)
  - _matches_: URL's that are targeted by the scripts. Examples: `http://www.totescool.com` or `*://*totescool.*`
  - _js_: An array of scripts that will be run for the matching URL's

```json
{
  "manifest_version": 2,
  "name": "Toucan Surprise",
  "version": "0.1",
  "content_scripts": [
    {
      "matches": [
        "<all_urls>"
      ],
      "js": [
        "colors.js",
        "content.js"
      ]
    }
  ]
}
```

<br>

#### content script 
This/these file(s) are run after the page loads and have access to the content on the page.<br /><br />

The content script is defined in the `content_scripts` property in `manifest.json`. Any logs or errors that occur within will output to the console in the developer tools inside the browser window.

```js
let paragraphs = document.getElementsByTagName('p');

const getRandomColor = () => Math.floor(Math.random()*16777215).toString(16);

for (paragraph of paragraphs) {
  const color = getRandomColor();
  paragraph.style['background-color'] = `#${color}`;
}
```

<br>

#### background script 
This/these file(s) are run after the browser launches and are listening for events associated with activity in the browser.<br /><br />

The background script is defined in the `background` property in `manifest.json`. Any logs or errors that occur within will output to the console in the developer tools that can be launched from the extensions page. The background script can communicate with the content script to display or react to user input in the content area.

```js
let paragraphs = document.getElementsByTagName('p');

const getRandomColor = () => Math.floor(Math.random()*16777215).toString(16);

for (paragraph of paragraphs) {
  element.style['background-color'] = getRandomColor();
}
```
