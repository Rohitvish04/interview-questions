

# MongoDB Beginner Interview Questions & Answers

---

# 1. What is MongoDB?

**Answer:**

**MongoDB** is a NoSQL, document-oriented database that stores data in JSON-like format (BSON).

It is:

* Schema-less
* Scalable
* High performance
* Used for modern web applications

---

# 2. What is NoSQL?

**Answer:**

NoSQL means **Not Only SQL**.

It is a non-relational database that does not store data in tables like traditional SQL databases.

Types of NoSQL databases:

* Document-based (MongoDB)
* Key-value
* Column-based
* Graph

---

# 3. What is a Document in MongoDB?

**Answer:**

A document is a single record stored in MongoDB in JSON-like format.

Example:

```json
{
  "name": "John",
  "age": 25,
  "city": "New York"
}
```

Documents are stored inside collections.

---

# 4. What is a Collection?

**Answer:**

A collection is a group of documents.

It is similar to a table in relational databases.

---

# 5. What is BSON?

**Answer:**

BSON stands for **Binary JSON**.

MongoDB stores data internally in BSON format.

It supports additional data types like:

* Date
* ObjectId
* Binary data

---

# 6. What is the `_id` Field?

**Answer:**

* Every document must have an `_id` field.
* It acts as a primary key.
* If not provided, MongoDB automatically creates an ObjectId.

Example:

```json
{
  "_id": ObjectId("123abc"),
  "name": "John"
}
```

---

# 7. What are CRUD Operations?

**Answer:**

CRUD stands for:

* Create
* Read
* Update
* Delete

---

## Create

```js
db.users.insertOne({ name: "John", age: 25 })
```

---

## Read

```js
db.users.find()
db.users.find({ age: 25 })
```

---

## Update

```js
db.users.updateOne(
  { name: "John" },
  { $set: { age: 26 } }
)
```

---

## Delete

```js
db.users.deleteOne({ name: "John" })
```

---

# 8. What is the Default Port of MongoDB?

**Answer:**

The default port is:

```
27017
```

---

# 9. Difference Between MongoDB and MySQL?

**Answer:**

| MongoDB                  | MySQL                 |
| ------------------------ | --------------------- |
| NoSQL database           | Relational database   |
| Stores data in documents | Stores data in tables |
| Schema-less              | Fixed schema          |
| Flexible structure       | Strict structure      |

---

# 10. What is Indexing?

**Answer:**

Indexing improves query performance.

Without index:

* MongoDB scans entire collection.

With index:

* MongoDB quickly finds matching documents.

Example:

```js
db.users.createIndex({ email: 1 })
```

---

# 11. What is Aggregation?

**Answer:**

Aggregation is used to process and analyze data.

It is similar to GROUP BY in SQL.

Example:

```js
db.orders.aggregate([
  { $group: { _id: "$customerId", total: { $sum: "$amount" } } }
])
```

---

# 12. What is a Replica Set?

**Answer:**

A replica set is a group of MongoDB servers that maintain the same data.

Purpose:

* High availability
* Automatic failover
* Data redundancy

One primary handles writes, secondaries replicate data.

---

# 13. What is Sharding?

**Answer:**

Sharding is horizontal scaling in MongoDB.

It distributes data across multiple servers to handle large data and high traffic.

---

# 14. What is the Maximum Document Size in MongoDB?

**Answer:**

Maximum document size is:

```
16 MB
```

---

# 15. What is the Difference Between `find()` and `findOne()`?

**Answer:**

* `find()` → Returns multiple documents (cursor)
* `findOne()` → Returns only the first matching document

---

# 16. What is Schema-less Database?

**Answer:**

Schema-less means documents in a collection can have different structures.

Example:

Document 1:

```json
{ "name": "John", "age": 25 }
```

Document 2:

```json
{ "name": "Alice", "city": "London" }
```

Both can exist in the same collection.

---

# 17. What is an ObjectId?

**Answer:**

ObjectId is a 12-byte unique identifier automatically generated for `_id` field.

It contains:

* Timestamp
* Machine identifier
* Process ID
* Counter

---

# 18. Why Use MongoDB?

**Answer:**

* Flexible schema
* Easy scalability
* Good performance
* Suitable for real-time applications
* Easy to integrate with modern tech stacks

---

# Beginner Revision Checklist

Make sure you understand:

* What is MongoDB
* CRUD operations
* `_id` field
* BSON
* Indexing basics
* Aggregation basics
* Replica set concept
* Sharding concept

---

END OF BEGINNER MONGODB INTERVIEW QUESTIONS & ANSWERS

---

If you want next level:

* Intermediate MongoDB Interview Q&A (.md)
* Aggregation Practice Problems (.md)
* MongoDB Mock Interview (Questions + Answers)

Tell me which one you need 👍
