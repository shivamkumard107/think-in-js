1.  It is an interface
2.  It is a Data structure
3.  Represent the HTML of a browser in the form of an object
4.  A Web API

> A HTML document consists of **node** and **elements**. Everything is a node in HTML, elements are HTML elements. HTML element is a subset of Node. Everything inside the document (each node) is an object.

`NodeList` and `HTMLCollection` are two iterable data type. Normal array methods push, pop, shift, unshift cannot be used. HTMLCollection contains all elements, NodeList contains everything including elements, text attributes.

Changes done in document object will instantly change the HTML

## DOM Manipulation

1.  Select the element
    1.  Use selectors to select element
        1.  getElementByTagName()
        2.  getElementById()
        3.  getElementByClassName()
        1.  querySelector()
        5.  querySelectorAll()
2.  Manipulate the element
![[Pasted image 20230226175617.png]]

DOM manipulation

```js
const h1 = document.getElementByTagName('h1')[0];
h1.style.color = "red"; // style is object accessible to every element in DOM
```

## 🌐 Text Properties

1.  innerText:
    1.  Gives text inside tag.
    2.  Aware of the styling
    3.  Can also be used as a plain text setter
2.  textContent:
    1.  Gives text inside tag.
    2.  Unaware of the styling
    3.  Can be used as a plain text setter
3.  innerHTML:
    1.  Gives text along with all HTML elements inside the tag
    2.  Used as a HTML setter (respect all html elements inside text)

## 💍 Class List

1.  add()
2.  remove()
3.  toggle()
4.  contains()

## 🏇 Attributes

1.  getAttribute('attribute name')
2.  setAttribute('attribute name', 'attribute value')

## 🕷️ Tree Traversal

1.  parentElement
2.  children
3.  nextElementSibling
4.  previousElementSibling