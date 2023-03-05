```js
// reverse words

const sentence = "The blue fox jumps over a white lazy dog";

function reverseFun(str) {
    return sentence.split(" ").reverse().join(" ");
}

const nums = 34125;

function countDigit(num) {
    return (String(num)).length;
}

const str = "io a e ufdsoikjbf";
function countVowels(str) {
    const vow = ['a', 'e', 'i', 'o', 'u'];
    let ans = 0;
    for (const i of str) {
        for (const j of vow) {
            if (i == j) {
                ans++;
            }
        }
    }
    return ans;
}

const numsArr = [49, 64, 81, 16];
// expected ans = [7, 8, 9, 4]
function squareRoot(numsArr) {
    const root = [];
    for (const iterator of numsArr) {
        root.push(Math.sqrt(iterator));
    }
    return root;
}


const message = "Hello World";
function frequency(msg) {
    const map = new Map();
    for (const i of msg.split("")) {
        if (i == " ") {
            continue;
        }
        if (map.get(i) !== undefined) {
            map.set(i, map.get(i) + 1);
        } else {
            map.set(i, 1);
        }
    }
    return map;
}

const list = [1, 2, 3, "4", 5];
const listSum = (list) => {
    let ans = 0;
    for (const element of list) {
        if (typeof element === 'number') {
            ans += element;
        }
    }
    return ans;
}


const num = 12345;
const evemSum = (num) => {
    let ans = 0;
    while (num != 0) {
        if ((num % 10) % 2 == 0) {
            ans += num % 10;
        }
        num = parseInt(num / 10);
    }
    return ans;
}

const str1 = "The blue fox jumps over a white lazy dog";
const capitalise = (str) => {
    const x = str.split(" ");
    let ans = [];
    for (const str of x) {
        ans.push(str.replace(str[0], str[0].toUpperCase()));
        // Also str.charAt(0).toUpperCase() + str.slice(1)
    }
    return ans.join(" ");
}
const sen1 = "I don't repeat mistakes I date mistakes mistakes date repeat";
const removeRepeat = (message) => {
    const set = new Set(message.split(" "));
    return Array.from(set).join(' ');
}

const myArr = [[1, 2], [3, 4, 5], ["Hello", true], [5, [true, false]], 99, 100];

const flatArray = (arr) => {
    let ans = [];
    for (const element of arr) {
        if (Array.isArray(element)) {
            for (const iterator of element) {
                ans.push(iterator);
            }
        } else {
            ans.push(element);
        }
    }
    console.log(ans);
}


console.log(`reverse: ${reverseFun(sentence)}`);
console.log(`count digit: ${countDigit(nums)}`);
console.log(`count vowels: ${countVowels(str)}`);
console.log(`square root: ${squareRoot(numsArr)}`);
console.log(`frequency: ${frequency(message)}`);
console.log(`listSum: ${listSum(list)}`);
console.log(`even sum: ${evemSum(num)}`);
console.log(`capitalise: ${capitalise(str1)}`);
console.log(`removeRepeat: ${removeRepeat(sen1)}`);
flatArray(myArr);
```