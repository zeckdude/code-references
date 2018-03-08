## Common CSS Scenarios

#### Quick Reference Notes

| Purpose | Notes |
|---------------|----------------------------------------------------------|
| [Make container take full width and height of the viewport](https://github.com/zeckdude/code-references/blob/master/react/state.md#set-initial-state-values) | *None* |


<br>

#### Make container take full width and height of the viewport
##### [vw](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vw)
##### [vh](https://developer.mozilla.org/en-US/docs/Web/CSS/length#vh)
```css
.container {
  width: 100vw;
  height: 100vh;
}
```
##### [*See example of code*](http://jsbin.com/sicacanimi/edit?html,css,output)

<br>

#### Center everything in the container both vertically and horizontally
##### [display](https://developer.mozilla.org/en-US/docs/Web/CSS/display#display-inside)
##### [justify-content](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content)
##### [align-items](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)
```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```
##### [*See example of code*](http://jsbin.com/yovajohuho/edit?html,css,output)

<br>

#### Center anything in its parent container regardless of its dimensions
##### [transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
##### [translate](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate)
```css
.center-within-parent {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
}
```
##### [*See example of code*](http://jsbin.com/forehukosu/1/edit?html,css,output)

<br>

#### Capitalize the first letter of a paragraph
##### [::first-letter](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter)
##### [text-transform](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)
```css
p::first-letter {
  text-transform: capitalize;
}
```
##### [*See example of code*](http://jsbin.com/qivowoquwa/1/edit?html,css,output)

<br>


