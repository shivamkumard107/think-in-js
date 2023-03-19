## Frontend Validations


## Backend Validations
Joi is a popular validation library for Node.js that makes it easy to validate and sanitize data inputs. Here's how to add backend validations using Joi in a Node.js application:
Joi is a popular validation library for Node.js that makes it easy to validate and sanitize data inputs. Here's how to add backend validations using Joi in a Node.js application:

Install Joi:

`npm install joi`

Create a validation schema using Joi:

```js
const Joi = require('joi');

const userSchema = Joi.object({
  name: Joi.string().required(),
  email: Joi.string().email().required(),
  password: Joi.string().min(6).required(),
  age: Joi.number().integer().min(18).max(100).required()
});
```
In this example, we define a validation schema for a user object with four properties: name, email, password, and age. Each property is validated using a Joi method, such as string() or number(), and chained with other validation rules, such as required() or min().

    Use the schema to validate user input:

javascript

```js
app.post('/register', (req, res) => {
  const { name, email, password, age } = req.body;

  const { error, value } = userSchema.validate({ name, email, password, age });

  if (error) {
    res.status(400).send(error.details[0].message);
  } else {
    // User input is valid, save to database
    saveUserToDatabase(value);
    res.send('User registered successfully!');
  }
});
```

In this example, we use the validate() method of the Joi schema to validate the name, email, password, and age properties of the user input. If there's an error in the input data, we send a 400 Bad Request error message with the details of the error. If the input data is valid, we save it to the database and send a success message.

Note that validate() method returns an object with two properties: error and value. If the input data is invalid, the error property contains the details of the error. If the input data is valid, the value property contains the sanitized input data.

By using Joi to validate and sanitize user input on the server side, you can ensure that your application is more secure and less prone to errors and malicious attacks.

##### Where to add validations in Web? Frontend or Backend.
Both frontend and backend validations are important for a robust and secure web application.

Frontend validations are used to provide immediate feedback to the user when they submit a form or interact with your application. They can help prevent simple mistakes such as missing or incorrect data. Frontend validations are typically implemented using JavaScript and run in the user's browser.

Backend validations are used to ensure that the data received from the frontend is valid, consistent, and secure. They can prevent more complex attacks such as SQL injection and cross-site scripting (XSS) attacks. 

Both frontend backend validations are required:
1. frontend validations can be bypassed by a malicious user, 
2. someone who disables JavaScript in their browser
3. backend api usage via postman or any other api client instead of web

