## Objects

#### Specify the exact names and types of properties of an object
```js
// This example specifies that the object must contain a property with the name of "name" that contains a string and a property with the name of "age" that contains a number 
let userData: { name: string, age: number } = {
  name: 'Chris',
  age: 27
}

// This example specifies that the object must contains a property named "data" which contains an array of numbers and a property named "output" which contains a function
let currencyOperations: {data: number[], output: (outputValues: boolean) => number[]} = {
  data: [100, 3.99, 10],
  output: function (outputValues: boolean): number[] { // Specifies that the functon accepts a boolean as its argument and returns an array of numbers
    return this.data;
  }
}
console.log(currencyOperations.output(true)); // Outputs the contents of the "data" property (in this case an array of numbers)
```
