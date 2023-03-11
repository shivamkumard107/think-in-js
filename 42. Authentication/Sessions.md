Sessions are a way to **store user data** across multiple HTTP requests. A session typically consists of a **unique session ID** that is stored in a cookie or as a URL parameter, and a **server-side data** store where the session data is kept.

### Use case
When a user visits a website, a new session can be created and associated with that user. The session ID is typically stored in a cookie or as a URL parameter, and is sent back to the server with each subsequent request. The server then uses the session ID to retrieve the user's session data from the session store, and can update or read the session data as needed.

Sessions are commonly used to store user authentication and authorization data, such as user IDs, roles, and permissions. They can also be used to store user-specific settings, preferences, and other data.

In Node.js, sessions are typically implemented using middleware such as **`express-session`** or **`cookie-session`**. These middleware modules handle the creation and management of sessions, and provide APIs for storing and retrieving session data.

#### Example
```js
const express = require('express');
const session = require('express-session');

const app = express();

app.use(session({
  secret: 'mySecret',
  resave: false,
  saveUninitialized: true,
  cookie: { secure: false }
}));

// Route to set a session variable
app.get('/set-session', (req, res) => {
  req.session.myVariable = 'Hello World!';
  res.send('Session variable has been set');
});

// Route to retrieve the session variable
app.get('/get-session', (req, res) => {
  const sessionValue = req.session.myVariable;
  res.send(`The value of myVariable is: ${sessionValue}`);
});

// Start the server
app.listen(3000, () => {
  console.log('Server listening on port 3000');
});

```

In the example above, we've added the `express-session` middleware to our application. We've configured it with a `secret` string, which is used to sign the session ID cookie, and set `resave` and `saveUninitialized` to their default values

To set a session variable, we simply assign a value to `req.session.myVariable`. The `myVariable` property is automatically added to the user's session data, and can be accessed on subsequent requests

To retrieve a session variable, we use `req.session.myVariable`. The value is automatically retrieved from the session data, and can be used in the response.

Note that the `express-session` middleware automatically creates a new session and associated session ID for each new user that visits the site. The session ID is typically stored in a cookie, which is sent back to the server with each subsequent request. The session data is stored on the server, and is associated with the session ID.