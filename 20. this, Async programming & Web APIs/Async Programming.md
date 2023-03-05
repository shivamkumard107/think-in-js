Javascript is a **single threaded, synchronous language**.

**Single** **threaded**: It can execute one command at a time
**Synchronous**: It will execute next command once the current command is executed

## 👩‍🚀 setTimeout

```js
setTimeout(() => {
    console.log("Helo after 1 sec");
}, 1000);
```

### 🤙 Callback queue

Once the timer expires, callback function is pushed to a queue called Callback queue where it waits for the event loop to pick it up and execute in call stack once it get empty.

### 📵 Event loop

Monitors the call stack and call back queue. Once it sees that the **call stack is empty**, it pushes the queue function to the call stack where it is executed quickly

### 🛠️ Starvation of a callback function

JS code takes infinite time to execute the call stack then event loop will never be able to put the callback function into the call stack

## 🐬 setInterval

```js
// will run infinite times if not stopped
const id = setInterval(() => {
    console.log("interval going on");
}, 1000);

setTimeout(() => {
    clearInterval(id);
    console.log("stopping interval");
}, 5000);
```

### 💍 var, let, const in setTimeout

```js

for (var i = 0; i < 5; i++) {
    setTimeout(() => {
        console.log(i);
    }, 1000);    
}
// prints 5, 5 times


for (let i = 0; i < 5; i++) {
    setTimeout(() => {
        console.log(i);
    }, 1000);    
}
// prints 0, 1, 2, 3, 4


for (var i = 0; i < 5; i++) {
    function fun() {
      var k = i; // or use let
      setTimeout(() => {
          console.log(k);
      }, 1000);
    }
  fun();
}
// prints 0, 1, 2, 3, 4
```

### ⏩ IIFE (Immediately Invoked Function Expression)

Saves variables not to pollute the global scope

```js
(
    function () {
        var a = 100;
        var b = 200;
    
    
        function fun() {
            console.log('Inside fun');
            console.log(a + b);
        }
    
        fun()
    }
)();

// prints 0, 1, 2, 3, 4
```