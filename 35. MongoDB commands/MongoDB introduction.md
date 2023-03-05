> Database > Collections (Tables) > Documents (Single Entries)

Data is automatically indexed in Mongo. [[Indexing]]  is a data structure technique which allows you to quickly retrieve records from a database file.

## CRUD operations

> Generic command type is like db.collections.query

```mongodb
db.orders.find({}).count()

db.orders.find({name: 'Margerita'})

db.orders.find({size: 'medium', name: 'Margerita'})

db.orders.updateMany({name: 'Farm House'}, {$set: {price: 500}})

db.orders.deleMany()
```

## Query Selectors
mongo store data in BSON format and represent it in JSON format. 

>Read [Json Vs BSON](https://www.mongodb.com/json-and-bson) for more info

```mongodb
db.orders.find({qty: {$gte: 5}})

db.orders.find({name: {$eq: 'Margerita'}})

db.orders.find({price: {$in: [100, 200, 500]}})

```

[Query and Projection Operators](https://www.mongodb.com/docs/manual/reference/operator/query/)

## Aggregation pipeline

```mongodb
db.orders.aggregate([
	{
		$match: {size: "medium"}
	},
	{
		$group: {_id: "$name", totalQuantity: {$sum: "$qty"}}
	}
])

db.orders.aggregate([
	{
		$group: {_id: "$size"}, 
		totalPrice: {
			$sum: {
				$multiply :["$price", "$qty"]
				}
			}
		}
	}
])
```

[[Object Document Mapper]] is layer between express and mongoDb document to convert from json to document and vice versa. We use **mongoose** for this purpose. 

## Mongoose
```js
const mongoose = require('mongoose');

mongoose.connect('mongodb://localhost:27017/pizzaDB')
	.then(() => console.log("connection open"))
	.catch((err) => console.log(err))

const orderSchema = new mongoose.Schema({
		name: String,
		price: Number,
		size: String,
		qty: Number
});

const Order = mongoose.model('Order', orderSchema);
const order = new Order(name: "", size: "", price: 250, qty: 5)


```

