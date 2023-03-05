## 🏯 Cascade

The order of CSS rules matter. When two rules from the same cascade layer apply and both have equal specificity, the one that is defined last in the stylesheet is the one that will be used.

## 🗣️ Specificity

Order of Specificity to apply styling in CSS

**ID > Class > Element**

Check specificity from [Specificity Calculator](https://specificity.keegan.st/)

## 👪 Inheritance

Some style properties are inherited from its parent some are not.

[https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance#:~:text=In%20CSS%2C%20inheritance%20controls%20what,value%20of%20the%20parent%20element](https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance#:~:text=In%20CSS%2C%20inheritance%20controls%20what,value%20of%20the%20parent%20element)

## 🇨🇴 Color Theory

24 bit color scheme in CSS

-   Hexadecimal
-   RGB()
-   RGBA()

## 🦄 Units in CSS

1.  Absolute
    1.  px
    2.  cm
    3.  In (Inch)
2.  Relative
    
    1.  % → takes x percent of its parent length
        1.  For example, div(child) inside a section(parent). section w: 400px, h: 200px. div w:40%, h:60%. div will take 40% and 60% of section(parent)
    2.  em → multiple of the parents size (Snowballing effect)
    3.  rem → relative to root element(HTML element) size which is 16(default)
    4.  vh → viewport height
    5.  vw → viewport width

**em** is a CSS unit relative to the font size of the parent element, while **rem** is a CSS unit relative to the font size of an html element.

### 🥊 Box Model

1.  Dimensions
2.  Padding
3.  Margin
4.  Border

box-sizing prevents element to bleed out from its parent

### 🖥️ Display Property (display)

1.  block → height, width, margin, padding all are respected
2.  inline → height and width are not respected, margin, padding are respected
3.  inline-block → respect all properties(height, width, margin, padding) along with inline property
4.  none → remove visibility of element

### 🧘‍♂️ Positions

Alters the normal flow of the web page

1.  static: positioned according to the normal flow of the document
2.  relative: positioned according to the normal flow of the document, and then offset _relative to itself_ based on the values of top, right, bottom, and left
3.  absolute: The element is removed from the normal document flow, and no space is created for the element in the page layout. It is positioned relative to its **closest positioned ancestor**, if any; otherwise, it is placed relative to the initial [containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block). Its final position is determined by the values of top, right, bottom, and left.
```css
        #absolute{
            position: relative;
            border: 1px solid black;
        }
        
        #absolute #middle{
            position: absolute;
            /* left:10px; */
            right: 10px;
            top:10px;
        }
```
4. fixed
5. sticky


> **A sticky element toggles between relative and fixed , depending on the scroll position**. It is positioned relative until a given offset position is met in the viewport - then it "sticks" in place (like position:fixed).

[https://developer.mozilla.org/en-US/docs/Web/CSS/position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)