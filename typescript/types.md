## Types

#### String
##### [Basic Types - String](https://www.typescriptlang.org/docs/handbook/basic-types.html#string)
```js
let name: string = 'Chris';
```

#### Boolean
##### [Basic Types - Boolean](https://www.typescriptlang.org/docs/handbook/basic-types.html#boolean)
```js
let cool: boolean = true;
```

#### Number
##### [Basic Types - Number](https://www.typescriptlang.org/docs/handbook/basic-types.html#number)
```js
let age: number = 34;
```

#### Any
##### [Basic Types - Any](https://www.typescriptlang.org/docs/handbook/basic-types.html#any)
```js
let anything: any = 'hello';
anything = 55;
anything = false;
```

#### Array
##### [Basic Types - Array](https://www.typescriptlang.org/docs/handbook/basic-types.html#array)
```js
let favNums: number[] = [9, 83, 72];
let favBeatles: string[] = ['John', 'George', 'Ringo'];
```

#### Tuple
##### [Basic Types - Tuple](https://www.typescriptlang.org/docs/handbook/basic-types.html#tuple)
*A tuple is an array type which specifies which exact types are in the array and in which order*
```js
let address: [number, string] = [2500, 'Broadway Ave'];
```

#### Enum
##### [Basic Types - Enum](https://www.typescriptlang.org/docs/handbook/basic-types.html#enum)
*An enum is a way of giving more friendly names to sets of numeric values*
```js
enum Color {
  Gray,
  Green = 100,
  Blue
}

let color: Color = Color.Gray;
// contains: 0 (numerical representation of the value in the enum - It begins with 0 since we didn't define a number for it)

let color: Color = Color.Green;
// contains: 100 (numerical representation of the value in the enum - Instead of 1, which would be the default numerical assignment, it is 100 since we specifically set it as such)

let color: Color = Color.Blue;
// contains: 101 (numerical representation of the value in the enum - It is 100 since it continues the numerical assignment based on the last number, if it doesn't have its own assignment)
```



