| **HTTP**                                        | **Web Socket**               |
| ----------------------------------------------- | ---------------------------- |
| Unidirectional communication / half duplex      | Bi-directional / full duplex |
| Data is transmitted in form of Text, HTML, JSON | Binary Data                  |

```js
const express = require('express')
const app = express();
const http = require('http');
const server = http.createServer(app);
const path = require('path');
const { Server } = require('socket.io')
const io = new Server(server);

app.use('/', express.static(path.join(__dirname, 'public')))

io.on('connection', (socket) => {
	console.log('connection established client with id ${socket.id}')
});

server.listen(3000, () => {
	console.log('connection establised at port 3000')
})
```



```js
socket.on('eventName', callback);
```

```js
socket.emit('eventName', data);
```

```js
io.emit('event', data); // sends to all io connections
```

```js
socket.broadcast('event')
```