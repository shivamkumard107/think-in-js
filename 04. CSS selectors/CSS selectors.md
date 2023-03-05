HTML tags make a tree like structure. To style a tag in CSS we have to select it.

> Kebab case is used in CSS. For example: fav-movies, web-dev

## 👨‍⚕️ Basic CSS selectors

1.  Elements
Applies to all elements of the HTML file
```css
elementName {
    propertyName: propertyValue;
}
```
2. id
Ids are unique to each element
```css
#idName {
    propertyName: propertyValue;
}
```
3. Class
group of elements to be styled
```css
.className {
    propertyName: propertyValue;
}
```
4. Attribute
styles to apply to the elements whose has the specified attribute
```css
input[type="email"] {
    propertyName: propertyValue;
}
```
5. Universal Selector
To select all the elements. Can be used to reset browser default styles and specify our own default styles. 
```css
*{
    propertyName: propertyValue;
}
```

## Advance Selector

1.  Combinators

2.  Descendant combinator
	1.  For example: `<ancestor-tag> <tag>{ }`
2.  Child combinator
	1.  For example: `<parent-tag> <tag> { }`
3.  General sibling combinator
	1.  style applied to all siblings forward to tag1 i.e all tag2s that exist within the same parent
	2.  `<tag1>~<tag2> {}`
		
4.  Adjacent sibling combinator
	1.  For example: `<tag1> + <tag2> { }`
	1.  style will be added to be forward adjacent sibling(tag2) of the tag1
2.  Pseudo Selectors
1.  A CSS pseudo-class is a keyword added to a selector that specifies a special state of the selected element(s)
2.  For example, the pseudo-class :hover, :focus
3.  Structural pseudo class
	1.  ul li:nth-of-type(x) { } → matches elements based on their position among siblings of the same type (tag name)
	2. x can be a number or "a * n + b" where b is offset a is interval
	3. first-child
	4. last-child
	5. nth-child(x)
