Sending an error response to the client with express can be done as

```js
app.get('/home', (req, res) => {
    try {
        const val = Math.floor(Math.random() * 100000);
        if (val % 3 === 0) {
            throw new Error('divisble by 3');
        }
        return res.status(200).send('Everything is okay!')
    }
    catch (err) {
	    // thrown error will be cached here
        return res.status(400).send(`Value : ${err.message}`);
    }
});
```

### Use Morgan
HTTP request logger middleware for node.js

```bash
npm i morgan
```

`var morgan = require('morgan')`

#### Usage
Create a new morgan logger middleware function using the given `format` and `options`. The `format` argument may be a string of a predefined name (see below for the names), a string of a format string, or a function that will produce a log entry.

Format
- combined
- common
- dev

Options
- Immediate
- skip
- stream

Also read: [[Use Winston]]

