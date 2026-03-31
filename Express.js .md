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

# Express.js Routes – Interview Notes

## 🔹 What are Routes?

Routes define how your application responds to a **client request** for a specific URL and HTTP method.

👉 **Route = URL + HTTP Method + Handler Function**

---

## 🔹 Basic Example

```js id="n5h4pz"
app.get("/home", (req, res) => {
  res.send("Welcome to Home Page");
});
```

* `/home` → URL
* `GET` → HTTP method
* Function → handles request & sends response

---

## 🔹 Common HTTP Methods

* `GET` → Fetch data
* `POST` → Create data
* `PUT` → Update data
* `DELETE` → Delete data

Example:

```js id="6g8r2v"
app.post("/user", (req, res) => {
  res.send("User created");
});
```

---

## 🔹 Route Parameters (Dynamic Routes)

```js id="m2r9yc"
app.get("/user/:id", (req, res) => {
  res.send(req.params.id);
});
```

👉 Example: `/user/101` → returns `101`

---

## 🔹 Query Parameters

```js id="1s0kxz"
app.get("/search", (req, res) => {
  res.send(req.query.name);
});
```

👉 Example: `/search?name=John`

---

## 🔹 Using Express Router (Modular Routes)

```js id="0j4k3d"
const router = express.Router();

router.get("/", (req, res) => {
  res.send("All users");
});

module.exports = router;
```

Use in main file:

```js id="q9l2w8"
app.use("/users", router);
```

---

## 🔹 How Routing Works

```text id="p8d7vx"
Client Request → Route Match → Handler Function → Response
```

---

## 🔹 Difference: Route vs Middleware

| Route                  | Middleware                    |
| ---------------------- | ----------------------------- |
| Handles final response | Runs before route             |
| Uses `app.get()` etc.  | Uses `app.use()`              |
| Ends request cycle     | Passes control using `next()` |

---

## 🔹 Short Interview Answer

> Routes in Express are used to define endpoints that handle client requests based on URL and HTTP methods. Each route executes a function that processes the request and returns a response.

