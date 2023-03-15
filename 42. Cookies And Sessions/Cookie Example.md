## Cookie Example

```js
const express = require('express');
const cookieParser = require('cookie-parser');

const app = express();

app.use(cookieParser());

// Route to set a cookie
app.get('/set-cookie', (req, res) => {
  res.cookie('myCookie', 'Hello World!', { maxAge: 900000, httpOnly: true });
  res.send('Cookie has been set');
});

// Route to retrieve the cookie value
app.get('/get-cookie', (req, res) => {
  const cookieValue = req.cookies.myCookie;
  res.send(`The value of myCookie is: ${cookieValue}`);
});

// Start the server
app.listen(3000, () => {
  console.log('Server listening on port 3000');
});
```

## Signed Cookie Example

```js
const express = require('express');
const cookieParser = require('cookie-parser');

const app = express();

app.use(cookieParser('mySecret'));

// Route to set a signed cookie
app.get('/set-cookie', (req, res) => {
  res.cookie('myCookie', 'Hello World!', { signed: true });
  res.send('Cookie has been set');
});

// Route to retrieve the signed cookie value
app.get('/get-cookie', (req, res) => {
  const cookieValue = req.signedCookies.myCookie;
  res.send(`The value of myCookie is: ${cookieValue}`);
});

// Start the server
app.listen(3000, () => {
  console.log('Server listening on port 3000');
});

```

To retrieve the value of a signed cookie, we use `req.signedCookies` instead of `req.cookies`. The `signedCookies` object is automatically populated with the signed cookies, and the values are verified using the secret specified in the `cookie-parser` middleware