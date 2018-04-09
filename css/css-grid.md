## CSS Grid

#### Syntax
| Keyword       | Description                                                     |
|---------------|-----------------------------------------------------------------|
| `display: grid` | Sets the element's contents as the columns of the row |

#### Create a basic grid
##### [display](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
```html
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

```css
.container {
  display: grid;
}
```

<br>

#### Define the rows and columns for the grid
##### [grid-template-rows](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows)
##### [grid-template-columns](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns)
```html
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

```css
.container {
  display: grid;
  
  /* Two rows of 50px height each */
  grid-template-rows: 50px 50px;
  /* Alternative approach */
  grid-template-rows: repeat(2, 50px);
  
  /* Three columns with the 1st and 3rd column at 100px and the 2nd column filling in the remaining space */
  grid-template-columns: 100px auto 100px;
}
```

<br>

#### Set responsive columns or rows to be a fraction of the grid
##### [grid-template-rows](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows)
##### [grid-template-columns](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns)
```html
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

```css
.container {
  display: grid;
  
  /* Each row will take up 50% of the grid height, since they're both 1 fraction unit out of 2 defined fraction units and 1/2 = 50% */
  grid-template-rows: 1fr 1fr;
  /* Alternative approach */
  grid-template-rows: repeat(2, 1fr);
  
  /* The first and 3rd column take 1/5th of the grid width, while the 2nd column takes 3/5th of the grid width */
  grid-template-columns: 1fr 3fr 1fr;
}
```

<br>

#### Create a gap between the rows and columns
##### [grid-gap](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-gap)
```html
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
</div>
```

```css
.container {
  display: grid;
  grid-template-rows: 50px 50px;
  grid-template-columns: 100px auto 100px;
  grid-gap: 3px;
}
```
