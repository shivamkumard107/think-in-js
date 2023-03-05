Useful for 
- High throughput requirement
	- Chatting apps
	- Social media apps
	- E-commerse
[[Don't use node for this]]



```js
const express = require('express');

const app = express();  

// app.use((req, res) => {
//     console.log("We got a request");
// })

app.get('/dog', (req, res) => {
	res.send("The feature notifier is distributed across all systems.");
});

app.listen(3000, () => {

console.log("Server is up and running...");

});
```