
# 50 SQL Rapid-Fire Questions with Answers

Quick one-line answers for SQL interview prep (0–2 Years Experience)

---

## Basics (1–15)

1. **What is SQL?**  
   Structured Query Language for managing relational databases.

2. **Difference between SQL and MySQL?**  
   SQL → language; MySQL → relational database system.

3. **What is a primary key?**  
   Unique identifier for each record in a table.

4. **What is a foreign key?**  
   Column linking two tables; maintains referential integrity.

5. **What is a unique key?**  
   Ensures all values in a column are unique.

6. **Difference between primary key and unique key?**  
   Primary key → cannot be NULL; unique key → can be NULL.

7. **What is an index?**  
   Speeds up query performance by creating a lookup structure.

8. **What is a composite key?**  
   Primary key made of two or more columns.

9. **What is normalization?**  
   Process of organizing data to reduce redundancy.

10. **What is denormalization?**  
    Adding redundancy to improve query performance.

11. **What is a view?**  
    Virtual table created using a SELECT query.

12. **Difference between DELETE and TRUNCATE?**  
    DELETE → removes rows, can use WHERE, slower; TRUNCATE → removes all rows, faster, cannot use WHERE.

13. **Difference between DROP and DELETE?**  
    DROP → removes table structure; DELETE → removes data but table remains.

14. **What is a schema?**  
    Collection of database objects like tables, views, procedures.

15. **What is a transaction?**  
    A unit of work that is atomic, consistent, isolated, and durable (ACID).

---

## SQL Queries (16–30)

16. **What is SELECT?**  
    Used to fetch data from a table.

17. **What is WHERE?**  
    Filters records based on conditions.

18. **What is ORDER BY?**  
    Sorts query results ascending (ASC) or descending (DESC).

19. **What is GROUP BY?**  
    Groups rows sharing the same value for aggregation.

20. **What is HAVING?**  
    Filters groups created by GROUP BY.

21. **What is JOIN?**  
    Combines rows from two or more tables.

22. **Types of JOIN?**  
    INNER, LEFT, RIGHT, FULL OUTER, CROSS JOIN.

23. **What is INNER JOIN?**  
    Returns rows with matching values in both tables.

24. **What is LEFT JOIN?**  
    Returns all rows from left table + matching rows from right table.

25. **What is RIGHT JOIN?**  
    Returns all rows from right table + matching rows from left table.

26. **What is FULL OUTER JOIN?**  
    Returns all rows from both tables; unmatched rows are NULL.

27. **What is CROSS JOIN?**  
    Cartesian product of two tables.

28. **What is UNION?**  
    Combines result sets of two SELECT queries, removes duplicates.

29. **Difference between UNION and UNION ALL?**  
    UNION → removes duplicates; UNION ALL → keeps duplicates.

30. **What is subquery?**  
    Query inside another query.

---

## Functions (31–40)

31. **What is COUNT()?**  
    Returns number of rows.

32. **What is SUM()?**  
    Returns total sum of a column.

33. **What is AVG()?**  
    Returns average value of a column.

34. **What is MIN()?**  
    Returns minimum value.

35. **What is MAX()?**  
    Returns maximum value.

36. **What is DISTINCT?**  
    Removes duplicate rows from result.

37. **What is LIKE?**  
    Used for pattern matching with `%` and `_`.

38. **What is IN?**  
    Checks if a value exists in a list.

39. **What is BETWEEN?**  
    Filters values within a range.

40. **What is IS NULL / IS NOT NULL?**  
    Checks for NULL or non-NULL values.

---

## Advanced / Constraints (41–50)

41. **What is a constraint?**  
    Rule enforced on table columns to maintain data integrity.

42. **Types of constraints?**  
    PRIMARY KEY, FOREIGN KEY, UNIQUE, NOT NULL, CHECK, DEFAULT.

43. **What is CHECK constraint?**  
    Ensures column values satisfy a condition.

44. **What is DEFAULT constraint?**  
    Provides default value if none is supplied.

45. **What is ACID property?**  
    Atomicity, Consistency, Isolation, Durability – ensures reliable transactions.

46. **What is a stored procedure?**  
    Predefined SQL code block stored in the database.

47. **What is a trigger?**  
    Executes automatically on INSERT, UPDATE, or DELETE events.

48. **What is an index and its types?**  
    Speeds up queries; types → UNIQUE, FULLTEXT, BITMAP, CLUSTERED.

49. **What is a cursor?**  
    Database object used to retrieve rows one at a time.

50. **Difference between OLTP and OLAP?**  
    OLTP → transactional, frequent insert/update/delete; OLAP → analytical, complex queries for reporting.

---

# End of 50 SQL Rapid-Fire Questions
```

---

I can also create a **combined “SQL + JS + Node + Coding + Output Questions Super Cheat Sheet”** as **one 300+ Q&A Markdown file** if you want, so you can revise everything in one place.

Do you want me to do that next?
