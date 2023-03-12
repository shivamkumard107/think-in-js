### Mongoose Usage Flow

- We define a schema for our Todo model using Mongoose's `Schema` class
- We specify the properties of our data model and their data types, including a title, completed flag, and createdAt timestamp
- We then create a Mongoose model for our "todos" collection using the `model()` method, and we can use this model to create, read, update, and delete documents in our MongoDB database.

```js
const mongoose = require('mongoose');

// Define a schema for our Todo model
const todoSchema = new mongoose.Schema({
  title: { type: String, required: true },
  completed: { type: Boolean, default: false },
  createdAt: { type: Date, default: Date.now },
});

// Create a Mongoose model for our Todo collection
const Todo = mongoose.model('Todo', todoSchema);

// Create a new todo item and save it to the database
const todo = new Todo({
  title: 'Buy groceries',
  completed: false,
});
todo.save((err, savedTodo) => {
  if (err) {
    console.error(err);
  } else {
    console.log(savedTodo);
  }
});

// Query the database for all todos
Todo.find((err, todos) => {
  if (err) {
    console.error(err);
  } else {
    console.log(todos);
  }
});

// Query the database for a specific todo
Todo.findOne({ title: 'Buy groceries' }, (err, todo) => {
  if (err) {
    console.error(err);
  } else {
    console.log(todo);
  }
});

// Update a todo in the database
Todo.updateOne({ title: 'Buy groceries' }, { completed: true }, (err, result) => {
  if (err) {
    console.error(err);
  } else {
    console.log(result);
  }
});

// Delete a todo from the database
Todo.deleteOne({ title: 'Buy groceries' }, (err) => {
  if (err) {
    console.error(err);
  } else {
    console.log('Todo deleted');
  }
});

```