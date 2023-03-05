## 👓 Event Delegation

Event handing pattern caused by event bubbling.

```js
const buttons = document.querySelectorAll(' section button');
// Lot of events added which consumes memory
for (const bt of buttons) {
    bt.addEventListener('click', (event) => {
        console.log(bt.innerHTML);
    })
}
// Event delegation
const section = document.querySelector('section');

section.addEventListener('click', (event) => {
    console.log(event.target.innerHTML);
})
```

## 🙏 Rate Limiting Techniques

### 💪 Throttling

```js
const searchInp = document.getElementById('searchInp');
let count = 0
function fetchAllMatchedProduct() {
    console.log('api call', count++);
}

function createThrottle(func, delay) {
    let start = 0;
    return function () {
        const current = new Date().getTime();
        if(current - start > delay) {
            func();
            start = current;
        }
    }
}
const throttleFunc = createThrottle(fetchAllMatchedProduct, 500);

searchInp.addEventListener('keypress', throttleFunc);
```

### 🥹 Debouncing

```js
const searchInp = document.getElementById('searchInp');
let count = 0
function fetchAllMatchedProduct() {
    console.log('api call', count++);
}

function createDebounce(func, delay) {
    let timer;
    return function () {
        clearTimeout(timer);
        timer = setTimeout(() => { 
            func();
         }, delay);
    }
}

const debounce = createDebounce(fetchAllMatchedProduct, 200);

searchInp.addEventListener('keypress', debounce);
```