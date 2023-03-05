
## Error Handling Middleware
```js
module.exports = function (callback) {
	return function (req, res, next) {
		callback().catch(next); // promise.catch()
	}
}
```

```js
app.use((err, req, res, next) => {
	const message = err.message || 'Something Went Wrong';
	res.status(500).json({ message: messsag });
	...
})
```