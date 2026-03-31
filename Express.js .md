# Express.js `app.use()` – Interview Notes

## 🔹 What is `app.use()`?

`app.use()` is used to **mount middleware functions** in an Express application.

👉 Middleware = functions that run **between the request and response cycle**

---

## 🔹 Basic Syntax

```js
app.use([path], middlewareFunction)
```

* `path` (optional): URL path
* `middlewareFunction`: function that handles request/response

---

## 🔹 Why do we use `app.use()`?

### 1. ✅ Run middleware for every request

```js
app.use((req, res, next) => {
  console.log("Request received");
  next();
});
```

---

### 2. ✅ Parse incoming JSON data

```js
app.use(express.json());
```

---

### 3. ✅ Serve static files

```js
app.use(express.static("public"));
```

---

### 4. ✅ Middleware for a specific path

```js
app.use("/api", (req, res, next) => {
  console.log("API middleware");
  next();
});
```

---

### 5. ✅ Use routers (modular code)

```js
const userRoutes = require("./routes/user");
app.use("/users", userRoutes);
```

---

## 🔹 How it works

```
Client → Middleware (app.use) → Route Handler → Response
```

Each middleware must call:

```js
next();
```

---

## 🔹 Common Interview Questions

### ❓ Difference between `app.use()` and `app.get()`

* `app.use()` → works for **all HTTP methods**
* `app.get()` → works only for **GET requests**

---

### ❓ What if `next()` is not called?

👉 Request will **hang** (no response)

---

### ❓ Does order matter?

👉 Yes ✅ Middleware runs **in order defined**

---

### ❓ Can we use multiple middleware?

```js
app.use(middleware1, middleware2);
```

---

## 🔹 Short Interview Answer

> `app.use()` is used to register middleware in Express. It executes for every request (or a specific path) and is commonly used for parsing data, logging, authentication, and routing.
