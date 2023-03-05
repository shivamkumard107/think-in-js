> this → it always points to an object (or undefined)

```js
function fun() {
  // prints window
  console.log(this);
}
```

### 🪟 Window object

**It represents the browser's window**. All global JavaScript objects, functions, and variables automatically become members of the window object. Global variables are properties of the window object. Global functions are methods of the window object.

### 🕣 this binding

#### 1.  Implicit binding

```js
const person = {
		name: "Kartik",
		age: 22,
		isAdult: true,
		favColor: ['Sky Blue', 'Purple']
		sayHello: function() {
		  console.log(this); // implicit binding
		  console.log(`Hello from ${this.name}`); // implicit binding
		}
	}
        
// called from the object, this in sayHello will point to person object
person.sayHello(); 

const greet = person.sayHello;
// if called from here, sayHello will point to Window object
greet(); 
```

#### 2.  Explicit binding
```js
function person(name, age) {
    console.log(name, age, this);
}
        
const obj = {
            l: 10,
            m: true
}
        
person("Kartik", 24);
        
const f = person.bind(obj);
        
f("Vivek", 23);
        
// do the same binding of this keyword with the specified obj (like bind)
person.call(obj, "Karthik", 24);
        
        
const person2 = {
	name: "Kartik",
	age: 22,
	isAdult: true,
	favColor: ['Sky Blue', 'Purple'],
	sayHello : function() {
	  console.log(this); // implicit binding
	  console.log(`Hello from ${this.name}`); // implicit binding
	}
}
        
// called from the object, this in sayHello will point to person object
person2.sayHello(); 

const greet0 = person2.sayHello;
// if called from here, sayHello will point to Window object
greet0();

const greet = person2.sayHello.bind(person2);
greet();

```

```js
function Product(name, price) {
	this.name = name;
	this.price = price;
	console.log(this);
}
        
function Food(name, price) {
  Product.call(this, name, price);
  this.category = 'food';
}
const cheese = new Food('Pizza', 5);
const paneer = new Product('Tomato', 100);
console.log(cheese);
console.log(paneer);
```
        
##### Output:
![[Pasted image 20230226174911.png]]
^ 'this' in Product binds to different obj at different time

#### 3.  new Keyword
```js
function Food(name, price) {
  // this points to the 'cheese' object created from Food constructor
	this.name = name;
	this.price = price;
	this.category = "Food";
}

let cheese = new Food("Pizza", 2);

console.log(cheese);
```   
4.  default
	1.  Window object

> Not recommended to use this keyword in arrow functions. It will implicitly points to Window object

```js
const car = {
  name: 'BMW',
  price: 23,
  startCar: () => {
    // points to window object
    console.log(this);
    console.log(this.name);
  }
}
```