
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

| Feature            | HTTP                                      | HTTPS                                         |
|-------------------|------------------------------------------|-----------------------------------------------|
| **Full Form**       | HyperText Transfer Protocol              | HyperText Transfer Protocol Secure           |
| **Security**        | Not secure. Data is sent in **plain text**, which can be intercepted or read by attackers. | Secure. Data is **encrypted** using TLS/SSL, making it hard for attackers to intercept or tamper with. |
| **Port Number**     | 80                                       | 443                                           |
| **URL Prefix**      | `http://`                                 | `https://`                                   |
| **Data Integrity**  | No guarantee. Data can be altered in transit. | Provides data integrity. Ensures data is not tampered with. |
| **Use Case**        | Suitable for websites where security isn’t critical (blogs, public info sites). | Essential for sensitive transactions (online banking, e-commerce, login pages). |
| **Trust Indicator** | Browser shows “Not secure” for forms and logins. | Browser shows padlock icon, indicating a secure connection. |

## Key Takeaways
1. **HTTPS is HTTP + encryption.** The encryption comes from **TLS (Transport Layer Security)**, formerly SSL.  
2. Using HTTPS protects **privacy, authentication, and data integrity**.  
3. Modern browsers increasingly **warn users** if a site is HTTP, especially if it has forms or login fields.  

---

## 4️⃣ What is a URL?

URL = **Uniform Resource Locator**
A URL is a reference (address) used to access resources on the internet, such as web pages, images, videos, or files.

Example:

```

[https://www.example.com:443/blog/article.html?id=5#comments)

```

Parts:

- https → secure protocol
- www.example.com → server/domain
- :443 → port (default for HTTPS)
- /blog/article.html → path to a file
- ?id=5 → query parameter
- #comments → fragment identifier

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
- 200 OK — Request succeeded.
​- 201 Created — Resource was created successfully, often after a POST request.
- ​204 No Content — Request succeeded but there is no response body. 

### 4xx – Client errors
- 400 Bad Request — The client sent invalid input or a malformed request.
- 401 Unauthorized — Authentication is missing or invalid.
- 403 Forbidden — Authentication may be valid, but access is not allowed.
- 404 Not Found — The resource does not exist.
- 429 Too Many Requests — The client hit a rate limit.

### 5xx – Server errors
- 500 Internal Server Error — Generic server-side failure.
- 502 Bad Gateway — One server got a bad response from another server.
- 503 Service Unavailable — The server is temporarily unavailable.
- 504 Gateway Timeout — A server upstream did not respond in time.
​

 

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
