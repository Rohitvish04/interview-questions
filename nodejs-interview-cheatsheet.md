
# Node.js Interview Cheat Sheet (0–1 Year Experience)

A quick revision guide with short, confident answers and examples.

---

# 1. What is Node.js?

**Answer:**

Node.js is a JavaScript runtime built on Chrome’s V8 engine. It allows us to run JavaScript outside the browser, mainly for building backend applications and APIs. It is single-threaded and uses an event-driven, non-blocking I/O model.

---

# 2. Why is Node.js Single-Threaded?

Node.js uses a single-threaded event loop to handle multiple requests efficiently. Instead of creating multiple threads, it handles tasks asynchronously using callbacks and promises, which makes it lightweight and scalable.

---

# 3. What is the Event Loop?

The event loop is the core mechanism in Node.js that handles asynchronous operations. It continuously checks the call stack and callback queue. If the call stack is empty, it pushes tasks from the callback queue to execute.

### Example:

```js
console.log("Start");

setTimeout(() => {
  console.log("Inside Timeout");
}, 0);

console.log("End");
````

**Output:**

```
Start
End
Inside Timeout
```

---

# 4. Callback vs Promise vs Async/Await

## Callback

A function passed as an argument to another function.

```js
fs.readFile("file.txt", (err, data) => {
  console.log(data);
});
```

## Promise

Handles async operations using `.then()` and `.catch()`.

```js
fetchData()
  .then(res => console.log(res))
  .catch(err => console.log(err));
```

## Async/Await

Cleaner syntax for handling promises.

```js
async function getData() {
  const data = await fetchData();
  console.log(data);
}
```

---

# 5. What is Middleware in Express?

Middleware is a function that runs between request and response. It has access to `req`, `res`, and `next`.

```js
app.use((req, res, next) => {
  console.log("Request received");
  next();
});
```

Used for logging, authentication, validation, etc.

---

# 6. What is REST API?

REST is an architectural style for designing APIs using HTTP methods:

* GET → Fetch data
* POST → Create data
* PUT → Update entire resource
* PATCH → Update specific fields
* DELETE → Remove data

---

# 7. PUT vs PATCH

* **PUT** updates the entire resource.
* **PATCH** updates specific fields only.

Example:

```json
PUT /user/1
{
  "name": "John",
  "age": 25
}
```

```json
PATCH /user/1
{
  "age": 26
}
```

---

# 8. What is JWT?

JWT (JSON Web Token) is used for authentication. After login, the server sends a token to the client. The client sends it in headers for future requests.

Example:

```
Authorization: Bearer token_here
```

---

# 9. Error Handling in Express

Use error-handling middleware:

```js
app.use((err, req, res, next) => {
  res.status(500).json({ message: err.message });
});
```

---

# 10. What is package.json?

Contains project metadata like:

* Name
* Version
* Dependencies
* Scripts

Example:

```json
{
  "name": "my-app",
  "version": "1.0.0",
  "dependencies": {
    "express": "^4.18.2"
  }
}
```

---

# 11. require vs import

* `require` → CommonJS (older Node versions)
* `import` → ES6 module syntax

```js
const express = require("express");
```

```js
import express from "express";
```

---

# 12. What is CORS?

CORS (Cross-Origin Resource Sharing) allows or restricts resources requested from another domain.

```js
const cors = require("cors");
app.use(cors());
```

---

# 13. What is MongoDB?

MongoDB is a NoSQL database that stores data in JSON-like documents (BSON format).

Example document:

```json
{
  "name": "Rahul",
  "age": 24
}
```

---

# 14. SQL vs NoSQL

| SQL          | NoSQL           |
| ------------ | --------------- |
| Table-based  | Document-based  |
| Fixed schema | Flexible schema |
| MySQL        | MongoDB         |

---

# 15. How to Explain Your Project

Use this structure:

* Built REST API using Node.js and Express
* Implemented authentication using JWT
* Used MongoDB with Mongoose
* Created CRUD APIs
* Implemented error handling
* Used environment variables for security

---

# Bonus: Why Should We Hire You?

I have strong fundamentals in JavaScript and Node.js. I have built real-world projects with REST APIs and authentication. I am eager to learn and contribute to the team.

---

# Final Interview Tips

* Speak clearly and confidently
* Keep answers short and structured
* Give small examples
* Explain your project properly
* If unsure, say:
  "I’m not fully sure, but I think..."

---

**End of Cheat Sheet**

```

---

If you want, I can also create:

- 📌 Advanced Node.js Interview Cheat Sheet (.md)
- 📌 50 Rapid-Fire Interview Questions (.md)
- 📌 Complete Backend Developer Interview Notes (PDF style markdown)

Tell me what you want next.
```
