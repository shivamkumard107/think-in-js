
## app.set express
The **app.set() function** is used to assigns the setting name to value. You may store any value that you want, but certain names can be used to configure the behavior of the server.

**Syntax:**
```js
app.set(name, value)
```

```js
var express = require('express');
var app = express();
var PORT = 3000;
  
app.set('title', 'GeeksforGeeks');
  
app.get('/', (req, res) => {
  res.send(app.get('title'));
})
  
app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
}); 
```


## app.use() express
The `app.use()` function is used **to mount middleware functions** at a specified path, which means that the middleware will be executed for every HTTP request that matches that path. This method is used to set up middleware functions that will be used throughout your application, such as middleware that logs requests, serves static files, or handles error messages. `app.use()` can also be used to mount router middleware.


## app.get express
The `app.get()` function, on the other hand, is used to **define a route for a GET request**. It takes two arguments: the route path and the callback function to be executed when that route is accessed with a GET request. The callback function will typically render a view or return JSON data to the client.


#### Differences app.use & app.get
In summary, `app.use()` is used to mount middleware at a specified path, while `app.get()` is used to define a route for a GET request.

#### Examples
##### app.use
```js
// Middleware function that logs requests to the console
const logger = (req, res, next) => {
  console.log(`${req.method} request for ${req.url}`);
  next();
};

// Mount the logger middleware at the root path
app.use(logger);

// Mount a router middleware at the '/users' path
const usersRouter = require('./routes/users');
app.use('/users', usersRouter);

```

##### app.get
```js
// Define a route for the root path that renders a view
app.get('/', (req, res) => {
  res.render('home');
});

// Define a route for the '/users' path that returns JSON data
app.get('/users', (req, res) => {
  const users = [
    { id: 1, name: 'Alice' },
    { id: 2, name: 'Bob' },
    { id: 3, name: 'Charlie' }
  ];
  res.json(users);
});

```