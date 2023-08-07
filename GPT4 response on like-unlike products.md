
```
I'm building an e commerce website using NodeJs, Mongoose, Express where
there are list of products inside mongodb collection. I'm using mongoose 
as an ODM. I want to build a feature where user can like & unlike a 
product so that I can show user his list of liked products. on the 
product page. Can you do this?
```

Of course! To implement a "like/unlike" feature for products on your e-commerce website using Node.js, Mongoose, and Express, you'll need to modify the database schema, create appropriate routes, and handle the user interactions. Here's a step-by-step guide to help you achieve this:

1.  Modify the User and Product Schemas: First, update your User and Product schemas to include an array of product references that represent the user's liked products, and an array of user references for users who liked the product.

In your `models/User.js`:

```js
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

const UserSchema = new Schema({
  // ... other user properties
  likedProducts: [{
    type: Schema.Types.ObjectId,
    ref: 'Product'
  }],
});

module.exports = mongoose.model('User', UserSchema);

```

In your `models/Product.js`:

```js
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

const ProductSchema = new Schema({
  // ... other product properties
  usersLiked: [{
    type: Schema.Types.ObjectId,
    ref: 'User'
  }],
});

module.exports = mongoose.model('Product', ProductSchema);

```
2.  Create routes for liking and unliking products: In your `routes/products.js`:

```js
const express = require('express');
const router = express.Router();
const Product = require('../models/Product');
const User = require('../models/User');

// Like a product
router.post('/:productId/like', async (req, res) => {
  try {
    const user = await User.findById(req.user._id); // assuming req.user contains the authenticated user
    const product = await Product.findById(req.params.productId);

    if (!user || !product) {
      return res.status(404).send('User or product not found');
    }

    // Add the product to the user's liked products
    user.likedProducts.addToSet(product._id);
    await user.save();

    // Add the user to the product's usersLiked
    product.usersLiked.addToSet(user._id);
    await product.save();

    res.status(200).send('Product liked');
  } catch (error) {
    res.status(500).send('Error liking the product');
  }
});

// Unlike a product
router.post('/:productId/unlike', async (req, res) => {
  try {
    const user = await User.findById(req.user._id);
    const product = await Product.findById(req.params.productId);

    if (!user || !product) {
      return res.status(404).send('User or product not found');
    }

    // Remove the product from the user's liked products
    user.likedProducts.pull(product._id);
    await user.save();

    // Remove the user from the product's usersLiked
    product.usersLiked.pull(user._id);
    await product.save();

    res.status(200).send('Product unliked');
  } catch (error) {
    res.status(500).send('Error unliking the product');
  }
});

module.exports = router;

```

3.  Handle user interactions on the front-end: Now, on your front-end, you need to make AJAX requests to the like and unlike endpoints when the user clicks the like or unlike button for a product. You can use JavaScript libraries like Axios or jQuery AJAX to make these requests.

Remember to update the UI accordingly when a product is liked or unliked, such as changing the button's text or icon.

4.  Show the user's list of liked products: To display the user's liked products, fetch the user's `likedProducts` array from the database, and then populate the product details using Mongoose's.

```
I don't want to change the product schema. Can you do it by changing the 
user schema only?
```

Sure, you can implement the like/unlike feature by only modifying the User schema. In this case, you'll only store the list of liked products in the User schema and won't track which users have liked a product in the Product schema.

1.  Modify the User Schema: Update your User schema to include an array of product references that represent the user's liked products.

In your `models/User.js`:

```js
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

const UserSchema = new Schema({
  // ... other user properties
  likedProducts: [{
    type: Schema.Types.ObjectId,
    ref: 'Product'
  }],
});

module.exports = mongoose.model('User', UserSchema);

```

2.  Create routes for liking and unliking products: In your `routes/products.js`:

```js
const express = require('express');
const router = express.Router();
const Product = require('../models/Product');
const User = require('../models/User');

// Like a product
router.post('/:productId/like', async (req, res) => {
  try {
    const user = await User.findById(req.user._id); // assuming req.user contains the authenticated user
    const product = await Product.findById(req.params.productId);

    if (!user || !product) {
      return res.status(404).send('User or product not found');
    }

    // Add the product to the user's liked products
    user.likedProducts.addToSet(product._id);
    await user.save();

    res.status(200).send('Product liked');
  } catch (error) {
    res.status(500).send('Error liking the product');
  }
});

// Unlike a product
router.post('/:productId/unlike', async (req, res) => {
  try {
    const user = await User.findById(req.user._id);
    const product = await Product.findById(req.params.productId);

    if (!user || !product) {
      return res.status(404).send('User or product not found');
    }

    // Remove the product from the user's liked products
    user.likedProducts.pull(product._id);
    await user.save();

    res.status(200).send('Product unliked');
  } catch (error) {
    res.status(500).send('Error unliking the product');
  }
});

module.exports = router;

```

3.  Handle user interactions on the front-end: Just as mentioned in the previous response, make AJAX requests to the like and unlike endpoints when the user clicks the like or unlike button for a product, and update the UI accordingly.
    
4.  Show the user's list of liked products: To display the user's liked products, fetch the user's `likedProducts` array from the database and populate the product details using Mongoose's `populate()` method:
    

```js
router.get('/liked-products', async (req, res) => {
  try {
    const user = await User.findById(req.user._id).populate('likedProducts');
    res.status(200).json(user.likedProducts);
  } catch (error) {
    res.status(500).send('Error fetching liked products');
  }
});

```

Now you can use this `/liked-products` endpoint to fetch and display the list of liked products for the user on the front-end.

```
How does the populate method fetch all the product details if you're not 
using the Product schema anywhere?
```

My apologies for any confusion. You're right that it's essential to explain how the `populate()` method works.

Mongoose's `populate()` method is used to fetch referenced documents in another collection by replacing the specified reference field with the actual document from the referenced collection. In this case, we have a reference field in the User schema called `likedProducts` containing an array of ObjectIds that refer to documents in the Product collection.

When you use `populate('likedProducts')` on a User query, Mongoose will fetch the Product documents corresponding to the ObjectIds in the `likedProducts` array and replace the array elements with the actual documents. This process essentially "joins" the data from the two collections, even though the Product schema is not explicitly imported in the routes file.

When you define the reference in the User schema using `ref: 'Product'`, you're telling Mongoose which collection the ObjectId references belong to:

```js
likedProducts: [{
  type: Schema.Types.ObjectId,
  ref: 'Product'
}],
```

This `ref: 'Product'` is the link that allows the `populate()` method to find and fetch the related Product documents based on the ObjectIds stored in the User document's `likedProducts` array. The 'Product' in the `ref` should match the name you use when creating the model from the schema:

```js
module.exports = mongoose.model('Product', ProductSchema);
```

So, although we don't explicitly import the Product schema in the routes file, the relationship between the User and Product schemas is established through the `ref` property. This relationship allows Mongoose to fetch the Product documents when you call `populate()`.