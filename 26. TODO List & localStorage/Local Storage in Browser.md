A way to store data on client side browsers.

```js
// Check if local storage is supported
if (typeof(Storage) !== "undefined") {
  // Store a value in local storage
  localStorage.setItem("background-color", "lightblue");
  
  // Retrieve a value from local storage
  var bgColor = localStorage.getItem("background-color");
  
  // Use the value to set the background color of an element
  document.body.style.backgroundColor = bgColor;
} else {
  // Local storage not supported
  console.log("Local storage is not supported by this browser.");
}
```

In this example, we first check if the browser supports local storage. If it does, we use the `localStorage.setItem()` method to store a value ("lightblue") with the key "background-color". Later, we retrieve this value using `localStorage.getItem()` and use it to set the background color of the `body` element. If local storage is not supported, we log a message to the console.