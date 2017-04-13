## Aliases

#### Creating a type alias to be re-used 
```js

type CurrencyOperationsType = {data: number[], output: (outputValues: boolean) => number[]};

let currencyOperations: CurrencyOperationsType = {
  data: [100, 3.99, 10],
  output: function (outputValues: boolean): number[] { 
    return this.data;
  }
}
```
