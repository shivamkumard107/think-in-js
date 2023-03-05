#### 🫱 Problems with Callback

1.  Callback hell
2.  Inversion of Control

#### 💥 Callback hell
```js
function downloadFile(url) {
    console.log(`starting the downloand from ${url}`);
    return new Promise((resolve, reject) => {
        if (!url.startsWith('http')) {
            reject(new Error("Invalid Url"));
        }
        setTimeout(() => {
            resolve(url);
        }, 3000);
    });
}

function compressFile(fileName) {
    console.log(`starting the file compression from ${fileName}`);
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve(fileName);
        }, 2000);
    });
}

function uploadFile(compressedPath) {
    console.log('starting the file upload');
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve(compressedPath);
        }, 3000)
    });
}
const URL = 'ws://facebook/storage/profile.jpg'

downloadFile(URL, function downloaded(url) {
    const fileName = url.split('/').pop();
    console.log(`File downloaded successfully ${fileName}`);
    compressFile(fileName, function (fileName) {
        const compressedPath = fileName.split('.')[0] + ".zip";
        console.log(`File compressed successfully as ${compressedPath}`);
        uploadFile(compressedPath, function () {
            const uploadedPath = 'http://facebook.com/localsystem' + compressedPath;
            console.log(`File uploaded successfull at ${uploadedPath}`);
            console.log("Everything done");
        })
    });
});
```

### 🤝 Good Code Using Promise

#### 🥘 Creating & Consuming a promise

```js
Creating a promise
const p = new Promise(function (resolve, reject) {
    const randumNum = Math.floor(Math.random() * 10);
    if (randumNum % 2 !== 0) {
        const err = new Error("Not a even number");
        reject(err);
    }
    resolve(randumNum);
});



// consuming a promise
p.then((num) => {
    console.log(num);
    })
    .catch((err) => {
        console.log(err.message);
    })
    .finally(() => {
        console.log('Yea chalega hi har case mein!');
    })
```

Promises are objects, are used to handle async operations which represent some eventual completion of a task. It has three states pending, fulfilled and rejected

#### Callback hell resolved

```js
downloadFile(URL)
    .then((url) => {
        const fileName = url.split('/').pop();
        console.log(`File downloaded successfully ${fileName}`);
        return compressFile(fileName);
    })
    .then((fileName) => {
        const compressedPath = fileName.split('.')[0] + ".zip";
        console.log(`File compressed successfully as ${compressedPath}`);
        return uploadFile(compressedPath);
    })
    .then((compressedPath) => {
        const uploadedPath = 'http://facebook.com/localsystem' + compressedPath;
        console.log(`File uploaded successfull at ${uploadedPath}`);
        console.log("Everything done");
    })
    .catch((err) => {
        console.log(err.message);
    });
```

#### 🌊 Async/Await

Async function: makes a normal function return a promise object whose state is fulfilled and value of the promise is the value returned by that function

```js
async function add(a, b) {
  return a + b;
}
```

await can only be used inside a async function. Once an await is encountered, JS transfers the function execution to Browser Web APIs and it continues the execution of rest of the code. Once the response is received the function is pushed again to the call stack, where it is executed from where await was encountered.