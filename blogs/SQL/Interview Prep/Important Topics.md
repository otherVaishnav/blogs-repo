---
order: 1
---

# High-Yield SQL Interview Topics

When preparing for a SQL technical interview—whether for a Data Analyst, Data Engineer, or Backend Developer role—interviewers don't query everything. They heavily favor concepts that demonstrate your ability to manipulate data conditionally, combine datasets efficiently, and perform rolling calculations.

Focus your energy on mastering the following **top 5 topics**:

---

## 1. Window Functions
Interviewers love Window Functions because they solve complex analytical problems (like running totals or rankings) elegantly without subqueries or self-joins.

**What to master:**
- Syntactical structure: `OVER (PARTITION BY ... ORDER BY ...)`
- Ranking functions: `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()` (and understanding the exact differences between them during ties).
- Value functions: `LEAD()`, `LAG()` to pull data from adjacent physical rows (e.g., month-over-month growth). 
- Aggregates within a window: `SUM(...) OVER()`.

## 2. Advanced Joins
Basic `INNER JOIN`s won't cut it. You need to know how to creatively link tables.

**What to master:**
- **`LEFT JOIN`** vs **`INNER JOIN`**: Know when one destroys necessary rows and the other creates nulls.
- **`SELF JOIN`**: Querying a hierarchical table (e.g., matching employees to their managers in the same table).
- **`CROSS JOIN`**: Creating Cartesian products (sometimes asked as a trick question or useful for generating a base calendar to join operational data against).

## 3. CTEs (Common Table Expressions)
CTEs (the `WITH` clause) demonstrate that you write clean, maintainable, and modular code.

**What to master:**
- Using CTEs instead of nasty, deeply-nested Subqueries.
- Referencing a single CTE multiple times within the same query.
- **Recursive CTEs** (more advanced, but common in senior engineering roles) for tree/graph traversal.

## 4. Conditional Aggregation
Often, you'll be asked to pivot data or calculate a specific metric based on conditions within a group.

**What to master:**
- Combining `SUM()`, `COUNT()`, or `MAX()` with an inner `CASE` statement.
  *Example: Count how many approved vs rejected transactions occurred per user in a single row.*
- The standard `PIVOT` clause (if writing Oracle/T-SQL), but the `CASE` statement approach is universally accepted and often preferred in interviews since it is standard SQL.

## 5. Date & Time Manipulation
Almost all reporting questions involve a time dimension (e.g., "trailing 7-day average" or "signups this month").

**What to master:**
- Extracting elements (Year, Month) dynamically.
- Date math logic (e.g., adding days, finding differences between timestamps).
- Handling `NULL` dates using `COALESCE`.
