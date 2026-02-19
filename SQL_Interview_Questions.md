 
---

# SQL Interview Questions and Answers

---

## Basics (Conceptual)

### 1. What is SQL?

SQL (Structured Query Language) is a **standard language** used to store, manipulate, and retrieve data in relational database management systems (RDBMS).

### 2. What is an RDBMS?

An RDBMS stores data in tables (rows and columns), enforces relationships using keys, and supports SQL for querying and managing data.

### 3. What are DDL, DML, DCL, and TCL?

* **DDL (Data Definition Language):** `CREATE`, `ALTER`, `DROP`, `TRUNCATE` – Defines schema
* **DML (Data Manipulation Language):** `SELECT`, `INSERT`, `UPDATE`, `DELETE` – Works with data
* **DCL (Data Control Language):** `GRANT`, `REVOKE` – Manages permissions
* **TCL (Transaction Control Language):** `COMMIT`, `ROLLBACK`, `SAVEPOINT` – Manages transactions

### 4. What is a Primary Key?

A primary key uniquely identifies each row in a table and cannot be `NULL`.

### 5. What is a Foreign Key?

A foreign key is a column (or columns) in one table that refers to the primary key of another table to enforce referential integrity.

### 6. Unique Key vs Primary Key

* Both enforce uniqueness.
* A table can have multiple unique keys.
* Unique key allows one `NULL` (in many DBs).
* Only one primary key per table.
* Primary key cannot be `NULL`.

### 7. What is a Candidate Key?

Any column or combination of columns that can uniquely identify a row; one of them is chosen as the primary key.

### 8. What is a Composite Key?

A key composed of more than one column used together to uniquely identify a row.

### 9. What is a View?

A view is a virtual table based on the result of a SQL query; it stores the query definition, not the actual data.

### 10. What is an Index? Why is it used?

An index is a data structure (like a B-tree) that speeds up data retrieval on one or more columns, at the cost of extra storage and slower writes.

---

## Queries and Clauses

### 11. Difference between `WHERE` and `HAVING`

* `WHERE` filters rows before grouping and cannot use aggregate functions directly.
* `HAVING` filters groups after `GROUP BY` and can use aggregates like `COUNT`, `SUM`.

### 12. Difference between `GROUP BY` and `ORDER BY`

* `GROUP BY` groups rows to apply aggregate functions.
* `ORDER BY` sorts the final result set.

### 13. Fetch employees with salary > 50000

```sql
SELECT *
FROM Employees
WHERE Salary > 50000;
```

### 14. Count employees in each department

```sql
SELECT DepartmentId, COUNT(*) AS EmployeeCount
FROM Employees
GROUP BY DepartmentId;
```

### 15. What is `DISTINCT`?

`DISTINCT` removes duplicate rows from the result set.

```sql
SELECT DISTINCT DepartmentId
FROM Employees;
```

---

## Joins

### 16. Types of Joins

* **INNER JOIN** – Matching rows in both tables
* **LEFT JOIN** – All rows from left + matching from right
* **RIGHT JOIN** – All rows from right + matching from left
* **FULL OUTER JOIN** – All rows from both tables
* **CROSS JOIN** – Cartesian product

### 17. Employees with their department names

```sql
SELECT e.Name, d.Name AS DepartmentName
FROM Employees e
INNER JOIN Departments d
  ON e.DeptId = d.Id;
```

### 18. What is a Self Join?

A self join joins a table with itself (e.g., employee-manager hierarchy).

```sql
SELECT e.Name AS Employee, m.Name AS Manager
FROM Employees e
LEFT JOIN Employees m
  ON e.ManagerId = m.Id;
```

---

## Subqueries and Advanced

### 19. What is a Subquery?

A subquery is a query inside another query, used in `SELECT`, `FROM`, or `WHERE`.

### 20. Correlated vs Non-correlated Subquery

* **Non-correlated:** Executes once.
* **Correlated:** Executes once per outer row.

### 21. Employees with salary greater than average

```sql
SELECT *
FROM Employees
WHERE Salary > (
    SELECT AVG(Salary) FROM Employees
);
```

### 22. Second Highest Salary

**Method 1:**

```sql
SELECT MAX(Salary) AS SecondHighestSalary
FROM Employees
WHERE Salary < (
    SELECT MAX(Salary) FROM Employees
);
```

**Method 2 (Using DENSE_RANK):**

```sql
SELECT Salary
FROM (
    SELECT Salary,
           DENSE_RANK() OVER (ORDER BY Salary DESC) AS r
    FROM Employees
) s
WHERE r = 2;
```

### 23. What is a Window Function?

Performs calculations across related rows without collapsing them.

```sql
SELECT EmployeeId,
       Salary,
       SUM(Salary) OVER (ORDER BY EmployeeId) AS RunningTotal
FROM Employees;
```

---

## Transactions and Constraints

### 24. What is a Transaction?

A transaction is a logical unit of work that is either fully completed or rolled back (ACID properties).

### 25. ACID Properties

* **Atomicity** – All or nothing
* **Consistency** – Valid state to valid state
* **Isolation** – No interference between transactions
* **Durability** – Changes persist after commit

### 26. `COMMIT` vs `ROLLBACK`

* `COMMIT` saves changes.
* `ROLLBACK` undoes changes since last commit/savepoint.

### 27. Common Constraints

`NOT NULL`, `UNIQUE`, `PRIMARY KEY`, `FOREIGN KEY`, `CHECK`, `DEFAULT`

---

## Performance and Design

### 28. Clustered vs Non-clustered Index

* **Clustered:** Defines physical order, one per table.
* **Non-clustered:** Separate structure pointing to data, multiple allowed.

### 29. When Can Indexes Hurt Performance?

* Heavy inserts/updates/deletes
* Too many indexes
* High maintenance overhead

### 30. What is Normalization?

Organizing data to reduce redundancy and improve integrity.

### 31. 1NF, 2NF, 3NF

* **1NF:** Atomic values, no repeating groups
* **2NF:** No partial dependency
* **3NF:** No transitive dependency

### 32. What is Denormalization?

Intentional redundancy to reduce joins and improve read performance.

---

## Tricky Questions

### 33. `DELETE` vs `TRUNCATE` vs `DROP`

* **DELETE:** Removes rows, can use `WHERE`, can rollback
* **TRUNCATE:** Removes all rows, faster, limited rollback
* **DROP:** Removes table structure and data

### 34. Handling `NULL` Values

* Use `IS NULL` / `IS NOT NULL`
* Use `COALESCE()` / `IFNULL()`
* Understand impact on aggregates

### 35. Why Avoid `SELECT *`?

* Poor performance
* Unnecessary columns
* Schema change risk
* Prevents index-only plans

### 36. Find Duplicate Records

```sql
SELECT Email, COUNT(*) AS Cnt
FROM Users
GROUP BY Email
HAVING COUNT(*) > 1;
```

### 37. Delete Duplicates but Keep One

```sql
WITH cte AS (
    SELECT *,
           ROW_NUMBER() OVER (PARTITION BY Email ORDER BY Id) AS rn
    FROM Users
)
DELETE FROM cte
WHERE rn > 1;
```

### 38. Employees Without Department

```sql
SELECT e.*
FROM Employees e
LEFT JOIN Departments d
  ON e.DeptId = d.Id
WHERE d.Id IS NULL;
```

---

# Quick Practice Set

## 1. Orders Table

`Orders(OrderId, CustomerId, Amount, OrderDate)`

* Get total amount spent by each customer.
* Get customers who spent more than 100000 in total.
* Find the latest order for each customer.

## 2. Students Table

`Students(Id, Name, Marks)`

* Get top 3 students by marks.
* Get students whose marks are above class average.
* Count students in grade buckets (>80, 60–80, <60).

---

If you’d like, I can also:

* Convert this into a **GitHub-ready README format**
* Add a **Table of Contents with anchor links**
* Create a **PDF version layout**
* Add **intermediate or advanced-level questions section**
