Media queries in CSS are providing responsiveness to the web page.

```css
@media screen and (width:1160px) {
  h2 {
  font-size: 5rem;
  color: lightcoral;
  }
}
```

### 🧜‍♂️ Display type

1.  Screen
2.  Print
3.  All

**max-width: 1160px** is similar to **width <= 1160px**

### AND operator

```css
@media screen and (orientation:portrait) {
  
}
```

### OR operator

```css
@media all and (orientation:landscape), (width < 485) {
}
```

### NOT operator

```css
@media not all and (width:970) {

}
```

## Animations

Used to show more than one transitions of state

```css
section {
animation-name: slider;
animation-duration: 2s;
animation-iteration-count: infinite; /* Can be number 1, 2, 3*/
animation-delay: 2s
animation-direction: normal; /* Can be reverse, alternate, alternate-reverse */
animation-fill-mode: forward; /* Can be backword. Which key frame to end animation on */
animation-timing-function: linear;
}
```

```css
@keyframes slider {
  25% {
  
  }
  50% {
  }
  75% {
  }
  100% {
  }
  
}
```