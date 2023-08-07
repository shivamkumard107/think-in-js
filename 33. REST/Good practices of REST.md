#### Following an architecture 
helps understand code better (Layered Architecture, MVC architecture)

#### Versioning 
is important (v1/routes, v2/routes) for better testing new features without disturbing current user base

#### API end points should be plural 
(v1/products, api/v2/reviews). Naming your resource in plural helps clear that it is a collection of different products or reviews

#### No Verbs 
are required like getAllProducts or createUser. HTTP verb itself already indicates the action.

#### Accept and respond with data in JSON format


#### Respond with standard HTTP Error Codes
and Error Messages. Messages need not to be so specific that it reveals internal data to the user. For Example: *The username is already signed up*. A good error message is *One of the following keys is missing or is empty in request body: 'name', 'mode', 'equipment', 'exercises', 'trainerTips'*

> Following topics to be read

#### Group associated resources together (logical nesting)

#### Integrate filtering, sorting & pagination

#### Use data caching for performance improvements

#### Good security practices

#### Document your API properly

Reference: [REST API Design Best Practices Handbook – How to Build a REST API with JavaScript, Node.js, and Express.js
](https://www.freecodecamp.org/news/rest-api-design-best-practices-build-a-rest-api/)
