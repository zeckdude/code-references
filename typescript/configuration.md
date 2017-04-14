## Configuration

#### Initialize configuration file 
```js
tsc --init // creates tsconfig.json file
```

<br>

#### Properties in configuration file 
```js
{
  "compilerOptions": {
    "module": "commonjs",
    "target": "es5",
    "noImplicitAny": false,
    "sourceMap": false,
    "strictNullChecks": false // Switch to turn on check which disallows a variable from being defined as null without having `null` defined as a type
  },
  "exclude": [ // Define folders which should be excluded from being compiled
    "node_modules"
  ]
}
```
