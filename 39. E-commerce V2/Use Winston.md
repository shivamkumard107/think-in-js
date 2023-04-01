First, install Winston using npm:

```bash
npm install winston
```

Then, create a file named `logger.js` and add the following code:

```js
const winston = require('winston');

const logger = winston.createLogger({
  level: 'info',
  format: winston.format.combine(
    winston.format.timestamp(),
    winston.format.json()
  ),
  transports: [
    new winston.transports.Console(),
    new winston.transports.File({ filename: 'logs/error.log', level: 'error' }),
    new winston.transports.File({ filename: 'logs/combined.log' })
  ]
});
module.exports = logger;
```

In this code, we're creating a Winston logger instance with three transports:

1. Console: outputs logs to the console
2. File with filename: 'logs/error.log': writes logs with level: 'error' to a file named error.log in the logs directory
3. File with filename: 'logs/combined.log': writes all logs to a file named combined.log in the logs directory

You can customize these transports to suit your needs.

Then, in your main Node.js file, you can import this logger and use it to log messages like this:

```js
const logger = require('./logger');

logger.info('This is an info message');
logger.warn('This is a warning message');
logger.error('This is an error message');
```

This will log messages to both the console and the specified files. You can also use other log levels like debug and verbose.


Note: [[Error Handling and Logging#Use Morgan |Morgan]] is focused on logging HTTP requests and is simpler and easier to use, while Winston is a more comprehensive logging library with greater flexibility and customization options for logging a wider range of events and messages in your Node.js application.
