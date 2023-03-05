String comparison is based on Unicode(UTF-16) in Javascript.

Make you code DRY (Don’t repeat yourself) and not WET (write everything twice)

1.  mini programs
2.  defined with some name
3.  reusable
4.  makes code modular
5.  function stops when function body completes or return statement reached

```js
function addNum(x, y) {
  const res = x + y;
  console.log(res);
}
```

```js
// no return type in javascript
function multiply(a, b, c) {
    return a * b * c;
}
```

Note the difference between _parameters_ and _arguments_:

-   Function parameters are the names listed in the function's definition.
    
-   Function [arguments](https://developer.mozilla.org/en-US/docs/Glossary/Argument) are the real values passed to the function.
    
-   Parameters are initialized to the values of the arguments supplied.
    

### 🌆 First Class Functions/Citizen

In Javascript, functions can be stored in a variable. There are first class functions.

```js
const sInterest = function (p, r, t) {
    return (p * r * t) / 100;
}
console.log(sInterest(110, 12, 5));
```

### 👩‍⚖️ Function expressions

Function Expression **allows us to create an anonymous function which doesn't have any function name**

```js
let variableName = function(x, y) { statements... return (z) };
```

### 🫦 Arrow functions (syntactical sugars)

```js
const cubeRoot = (num) => {
    return Math.cbrt(num);
}
// can also be written as ... 
// if there is only one func parameter and one liner code
const cubeRoot = num => Math.cbrt(num); // function implicit return 

console.log(cubeRoot(27));
```

## 💄 Execution context(EC)

Everything in javascript code executes inside an execution context. Two phases of EC are Memory Creation Phase and Code Execution Phase.

The first execution context created is the **Global EC(contains MCP & CEP).**

```js
var a = 100; // Global EC
function fun() {
  var y = 99; // Not in Global EC
  console.log('Inside Fun');
  console.log(y);
}

fun();

console.log(a);
```

### 🪘 Global execution context


![[Screenshot 2023-02-26 at 5.29.38 PM.png]]

MCP scans the whole code and **allocates memory for Variables and Functions declared in the program**. Variables will be assigned undefined. For functions, function definition will be saved

After MCP CEP starts its execution. JS engine executes code line by line top to bottom.

Whenever a function is called a new execution context inside the global CEP(or its previous CEP) for that function is created. Again MCP skim out all the variables and functions present inside function and allocate memory for them. Then CEP for that function starts execution.

**Global scope**: anything which is not inside any function body

```js
var b = 100;

function fun() {
  var c = 200;
  function innerFun() {
    console.log(c);
    console.log('Inside  inner fun');
  }
  console.log(b);
  conosle.log('Inner fun');
  
  innerFun();
}

fun();
// Execution flow discussed below
```

#### 🇱🇨 Global Execution Context →

![[Screenshot 2023-02-26 at 5.31.07 PM.png]]

#### EC1 →
![[Screenshot 2023-02-26 at 5.31.20 PM.png]]

Another exec context created when CEP reaches innerFun() line 12 **EC2**

#### EC2 →
![[Screenshot 2023-02-26 at 5.31.40 PM.png]]

All the execution context are maintained as a **call stack in javascript engine**.

>  JS is called single threaded as it uses a single call stack to execute the code.

![[Screenshot 2023-02-26 at 5.33.00 PM.png]]

### Hoisting in Javascript
We’re able to access the var even before declaring it. This is possible due to hoisting
```js
console.log(a);
fun();
var a = 200;
function fun() {
  console.log('Inside fun');
}
```

#### ⛔Hoisting issues
hoisting will not be present for arrow functions and function expressions (variables are created but it is not known as a function until JS engine reaches that line to change it to function from undefined). So we can’t call it like a function. Normal functions are hoisted. See below example

1. 
```js
fun();
var fun = () => {
    console.log('Inner fun');
}
```
![[Pasted image 20230226173414.png | 400]]
For above code, Javascript engine throws the following error

2. 
```js
fun();
const/let fun = () => {
    console.log('Inner fun');
}
```
![[Pasted image 20230226173448.png | 400]]
This is because fun is a normal variable who needs to be initialised before use (because of let and const)
> **Temporal dead zone**. Cannot access a before initialisation

```js
console.log(a);
fun();
let a = 200;
function fun() { console.log('Inside fun'); }`
```

> **Important Article**: [[https://www.freecodecamp.org/news/javascript-let-and-const-hoisting/ | Hoisting in JavaScript with let and const – and How it Differs from var]]
### General Errors

- Reference error
- Type error
- Syntax error