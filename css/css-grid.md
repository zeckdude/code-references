## CSS Grid

#### Syntax
| Keyword         | Description                                           |
|-----------------|-------------------------------------------------------|
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
##### [grid-template](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template)
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
  
  /* Shorthand approach: Rows and columns are separated by a slash */
  grid-template: repeat(2, 50px) / 100px auto 100px;
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
  grid-template: 50px 50px / 100px auto 100px;
  grid-gap: 3px;
}
```

<br>

#### Define a grid item's start and end position
##### [grid-column-start](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-start)
##### [grid-column-end](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-end)
##### [grid-column](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column)
##### [grid-row-start](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-start)
##### [grid-row-end](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-end)
##### [grid-row](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row)
```html
<div class="container">
  <div class="header">HEADER</div>
  <div class="menu">MENU</div>
  <div class="content">CONTENT</div>
  <div class="footer">FOOTER</div>
</div>
```

```css
.container {
  display: grid;
  grid-template: 40px 200px 40px / repeat(2, 1fr); 
}

.header {
  /* Defines at which column position the grid item begins */
  grid-column-start: 1;
  
  /* Defines at which column position the grid item ends */
  grid-column-end: 3;
  
  /* Shorthand approach: Start and end positions are separated by a slash */
  grid-column: 1 / 3;
  
  /* 
    Alternative approach: Start position is defined and the number of columns the element should span (separated by a slash)
    In this case, it begins at the first position and then spans 2 columns
  */
  grid-column: 1 / span 2;
  
  /* Alternative approach: If the element should span across all columns, the end position can be defined as -1 which is always the last position */
  grid-column: 1 / -1;
}
```

<br>

#### Define a template area to specify the grid layout
##### [grid-template-areas](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas)
```html
<div class="container">
  <div class="header">HEADER</div>
  <div class="menu">MENU</div>
  <div class="content">CONTENT</div>
  <div class="footer">FOOTER</div>
</div>
```

```css
.container {
  height: 100%;
  display: grid;
  grid-template: 40px auto 40px / repeat(12, 1fr);
  
  /* 
    Set a custom identifier to signify how much space a grid item occupies (Use a '.' to signify an empty area)
    Header: 1 row & 12 columns across
    Menu: 1 row (flexible because it is set to auto) & 1 column
    Content: 1 row (flexible because it is set to auto) & 11 columns
    Footer: 1 row & 12 columns across
  */
  grid-template-areas: 
    "h h h h h h h h h h h h"
    "m c c c c c c c c c c c"
    "f f f f f f f f f f f f";
}

/* Each grid item element needs to be linked to the custom letter that is defined in the grid-template-areas property on the grid element */
.header {
  grid-area: h;
}

.menu {
  grid-area: m;
}

.content {
  grid-area: c;
}

.footer {
  grid-area: f;
}
```

<br>

#### Fill the grid with the most available grid items of a certain width (and fallback to a fraction otherwise)
##### [repeat](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat)
##### [minmax()](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax)
```html
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
  <div>7</div>
  <div>8</div>
  <div>9</div>
  <div>10</div>
  <div>11</div>
  <div>12</div>
</div>
```

```css
.container {
  display: grid;
  
  /* 
    The grid will fit as many available grid items as is possible in each column 
    The grid items will be 100px minimum width and 1 fraction unit at their maximum width
      The grid items will all be 100px when possible. If the grid width is at a point where they don't fit all perfectly at 100px width each, then they all change to use 1 fraction unit and become responsive.
  */
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
  grid-template-rows: repeat(2, 100px);
}
```


<br>

#### Define rules for rows that don't have specific definitons (implicit rows)
##### [grid-auto-rows](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-rows)
```html
<div class="container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
  <div>5</div>
  <div>6</div>
  <div>7</div>
  <div>8</div>
  <div>9</div>
  <div>10</div>
  <div>11</div>
  <div>12</div>
</div>
```

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
  
  /* Create as many rows as necessary at 75px height */
  grid-auto-rows: 75px;
}
```
