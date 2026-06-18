# DQL (Data Query Language)

---
DQL is a subset of SQL used to query and fetch data from databases. It allows users to retrieve information from one or more tables without modifying the underlying data structure or the data itself.

The primary and only command in DQL is **`SELECT`**.

---

### SELECT

→ It is used to extract or retrieve data from a database. 
→ The data returned is stored in a temporary result table, often called the result-set.

**Basic Syntax:**

```sql
SELECT column1, column2, ...
FROM table_name;
```

To fetch all columns from a table, you can use the `*` (asterisk) wildcard:

```sql
SELECT * FROM table_name;
```

---

### Common Clauses used with DQL

When querying data, `SELECT` is often combined with several other clauses to filter, group, or sort the retrieved data:

1. **`WHERE`**  
   → Used to filter records based on specific conditions.
   ```sql
   SELECT * FROM employees WHERE department = 'Sales';
   ```

2. **`ORDER BY`**  
   → Used to sort the result-set in ascending (`ASC`) or descending (`DESC`) order.
   ```sql
   SELECT name, salary FROM employees ORDER BY salary DESC;
   ```

3. **`GROUP BY`**  
   → Used to group rows that have the same values into summary rows. It is most often used with aggregate functions like `COUNT()`, `MAX()`, `MIN()`, `SUM()`, or `AVG()`.
   ```sql
   SELECT department, COUNT(*) FROM employees GROUP BY department;
   ```

4. **`HAVING`**  
   → Similar to the `WHERE` clause, but it is used to filter records after they have been grouped by `GROUP BY` (because `WHERE` cannot be used directly with aggregate functions).
   ```sql
   SELECT department, COUNT(*) FROM employees GROUP BY department HAVING COUNT(*) > 5;
   ```

5. **`LIMIT` / `OFFSET` / `FETCH`**  
   → Used to limit the number of records returned (syntax may vary slightly depending on the database system like PostgreSQL, MySQL, or Oracle).
   ```sql
   SELECT * FROM employees ORDER BY salary DESC LIMIT 10;
   ```

---

### Key Characteristics of DQL

- **Read-Only:** DQL strictly reads data. It does not manipulate or change the data within tables (operations like `INSERT`, `UPDATE`, and `DELETE` belong to Data Manipulation Language or DML).
- **Relational Interactions:** DQL can dynamically link real-world entities through operations like table `JOIN`s, `Subqueries`, and Set Operators (`UNION`, `INTERSECT`, etc.).
