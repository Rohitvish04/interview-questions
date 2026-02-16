 

# MongoDB Interview Questions & Answers – Complete Guide

---

## 1. What is MongoDB?

**Answer:**
**MongoDB** is a NoSQL, document-oriented database that stores data in JSON-like format (BSON).

* Schema-less
* Scalable
* High performance
* Suitable for modern web applications

---

## 2. What is NoSQL?

**Answer:**
NoSQL means **Not Only SQL**.
It is a non-relational database that stores data in flexible formats:

* Document-based (MongoDB)
* Key-value
* Column-based
* Graph

---

## 3. What is a Document in MongoDB?

**Answer:**
A document is a single record in JSON-like format stored in a collection.

```json
{
  "name": "John",
  "age": 25,
  "city": "New York"
}
```

---

## 4. What is a Collection?

**Answer:**
A collection is a group of documents, similar to a table in relational databases.

---

## 5. What is BSON?

**Answer:**
BSON = Binary JSON.
MongoDB stores data in BSON format which supports additional types like Date, ObjectId, and Binary.

---

## 6. What is the `_id` Field?

**Answer:**

* Acts as a primary key for documents
* Automatically generated if not provided (ObjectId)

Example:

```json
{
  "_id": ObjectId("63f2a1b5e1234abcd56789ef"),
  "name": "John"
}
```

---

## 7. What are CRUD Operations?

* **Create** → `insertOne()`
* **Read** → `find()` / `findOne()`
* **Update** → `updateOne()` / `updateMany()`
* **Delete** → `deleteOne()` / `deleteMany()`

Example:

```js
db.users.insertOne({ name: "John", age: 25 })
db.users.find({ age: 25 })
db.users.updateOne({ name: "John" }, { $set: { age: 26 } })
db.users.deleteOne({ name: "John" })
```

---

## 8. What is the Default Port of MongoDB?

**Answer:** 27017

---

## 9. Difference Between MongoDB and MySQL

| MongoDB                  | MySQL                 |
| ------------------------ | --------------------- |
| NoSQL database           | Relational database   |
| Stores data in documents | Stores data in tables |
| Schema-less              | Fixed schema          |
| Flexible structure       | Strict structure      |

---

## 10. What is Indexing?

**Answer:**
Indexing improves query performance by allowing MongoDB to locate data without scanning the full collection.

Example:

```js
db.users.createIndex({ email: 1 })
```

---

## 11. What is Aggregation?

**Answer:**
Aggregation is used to process and compute data, similar to SQL GROUP BY.

Example:

```js
db.orders.aggregate([
  { $match: { status: "completed" } },
  { $group: { _id: "$customerId", total: { $sum: "$amount" } } }
])
```

---

## 12. What is a Replica Set?

**Answer:**
A replica set is a type of cluster for high availability:

* **Primary node** → handles writes
* **Secondary node(s)** → replicate data
* **Arbiter (optional)** → votes in elections

**Features:**

* Automatic failover
* High availability
* Data redundancy

---

## 13. What is a Sharded Cluster?

**Answer:**
Sharding distributes data across multiple servers to handle large datasets and high traffic.

Components:

* **Shards** → store actual data
* **Config servers** → store metadata
* **Mongos** → route queries

---

## 14. What is a Cluster in MongoDB?

**Answer:**
A cluster is a group of MongoDB servers working together to provide **high availability, fault tolerance, and scalability**.

---

## 15. Difference Between Cluster and Replica Set

| Feature    | Cluster                        | Replica Set                    |
| ---------- | ------------------------------ | ------------------------------ |
| Definition | Group of MongoDB servers       | Type of cluster for redundancy |
| Purpose    | High availability / scaling    | High availability only         |
| Components | Shards, config servers, mongos | Primary + Secondary + Arbiter  |
| Data       | Distributed (sharded)          | Replicated                     |
| Scaling    | Horizontal                     | Fault tolerance only           |
| Use Case   | Large datasets, high traffic   | Applications needing failover  |

---

## 16. What is a Shard Key?

**Answer:**
A shard key determines how data is distributed across shards.
Good shard key → high cardinality, frequently queried, evenly distributed.

---

## 17. What is a Config Server and Mongos?

* **Config Server:** Stores metadata about shards and data distribution.
* **Mongos:** Routes queries to the correct shard.

---

## 18. Maximum Document Size

**Answer:** 16 MB

---

## 19. find() vs findOne()

* `find()` → returns multiple documents (cursor)
* `findOne()` → returns the first matching document

---

## 20. Covered Query

**Answer:**
A query that only uses fields in an index and does not scan the documents. Very fast.

---

## 21. Index Intersection

**Answer:**
MongoDB can combine multiple indexes to satisfy a query.

---

## 22. Write Concern

**Answer:**
Defines acknowledgment level for write operations.

```js
{ w: "majority" }
```

---

## 23. Read Concern

**Answer:**
Defines consistency level of read operations:

* local, majority, linearizable

---

## 24. Embedding vs Referencing

| Embedding                           | Referencing                       |
| ----------------------------------- | --------------------------------- |
| Store related data in same document | Store data in separate collection |
| Faster reads                        | Better scalability                |
| Risk of large document growth       | Requires `$lookup` for joins      |

---

## 25. Scenario-Based Questions

### Scenario 1: Slow Query

* Use `explain("executionStats")`
* Check for collection scan
* Add proper index
* Optimize query & projection

### Scenario 2: Index created but query slow

* Wrong index order
* Low selectivity
* Sorting on non-indexed field

### Scenario 3: Primary node fails in replica set

* Secondary nodes hold election
* New primary chosen automatically

### Scenario 4: Large dataset

* Use sharding with good shard key
* Each shard as a replica set

### Scenario 5: Auto delete old data

* Use TTL index:

```js
db.collection.createIndex(
  { createdAt: 1 },
  { expireAfterSeconds: 2592000 }
)
```

### Scenario 6: Pagination efficiently

* Bad: `.skip(10000).limit(10)`
* Better:

```js
db.users.find({ _id: { $gt: lastId } }).limit(10)
```

---

## 26. Beginner Revision Checklist

* MongoDB basics, BSON, `_id`
* CRUD operations
* Indexing basics
* Aggregation pipeline
* Replica sets & failover
* Sharding & cluster basics

---

## 27. 2 Years Experience Checklist

* Covered queries
* Index intersection
* Shard key selection
* Multi-document transactions
* Performance optimization
* Real scenario examples from projects

---

## 28. References

* [MongoDB Official Docs](https://www.mongodb.com/docs/)
* [MongoDB University Courses](https://university.mongodb.com/)
* [MongoDB Atlas Free Cluster](https://www.mongodb.com/cloud/atlas)

---

**END OF DOCUMENT**

---

I can also create a **visual “MongoDB Cluster & Replica Set Diagram + Questions” .md** file next for quick interview reference.

Do you want me to do that?
