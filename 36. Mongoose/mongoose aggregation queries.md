> TODO Read docs and document notes here. Build 2-3 sample aggregation queries

```js
const result =  await Order.aggregate([
        {
            $group: {
                _id: "$size",
                pizzaSize: { "$first" : "$size"},
                totalQuantity: {
                    $sum: "$qty"
                }
            }
        },
        {
            $sort: {
                totalQuantity:-1
            }
        }
    ]
    )
```