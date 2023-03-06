## 👓 Event Delegation
Event delegation is a technique in JavaScript that allows you to **attach a single event listener to a parent element** instead of attaching an event listener to multiple child elements. When an event occurs on a child element, the **event "bubbles" up the DOM tree** to the parent element, which can then handle the event.

This is useful when you have a **large number of elements** that need the same event listener attached to them, such as a list of items. Instead of adding the event listener to each individual item in the list, you can add a single event listener to the parent element that contains the list.

##### Example
Event handing pattern caused by event bubbling.
```html
<ul id="my-list">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

```

Instead of attaching a click event listener to each `<li>` element, you can attach a single click event listener to the `<ul>` element:

```js
const myList = document.querySelector('#my-list');

myList.addEventListener('click', function(event) {
  if (event.target.tagName === 'LI') {
    // Handle click on <li> element
  }
});
```

## 🙏 Rate Limiting Techniques
Rate limiting is a technique used to **control the amount of traffic** or requests that can be sent to a server or API within a given time frame. In JavaScript, rate limiting is typically used to **prevent excessive requests** being made to a server or API, which can cause performance issues or even a denial of service (DoS) attack.

### 💪 Throttling
Throttling is used to **limit the rate at which functions are called**.

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

Read for more explanation [[Throttling]]

### 🥹 Debouncing
Debouncing is used to limit the rate at which functions are called by **delaying the execution of the function** until a certain amount of time has passed since the last call

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

Read for more explanation [[Debouncing]]