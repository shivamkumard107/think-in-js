## Runtime environment
V8 engine was build for chrome to run Javascript inside browser. It was fast, comparable to C++ or Java. In 2009, Ryan Dahl picked the V8 engine and made a runtime environment for running Javascript outside the browser. Through this Javascript was made a true platform independant langauge. 

### Difference between browser and NodeJS
| **Browser**     | **NodeJS**  |
| ----------- | --------|
| Global object: window | Global object: global |
|DOM API exist|DOM not accessible |
|fetch|node-fetch|
|Cannot access file system|file system|

______________

## View of inbuild libraries
- [[Assertion Testing]]
- [[Process]]
- [[File System]]

#### require keyword

##### require() a file 
```js
// Indise app.js
const library = require('./library')
-------------------------------------
// Inside library.js
const PI = 3.14;
const LUCK_NUM = 37;

const square = num => num ** 2;
const cube = num => num ** 3;

module.export = {
	PI, LUCK_NUM, square, cubeOfNum:cube 
	// cube accesible as cubeOfNum
}

// module.export = square; // another way
```

##### require() folder
A index.js file inside folder, which exports all the sibling js files inside it and can be directly used by app.js file. 

