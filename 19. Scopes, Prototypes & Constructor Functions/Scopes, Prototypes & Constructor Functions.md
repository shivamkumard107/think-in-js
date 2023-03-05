### Types of scopes
1.  Global Scope
2.  Functional Scope
3. Script Scope
4. Block Scope

```js
// In Global scope
var name = "Sarah";

// In Global scope
function getName() {
  console.log(name);
}

console.log(name);

getName();
```

When an Execution context is created, a reference to its lexical parent is also kept in its MCP

### var is function or global scoped

```js
var a = 100;
function fun() {
  var a = 200; // new variable a will be created which have this functional scope
  console.log(a);
}
console.log(a);
fun();
```

```js
var c = 300;
if(true) {
  var c = 500;// new variable won't be created, c will be updated which is in global scope
  console.log(c); 
}

console.log(c);
```

### let and const are block or script scoped
Global > Script > Block scope

```js
let a = 900;
{
  let a = 800;
  console.log(a);
}
console.log(a);
```

script and block scope

### Scope chain

```js
var name = "Sarah";
function getName() {
    var name = "Another Name";
    console.log(name);
    fun();
}
function fun() {
    console.log(name);
}

getName();
```
fun is physically present in the global scope so it will use the ‘name’ of the global scope.

## 📽️ Prototypes
__proto__ : Dunder proto (double underscore prototyp)
Prototypes chaining of Object
Dunder Prototype example

### ⚱️ Constructor Functions
First function get called when a class is instantiated

### 🫙 Classes in JS
1.  getters and setters can be specified with a get and set keyword
2.  getters/setters functions of an object are called like a property. point.getX and not point.getX()
3.  Any operation performed on multiple objects can be written as static function
4.  functions in a class don’t use function keyword. Just specify the function name

```js
class Point {
    constructor(x, y) {
        this.x = x;
        this.y = y;
    }   
    get getX() {
        return this.x;
    }

    get getY() {
        return this.y;
    }

    set setX(newX) {
        this.x = newX;
    }

    set setY(newY) {
        this.y = newY;
    }

    static distance(p1, p2) {
        return Math.hypot(p1.x - p2.x, p1.y - p2.y);
    }

    static slope(p1, p2) { 
        return (p2.y - p1.y) / (p2.x - p1.x);
    }

    static centroid(p1, p2, p3) {
        return new Point((p1.x + p2.x + p3.x) / 3, (p1.y + p2.y + p3.y) / 3);
    }
}

let p1 = new Point(1, 2);

let p2 = new Point(3, 5);

let p3 = new Point(0, 0);

console.log(Point.distance(p1, p2));
console.log(Point.slope(p1, p2));

let centroid = Point.centroid(p1, p2, p3);
console.log(centroid.getX, centroid.getY);
```