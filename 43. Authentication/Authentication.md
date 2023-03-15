Authentication is the process of **verifying the identity** of a user, device, or system. This is typically achieved by requiring the user to provide credentials, such as a username and password, that can be verified against a database of authorized users. The purpose of authentication is to ensure that only legitimate users are granted access to protected resources.
1. Password
2. Biometric
	1. fingerprint
	2. voice
	3. face recognition
3. Token based (JWT)

### How do we store the password?
Storing passwords securely is a critical aspect of web security, as passwords are often the primary means of authenticating users. Passwords should **never be stored in plain text**, as this would allow anyone with access to the password database to view the passwords and use them to access user accounts.

The most common approach for storing passwords securely is to use a technique called **password hashing**. Password hashing involves taking the user's password and running it through a one-way cryptographic function, such as bcrypt, scrypt, or Argon2, to generate a fixed-length string of random-looking characters, known as a hash. The hash is then stored in the password database, rather than the plaintext password

When a user attempts to log in, their entered password is hashed using the same cryptographic function and the resulting hash is compared to the hash stored in the database. If the two hashes match, the user is authenticated

This approach has several benefits:

1.  Passwords are not stored in plain text
2. reverse-engineer the hash to password is not possible
3. Salt can be added to the password hash, which adds an additional layer of security. A salt is a random string that is added to the password before hashing

#### [[Authentication Example |Example]]
