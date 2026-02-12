 
# 25 Node.js Tricky Output Questions

Predict the output before running the code.
Focus: Event Loop, process.nextTick, setImmediate, Promises, Async behavior.

---

# 1
```js
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 0);

console.log("End");
````

**Output:**

```
Start
End
Timeout
```

---

# 2

```js
setImmediate(() => console.log("Immediate"));
setTimeout(() => console.log("Timeout"), 0);
```

**Output:**
Order is not guaranteed (depends on event loop phase)

---

# 3

```js
process.nextTick(() => console.log("NextTick"));
console.log("Main");
```

**Output:**

```
Main
NextTick
```

---

# 4

```js
setTimeout(() => console.log("Timeout"), 0);
process.nextTick(() => console.log("NextTick"));
```

**Output:**

```
NextTick
Timeout
```

---

# 5

```js
Promise.resolve().then(() => console.log("Promise"));
process.nextTick(() => console.log("NextTick"));
```

**Output:**

```
NextTick
Promise
```

---

# 6

```js
console.log("A");

setTimeout(() => console.log("B"), 0);

Promise.resolve().then(() => console.log("C"));

process.nextTick(() => console.log("D"));

console.log("E");
```

**Output:**

```
A
E
D
C
B
```

---

# 7

```js
let a = 5;
(function() {
  console.log(a);
  let a = 10;
})();
```

**Output:** ReferenceError

---

# 8

```js
global.x = 10;
console.log(x);
```

**Output:** `10`

---

# 9

```js
console.log(__dirname);
```

**Output:** Current directory path

---

# 10

```js
console.log(__filename);
```

**Output:** Full file path

---

# 11

```js
setTimeout(() => {
  console.log("Timeout 1");
  process.nextTick(() => console.log("NextTick inside Timeout"));
}, 0);
```

**Output:**

```
Timeout 1
NextTick inside Timeout
```

---

# 12

```js
setImmediate(() => {
  console.log("Immediate 1");
  process.nextTick(() => console.log("NextTick inside Immediate"));
});
```

**Output:**

```
Immediate 1
NextTick inside Immediate
```

---

# 13

```js
console.log(typeof module);
```

**Output:** `"object"`

---

# 14

```js
console.log(typeof exports);
```

**Output:** `"object"`

---

# 15

```js
exports.name = "Node";
console.log(module.exports);
```

**Output:**

```
{ name: 'Node' }
```

---

# 16

```js
exports = { name: "Node" };
console.log(module.exports);
```

**Output:**

```
{}
```

---

# 17

```js
console.log(Buffer.from("Node"));
```

**Output:** `<Buffer 4e 6f 64 65>`

---

# 18

```js
console.log(Buffer.from("Node").toString());
```

**Output:** `"Node"`

---

# 19

```js
setTimeout(() => console.log("Timeout"), 0);
setImmediate(() => console.log("Immediate"));
process.nextTick(() => console.log("NextTick"));
```

**Output:**

```
NextTick
Timeout/Immediate (order may vary)
```

---

# 20

```js
async function test() {
  console.log("1");
  await Promise.resolve();
  console.log("2");
}
test();
console.log("3");
```

**Output:**

```
1
3
2
```

---

# 21

```js
console.log("Start");

fs.readFile(__filename, () => {
  console.log("File Read");
});

setImmediate(() => console.log("Immediate"));
```

**Output:**
Usually:

```
Start
Immediate
File Read
```

(File I/O happens in poll phase)

---

# 22

```js
process.nextTick(() => {
  process.nextTick(() => console.log("Nested"));
});
```

**Output:**

```
Nested
```

---

# 23

```js
console.log(require.main === module);
```

**Output:**
`true` (if file run directly)

---

# 24

```js
console.log(typeof setImmediate);
```

**Output:** `"function"`

---

# 25

```js
console.log("A");

setTimeout(() => console.log("B"), 0);

setImmediate(() => console.log("C"));

process.nextTick(() => console.log("D"));

Promise.resolve().then(() => console.log("E"));

console.log("F");
```

**Output:**

```
A
F
D
E
B/C (order may vary)
```

---

# Key Event Loop Order in Node.js

1. Synchronous code
2. process.nextTick()
3. Promise microtasks
4. Timers (setTimeout)
5. I/O callbacks
6. setImmediate()

---

# End of Node.js Tricky Output Questions

```

---

If you want next:

- 🔥 Node.js Event Loop Deep Dive Diagram  
- 🚀 Advanced Backend Interview Questions  
- 💻 System Design for Node.js Developers  
- 🧠 Real Company Node.js Interview Experience Questions  

Tell me what level you want next 👌
```
