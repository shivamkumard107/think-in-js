### 🐄 Spread Operator

```js
const arr1 = [1, 2, 4];
const arr = [...arr1, 8, 9, 10, 70];

console.log(arr);
console.log(Math.max(...arr));

const car = {
  name: "BMW",
  price: 100
}

const racingCar = {
  ...car,
  topSpeed: 200,
  color: 'black'
}
console.log(racingCar);
```

### 😌 Rest Parameter (should be at last of the parameter list)

```js
function add(a, b, ...nums) {
  return a + b + nums.reduce((sum, num) => sum + num, 0);
}
console.log(add(2, 3));
```

### 🤱 Destructuring

```js
const colors = ['blue', 'orange', 'purple', 'lightgreen', 'brown'];

const [firstColor, secondColor] = colors;

// similar to
// const firstColor = colors[0];
// const lastColor = colors[1];
```

```js
const person = {
  age: 23,
  lastName: 'Doe',
  firstName: 'John'
}

const { firstName:myFirstName = "Default Val", lastName } = person;
// also can change the variable name
console.log(myFirstName);
```

### 🚧 Polyfills

-   Take the array
-   Write your own function (myFilter, mapArr, ...)
-   Extract out the logic part from the function and pass it as a callback into your function
-   Set the function as a prototype of that Array
-   Remove the array passed as a parameter and use 'this' keyword to access each object

```js
const arr = [1, 2, 4, 5, 12, 5, 10, 6];

const logic = (e) => {
    if (e === 1212) {
      return true;
    }
}

Array.prototype.findArr = function(logic){
  for (const a of this) {
    if (logic(a)) {
      return a;
    }
  }
  return null;
}

// console.log(findArr(1, arr, logic));

console.log(arr.findArr((e) => e === 4));


const logic = e => {
  if (e === 122) {
    return true;
  }
  return false;
}

Array.prototype.someArr = function (logic) {
  for (const num of this) {
    if(logic(num)) {
      return true;
    }
  }
  return false;
}

console.log(arr.someArr(logic));
```