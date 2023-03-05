The `node:assert` module provides a set of assertion functions for verifying invariants.

```js
const assert = require('assert');

function add(a, b) {
	return a + b;
}

assert.deepStrictEqual(add(2, 3), 5);
assert.deepStrictEqual(add(5, 3), 8);
try {
	assert.deepStrictEqual(add(4, 10), -1);
} catch (error) {
console.log("Error. Test Failed");
console.log(error);
}
```

## Strict assertion mode
In strict assertion mode, non-strict methods behave like their corresponding strict methods. For example, [`assert.deepEqual()`](https://nodejs.org/api/assert.html#assertdeepequalactual-expected-message) will behave like [`assert.deepStrictEqual()`](https://nodejs.org/api/assert.html#assertdeepstrictequalactual-expected-message)

## Legacy assertion mode
Legacy assertion mode uses the [`==` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality) in:

-   [`assert.deepEqual()`](https://nodejs.org/api/assert.html#assertdeepequalactual-expected-message)
-   [`assert.equal()`](https://nodejs.org/api/assert.html#assertequalactual-expected-message)
-   [`assert.notDeepEqual()`](https://nodejs.org/api/assert.html#assertnotdeepequalactual-expected-message)
-   [`assert.notEqual()`](https://nodejs.org/api/assert.html#assertnotequalactual-expected-message)

