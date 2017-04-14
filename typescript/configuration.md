## Configuration

#### Initialize configuration file 
```js
tsc --init // creates tsconfig.json file
```

<br>

#### Properties in configuration file
##### [Project Configuration - tsconfig.json](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)
##### [Project Configuration - Compiler Options](https://www.typescriptlang.org/docs/handbook/compiler-options.html)
```js
{
  "compilerOptions": {
    "module": "commonjs",
    "target": "es5", // Define which version of JS typescript should compile to
    "noImplicitAny": false, // Prevent a variable from being implicitly set to the `any` type when a variable is declared without a type and not defined with a value
    "sourceMap": false, // Enable sourcemaps, so breakpoints can be set in the typescript files directly
    "strictNullChecks": false, // Prevent a variable from being defined as null without having `null` defined as a type
    "noEmitOnError": false, // Prevent JS from being compiled if typescript errors are found
    "noUnusedParameters": false, // Prevent methods from having declared variables that are never used
  },
  "exclude": [ // Define folders which should be excluded from being compiled
    "node_modules"
  ]
}
```
