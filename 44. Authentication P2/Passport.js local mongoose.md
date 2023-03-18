Mongoose plugin: [passport-local-mongoose](https://www.npmjs.com/package/passport-local-mongoose)

Passport-local-mongoose is a Node.js package that **simplifies the process of creating a user authentication system with Passport.js and Mongoose**. Passport.js is a popular authentication middleware for Node.js that provides a flexible way to authenticate users using a **variety of authentication strategies**. 

Passport-local-mongoose combines the functionality of Passport.js and Mongoose to provide a simple way to **create a local authentication strategy**, where users are authenticated using a username and password stored in a MongoDB database.

It provides a
1. Pre-defined Mongoose schema for user authentication and password management,
2. Set of Passport.js strategies for authentication, session management, and user serialization and deserialization.

Using passport-local-mongoose, you can quickly set up a user authentication system in your Node.js application without having to write a lot of code. 
It also includes features like 
- Password hashing 
- Salting
- Account locking 
- Unlocking
- Password reset functionality


1. User modal. add passport local plugin in modal. Create and export modal
2. 