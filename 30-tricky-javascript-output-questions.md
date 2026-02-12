 
# 30 Tricky JavaScript Output Questions

Practice predicting the output before running the code.

---

# 1
```js
console.log(1 + "2" + "3");
````

**Output:** `"123"`

---

# 2

```js
console.log("1" + 2 + 3);
```

**Output:** `"123"`

---

# 3

```js
console.log(1 + 2 + "3");
```

**Output:** `"33"`

---

# 4

```js
console.log([] + []);
```

**Output:** `""`

---

# 5

```js
console.log([] + {});
```

**Output:** `"[object Object]"`

---

# 6

```js
console.log({} + []);
```

**Output:** `0` (in most browsers)

---

# 7

```js
console.log(true + false);
```

**Output:** `1`

---

# 8

```js
console.log(null + 1);
```

**Output:** `1`

---

# 9

```js
console.log(undefined + 1);
```

**Output:** `NaN`

---

# 10

```js
console.log(typeof null);
```

**Output:** `"object"`

---

# 11

```js
console.log(typeof NaN);
```

**Output:** `"number"`

---

# 12

```js
console.log(0.1 + 0.2 === 0.3);
```

**Output:** `false`

---

# 13

```js
console.log([] == false);
```

**Output:** `true`

---

# 14

```js
console.log([] === false);
```

**Output:** `false`

---

# 15

```js
console.log("5" - 3);
```

**Output:** `2`

---

# 16

```js
console.log("5" + 3);
```

**Output:** `"53"`

---

# 17

```js
console.log(!!"false");
```

**Output:** `true`

---

# 18

```js
let a = {};
let b = {};
console.log(a == b);
```

**Output:** `false`

---

# 19

```js
let a = {};
let b = a;
console.log(a == b);
```

**Output:** `true`

---

# 20

```js
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 0);
}
```

**Output:**

```
3
3
3
```

---

# 21

```js
for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 0);
}
```

**Output:**

```
0
1
2
```

---

# 22

```js
console.log(typeof typeof 1);
```

**Output:** `"string"`

---

# 23

```js
console.log(1 < 2 < 3);
```

**Output:** `true`

---

# 24

```js
console.log(3 > 2 > 1);
```

**Output:** `false`

---

# 25

```js
console.log("b" + "a" + +"a" + "a");
```

**Output:** `"baNaNa"`

---

# 26

```js
console.log([] == ![]);
```

**Output:** `true`

---

# 27

```js
let x = 10;
(function() {
  console.log(x);
  let x = 20;
})();
```

**Output:** ReferenceError (Temporal Dead Zone)

---

# 28

```js
console.log(a);
var a = 5;
```

**Output:** `undefined`

---

# 29

```js
console.log(a);
let a = 5;
```

**Output:** ReferenceError

---

# 30

```js
Promise.resolve().then(() => console.log("Promise"));
console.log("Start");
```

**Output:**

```
Start
Promise
```

---

# End of Tricky Output Questions

```

---

If you want next:

- 🔥 20 Advanced Event Loop Questions  
- 🚀 25 Node.js Tricky Output Questions  
- 💻 Frontend Interview Rapid Fire Round  
- 🧠 JavaScript Deep Concepts Explained  

Tell me what difficulty level you want next 👌
```
