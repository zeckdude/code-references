## Web Extension Development

### Required files
#### manifest.json 
This file serves as a settings file for the extension<br />
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

