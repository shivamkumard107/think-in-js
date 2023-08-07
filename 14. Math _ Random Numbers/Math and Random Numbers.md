### Math Class
1. `Math.E => 2.7
2. `Math.abs(-100) => 100`
3. `Math.floor(1.2) => 1`
4. `Math.ceil(-11.1) => -12`
5. `Math.pow(3,4)`
6. `Math.sqrt(16) => 4`
7. `Math.cbrt(27) => 3`
8. `Math.max(number, number, number, ...)`
9. `Math.min()`
10. `Math.hypot(3, 4) => 5`

### Random Numbers
Random number between a and b (both inclusive)

`let random = Math.floor(a + Math.random() * (b  + 1 - a))`

### String Tempalte Literals
Allow us to write Multi-line strings, ${some JS}

`console.log(Sum of 2 and is ${2 + 3})`

### Comparison Operators
The result of any comparison expression is always true/false

`2 > 3 `
`<, >, <=, >=`

Equality operator

`==` : Non Strict Equality (perform type coercion only on primitives)
`===` : Strict Equality (does not perform type coercion) 
`!=`
`!==`

### Falsy Values
`"", 0, NaN, null and Undefined. false`

### Logical Operators `(&&, ||, !)`
As soon as final result of a logical expression is known, the execution stops