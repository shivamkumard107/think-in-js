```js
const bcrypt = require('bcrypt');
const saltRounds = 10;

// Hashing a password using bcrypt
bcrypt.hash('myPassword', saltRounds, function(err, hash) {
  if (err) {
    console.error(err);
  } else {
    console.log(hash);
    // Store hash in your password database.
  }
});

// Comparing a password with its hash using bcrypt
const myPassword = 'myPassword';
const hash = '$2b$10$XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX'; // Example hash
bcrypt.compare(myPassword, hash, function(err, result) {
  if (err) {
    console.error(err);
  } else {
    console.log(result); // true or false
  }
});
```
In this example, we first require the bcrypt module and set the number of salt rounds to 10.

Then, we use the `bcrypt.hash()` method to hash a password. This method takes three parameters: the password to be hashed, the number of salt rounds to use, and a callback function that takes an error (if there is one) and the resulting hash.

Next, we use the `bcrypt.compare()` method to compare a password with its hash. This method takes three parameters: the password to be compared, the hash to be compared against, and a callback function that takes an error (if there is one) and the resulting boolean value indicating whether the password matches the hash.