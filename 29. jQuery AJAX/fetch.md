```js
const BASE_URL = 'http://api.github.com/users';

fetch(`${BASE_URL}/facebook`)
	.then((res) => {
		if(res.status === 200) {
			// successful
		}
		console.log(res)
	}).catch((error) => {
		console.log(error)
	});
```

Read More: [[HTTP Response Code & Status]]
