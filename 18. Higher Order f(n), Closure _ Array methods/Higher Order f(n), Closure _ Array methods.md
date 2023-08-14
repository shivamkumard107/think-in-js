## ⚡ Higher Order Functions

```js
function fun(x, y) {
  return z;
}
```

If a function accepts x, y parameter as function and/or return z as a function then it will be called a **Higher Order Function**

## 🤡 Closure
Closure is a function bundled together with it’s **lexical environment**(Physical location of that function)

```js
var a = 200;

function fun() {
    
    var a = 100;

    function innerFun() {
        a++;
        console.log(a);
    }

    return innerFun;
}

var f = fun();
f();
f();
f();
f();
```

In the above code, the scope of fun is popped from the call stack after it returns innerFun. Note that when innerFun is returned, two things are returned, **function definition** and its **closure**. That’s why 'a' can be accessed inside innerFun because it resides in the innerFun’s closure

A **closure** is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment).

**Lexical environment** is the local memory plus lexical environment of its parent.

_Lexical_ meaning in hierarchy

## 🚇 Array Methods
- map() → Used to transform the array (non destructive)
```js
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9];
function square(num) {
  return num ** 2;
}
num.map(square);
```

- **filter()** → transforms the array based on boolean value returned by callback
- **reduce()** → reduce the array to a single value. For example returns sum of all elements of an array
- **sort()** → sort the array according to the comparator function
- **some()** → return true or false if element is present in array according to logic in callback function
- **find()** → returns the element if that is present in the array
- **flat()** → The flat() method creates a new array with all sub-array elements concatenated into it recursively up to the specified depth

```js
const arr1 = [0, 1, 2, [3, 4]];

console.log(arr1.flat());
// expected output: [0, 1, 2, 3, 4]

const arr2 = [0, 1, 2, [[[3, 4]]]];

console.log(arr2.flat(2));
// expected output: [0, 1, 2, [3, 4]]
```