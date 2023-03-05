```js

const req = new XMLHttpRequest();
const BASE_URL = 'api.github.com/users';
req.onload = function() {
	// get response in this.responseText
	console.log(this);
}

req.onerror = function () {
	console.log(this);
}

req.open('GET', `${BASE_URL}/facebook`);
req.send();

```

Not recommended because of so much boilerplate code and it is based on callback based architecture.