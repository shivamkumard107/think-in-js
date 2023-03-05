The `process` object provides information about, and control over, the current Node.js process. 
```js
const process = require('node:process');

process.release
/*
{
  name: 'node',
  lts: 'Hydrogen',
  sourceUrl: 'https://nodejs.org/download/release/v18.12.1/node-v18.12.1.tar.gz',
  headersUrl: 'https://nodejs.org/download/release/v18.12.1/node-v18.12.1-headers.tar.gz'
}
*/
process.argv
// [ '/usr/local/bin/node' ]
process.cwd()
// '/Users/shivamkumar/Documents/WebD/SelfWork/Practice'