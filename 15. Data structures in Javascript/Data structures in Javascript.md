## 📊 Arrays in JS
1.  Array is a data structure  
2.  Ordered collection of values (not stored contiguous in memory)
3.  Heterogenous data can be stored

![[Screenshot 2023-02-26 at 5.26.33 PM.png]]

### Array methods

- **Unshift()**: add color in starting
- **Shift()**: removes element from starting and returns that color
- **pop()**: removes element from array end
- **push()**: add elements at array end
- **indexof(element):** return index of given element
- **includes(element):** returns true or false on availability
- **concat():** concatenate arrays in order (order matters)
- **join():** join all elements with the given separator and return strings
- **reverse():** destructive method rchroeversing the original array
- **slice():** slices array according to provided start and/or end index. Also slices with negative index. Always slices in forward direction
- **splice():** deletes and insert new elements. destructive methods
- **split():** split array with separator

#### Array (Behind the scenes)

```js
const movies = ['No time to die', 'Drishyam', 'Orphan', 'Ironman', 'Aquaman'];
const copyMovies = movies; //passed by reference

copyMovies.push('Spiderman', 'Antman'); // copyMovies and movies point to same memory location
> 7
copyMovies
> ['No time to die', 'Drishyam', 'Orphan', 'Ironman', 'Aquaman', 'Spiderman', 'Antman']
movies
> ['No time to die', 'Drishyam', 'Orphan', 'Ironman', 'Aquaman', 'Spiderman', 'Antman']
movies === copyMovies;
> true
```

## Objects in JS

1.  Data structure
2.  Collection of properties
3.  properties are key-value pairs
4.  order is not maintained
5.  pass by reference

```js
const person = {
    name: "Karthik",
    age: 22,
    isAdult: true,
    favColor: ['blue', 'green']
}
const newPerson = person;
newPerson.favSport = "Badminton";

console.log(person);
console.log(newPerson);
```

## Loops in JS
Generic expression of a for loop
```js
for(initialisation; condition; update expression) {

}
```

```js
// 1 for
for (const index = 0; index < [23, 23, 23, 13, 13].length; index++) {

}

// 2 while
while (true) {

}

// 3 do while
do {
} while (true) {

}

// 4 for of
for (const iterator of object) {
// can only be used by those data structures which are iterable
}

// 5 for in
for (const key in object) {
    if (Object.hasOwnProperty.call(object, key)) {
        const element = object[key];

    }
}
```

The for...in statement iterates over the enumerable string properties of an object, while the for...of statement iterates over values that the iterable object defines to be iterated over.

**break and continue in loops**

### Iterators and Generators
String, array, map, set data structures are iterable object. They implement the iteration protocol.