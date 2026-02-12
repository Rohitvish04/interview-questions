
# JavaScript Interview Cheat Sheet (0–2 Years Experience)

Quick revision guide with clear explanations and examples.

---

# 1. var vs let vs const

| var | let | const |
|-----|-----|-------|
| Function scoped | Block scoped | Block scoped |
| Can redeclare | Cannot redeclare | Cannot redeclare |
| Can reassign | Can reassign | Cannot reassign |

Example:

```js
var a = 10;
let b = 20;
const c = 30;
````

---

# 2. What is Hoisting?

Hoisting is JavaScript's default behavior of moving variable and function declarations to the top of their scope.

Example:

```js
console.log(a); // undefined
var a = 5;
```

---

# 3. What is a Closure?

A closure is a function that remembers variables from its outer scope even after the outer function has finished executing.

```js
function outer() {
  let count = 0;
  return function inner() {
    count++;
    return count;
  };
}

const counter = outer();
counter(); // 1
counter(); // 2
```

---

# 4. == vs ===

* `==` → Compares value only (type coercion happens)
* `===` → Compares value and type (strict comparison)

```js
5 == "5"   // true
5 === "5"  // false
```

---

# 5. What is the Event Loop?

JavaScript is single-threaded. The event loop handles asynchronous operations by pushing callbacks from the callback queue to the call stack when it’s empty.

Example:

```js
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 0);

console.log("End");
```

Output:

```
Start
End
Timeout
```

---

# 6. Callback, Promise, Async/Await

## Callback

```js
function greet(name, callback) {
  callback("Hello " + name);
}
```

## Promise

```js
const promise = new Promise((resolve, reject) => {
  resolve("Success");
});
```

## Async/Await

```js
async function fetchData() {
  return "Data";
}
```

---

# 7. What is a Promise?

A Promise represents a value that may be available now, later, or never.

States:

* Pending
* Fulfilled
* Rejected

---

# 8. What is Destructuring?

Destructuring allows unpacking values from arrays or objects.

```js
const person = { name: "Rahul", age: 25 };
const { name, age } = person;
```

---

# 9. What is Spread Operator?

Used to expand elements.

```js
const arr1 = [1, 2];
const arr2 = [...arr1, 3, 4];
```

---

# 10. What is Rest Operator?

Collects remaining elements.

```js
function sum(...numbers) {
  return numbers.reduce((a, b) => a + b);
}
```

---

# 11. Arrow Functions

Shorter syntax for functions. Does not have its own `this`.

```js
const add = (a, b) => a + b;
```

---

# 12. What is this keyword?

`this` refers to the object that is executing the function.

Example:

```js
const obj = {
  name: "JS",
  greet() {
    console.log(this.name);
  }
};
```

---

# 13. Array Methods (Important)

## map()

Returns new array

```js
[1,2,3].map(n => n * 2);
```

## filter()

Filters elements

```js
[1,2,3,4].filter(n => n % 2 === 0);
```

## reduce()

Reduces to single value

```js
[1,2,3].reduce((sum, n) => sum + n, 0);
```

---

# 14. What is Debouncing?

Debouncing limits function execution after a delay.

```js
function debounce(fn, delay) {
  let timeout;
  return function() {
    clearTimeout(timeout);
    timeout = setTimeout(() => fn(), delay);
  };
}
```

---

# 15. What is Throttling?

Throttling limits function execution to once in a given time interval.

---

# 16. What is Prototype?

JavaScript uses prototypal inheritance.

```js
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function() {
  console.log("Hello");
};
```

---

# 17. call(), apply(), bind()

Used to control `this`.

```js
function greet() {
  console.log(this.name);
}

const user = { name: "Rahul" };
greet.call(user);
```

---

# 18. What is IIFE?

Immediately Invoked Function Expression.

```js
(function() {
  console.log("Runs immediately");
})();
```

---

# 19. What is Temporal Dead Zone (TDZ)?

Variables declared with `let` and `const` cannot be accessed before initialization.

---

# 20. Common Coding Questions

Reverse a string:

```js
function reverse(str) {
  return str.split("").reverse().join("");
}
```

Check palindrome:

```js
function isPalindrome(str) {
  return str === str.split("").reverse().join("");
}
```

Remove duplicates from array:

```js
const unique = arr => [...new Set(arr)];
```

Find second largest:

```js
function secondLargest(arr) {
  return [...new Set(arr)].sort((a,b) => b-a)[1];
}
```

---

# 21. What is Event Bubbling?

Event bubbling means events propagate from child to parent.

---

# 22. What is Event Delegation?

Attaching event listener to parent instead of multiple children.

---

# Final Interview Tips

* Keep answers short and clear
* Give small examples
* Explain concepts in simple words
* Practice coding problems
* Speak confidently

---

**End of JavaScript Cheat Sheet**

```

---

If you want, I can also create:

- 🔥 Advanced JavaScript Interview Cheat Sheet  
- 💻 50 Coding Interview Questions (with solutions)  
- 🧠 Tricky JavaScript Output Questions  
- 📄 Complete Frontend Developer Interview Notes  

Tell me what you want next.
```
