
# HTTP & Web Basics – Interview Questions

---

## 1️⃣ What happens when you type a URL in the browser?

**Answer:**

1. Browser checks cache  
2. DNS(Domain Name System) resolves domain to IP  
3. Browser establishes TCP(Transmission Control Protocol) connection  
4. Sends HTTP request  
5. Server processes request  
6. Server sends HTTP response  
7. Browser renders HTML/CSS/JS  

---

## 2️⃣ What is HTTP?

HTTP (HyperText Transfer Protocol) is a **communication protocol used for transferring data between client and server on the web**.

Example:

```

Browser → HTTP Request → Server
Server → HTTP Response → Browser

```

---

## 3️⃣ Difference between HTTP and HTTPS?

| HTTP | HTTPS |
|-----|------|
| Not secure | Secure |
| No encryption | Uses SSL/TLS encryption |
| Port 80 | Port 443 |

HTTPS protects data from **man-in-the-middle attacks**.

---

## 4️⃣ What is a URL?

URL = **Uniform Resource Locator**

Example:

```

[https://example.com/users?id=10](https://example.com/users?id=10)

```

Parts:

- Protocol  
- Domain  
- Path  
- Query parameters  

---

## 5️⃣ What is DNS?

DNS (Domain Name System) converts **domain names to IP addresses**.

Example:

```

google.com → 142.250.183.206

```

---

## 6️⃣ What is an HTTP Request?

A request sent by a **client to a server asking for a resource**.

Structure:

```

GET /users HTTP/1.1
Host: example.com
Authorization: Bearer token

```

Components:

- Method  
- URL  
- Headers  
- Body  

---

## 7️⃣ What is an HTTP Response?

A response sent by a **server back to the client**.

Structure:

```

HTTP/1.1 200 OK
Content-Type: application/json

```

Contains:

- Status code  
- Headers  
- Body  

---

## 8️⃣ What are HTTP Methods?

Methods define **what action should be performed**.

| Method | Purpose |
|------|------|
| GET | Fetch data |
| POST | Create resource |
| PUT | Update resource |
| PATCH | Partial update |
| DELETE | Remove resource |

---

## 9️⃣ Difference between GET and POST?

| GET | POST |
|----|----|
| Used to retrieve data | Used to send data |
| Data in URL | Data in body |
| Cached | Not cached |
| Idempotent | Not idempotent |

---

## 🔟 What are HTTP Status Codes?

Status codes indicate **result of the request**.

Example:

```

200 OK
404 Not Found
500 Server Error

```

---

## 1️⃣1️⃣ Common Status Codes

### 2xx – Success
- 200 OK  
- 201 Created  

### 4xx – Client errors
- 400 Bad Request  
- 401 Unauthorized  
- 403 Forbidden  
- 404 Not Found  

### 5xx – Server errors
- 500 Internal Server Error  

---

## 1️⃣2️⃣ Difference between 401 and 403?

| 401 | 403 |
|----|----|
| Authentication required | Permission denied |

Example:

- 401 → User not logged in  
- 403 → Logged in but no permission  

---

## 1️⃣3️⃣ What are HTTP Headers?

Headers provide **metadata about request/response**.

Examples:

```

Content-Type: application/json
Authorization: Bearer token
User-Agent: Chrome

```

---

## 1️⃣4️⃣ What is Content-Type header?

It tells the **format of the request or response body**.

Examples:

```

application/json
text/html
multipart/form-data

```

---

## 1️⃣5️⃣ What are Cookies?

Cookies are **small pieces of data stored in the browser**.

Example:

```

Set-Cookie: sessionId=abc123

```

Used for:

- Authentication  
- User tracking  
- Preferences  

---

## 1️⃣6️⃣ What are Sessions?

Sessions store **user data on the server**.

Flow:

1. User logs in  
2. Server creates session  
3. Session ID stored in cookie  
4. Cookie sent with each request  

---

## 1️⃣7️⃣ Difference between Cookies and Sessions?

| Cookies | Sessions |
|------|------|
| Stored in browser | Stored on server |
| Limited size | Larger storage |
| Less secure | More secure |

---

## 1️⃣8️⃣ What is CORS?

CORS (Cross-Origin Resource Sharing) is a **browser security feature that restricts requests between different origins**.

Example:

Frontend

```

[http://localhost:3000](http://localhost:3000)

```

Backend

```

[http://localhost:5000](http://localhost:5000)

```

Server must allow it using:

```

Access-Control-Allow-Origin: *

```

---

## 1️⃣9️⃣ What is Idempotent in HTTP?

An operation is **idempotent if repeating it gives the same result**.

### Idempotent
- GET  
- PUT  
- DELETE  

### Not Idempotent
- POST  

---

## 2️⃣0️⃣ What is REST?

REST (Representational State Transfer) is an **architecture for designing APIs using HTTP methods**.

Example API:

```

GET /users
POST /users
PUT /users/1
DELETE /users/1

```

---

## ✅ Pro Interview Tip

Practice API calls using:

- Postman  
- curl  
- MDN Web Docs
```

✅ Save this file as:

```
http-interview-notes.md
```

You can open it in:

* Visual Studio Code
* Obsidian
* Notion
* GitHub

---

If you want, I can also create a **complete Backend Interview Notes `.md` file (about 150+ questions)** which is **perfect for revision before interviews**. 🚀
