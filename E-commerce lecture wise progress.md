The list below gives an overview of the e-commerce project with respect to the packages & architecture used during its development. Does not target feature development process.

### Lecture 38
- Project setup using NodeJs, Express
- Used **babelrc** for compiling JS
- High Level Design
- **Layered** Vs **MVC** architecture (Theory and Demo)

### Lecture 39
- Implemented **layered architecture**
- Setup view engine **ejs**
- Build some generic core classes 
	- ApiError(custom error middleware to catch errors)
	- catchAsync
	- logger
	- statusCode
- Used **winston** for logging
- Started on Product route

### Lecture 40
- added **ejs-mate** to reuse boilerplate code in ejs tempalate
- added **method-override** to use HTTP verbs such as PUT or DELETE in places where the client doesn't support it
- Built **Product routes**

### Lecture 41
- **Mongo relationship**: Embedded Vs Referential(Theory and Demo)
- Implemented Review routes. Setup relationship with Product route

### Lecture 42
- Browser storage options. Client-side, indexDB, CacheAPI
- **cookie-parser** to use cookies in project
- **express-sessions** to maintain user sessions
- **connect-flash** to flash messages for performing any user action

### Lecture 43
- auth demo
- **bcrypt** for hashing password

### Lecture 44
- Authentication implementation in project
- **passport.js**
- **passport-local**
- **passport-local-mongoose**
- Setup user authentication using passport js
- `User` routes for login, register, logout

### Lecture 45
- Form validations implementation using **joi**
- Product & user validator middleware

### Lecture 46
- **dotenv** for environment variable setup according to testing, development & production environment 
- `isProductAuthor` middleware added
- Database deployment to **mongodb atlas**
- Deploy website to **Heroku**