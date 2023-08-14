### Project Setup
1. HTML
2. CSS
3. JS
4. Bootstrap
5. EJS
6. NodeJs
7. Express
8. MongoDB
9. Mongoose
### Dev Tools
1. **Babel** -> Compiler for JS, For Latest JS features, import and export class
### Initial Project Setup Steps
1. initialise repository `npm init`
2. install required packages 
		`npm i express ejs mongoose`
3. nodejs babel setup in project. *-D* flag for dev dependency
		`npm i -D @babel/core @babel/preset-env @babel/node @babel/cli`
4. babel configuration for our project
		`touch .babelrc` 
5. make a source and test directory for source code and test code
		`mkdir src test`
6. Creating `app.js` and `server.js` 
7. In `app.js` create and export express app, in `server.js`  create endpoints and start the server 

### Scripts
```json
"scripts": {
	"build": "babel ./src --out-dir ./build",
	"start": "node build/server.js",
	"dev":"nodemon --exec babel-node src/server.js",
	"test": "echo \"Error: no test specified\" && exit 1"
}
```

### Different Project Environments
1. local env
2. sbox env
3. staging
4. preprod
5. prod
### Create database config
1. `database.js` contains different configurations related to different project environment
2. `index.js` contains the basic connect and disconnect database
### Project Layered Architecture

## Build an HLD

###### PS: Read about export and default export of app