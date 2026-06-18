---
title: "Temporary Tables"
description: "Explore the Temporary Tables section."
pubDate: "2025-06-01"
---

<!-- # Temporary Tables -->

---

**Temporary Tables** are specialized tables used to store intermediate result sets that are only needed for a short period—usually the lifespan of a single database session or transaction.

### Why use Temporary Tables?
- **Performance Optimization**: Breaking down massively complex queries into stepping-stones can drastically speed up performance.
- **Session Isolation**: Each user or session automatically gets their own isolated instance of the temporary table; data is never mixed between concurrent connections.
- **Auto-Cleanup**: The database automatically drops the table or deletes its contents when the session terminates or a commit occurs.

**Syntax Example (Standard SQL Server):**
```sql
-- Creating a temp table (denoted by # in some systems)
CREATE TABLE #TempEmployees (
    id INT, 
    salary DECIMAL
);

-- Populating it via a query
INSERT INTO #TempEmployees
SELECT id, salary FROM employees WHERE status = 'Active';
```

---

### Notes & Questions

---

### Permanent / Regular Tables

- Stored permanently in the database
- Exist until explicitly dropped
- Shared by all users/sessions
- Part of the schema
    
    ```sql
    CREATE TABLE employees (
    emp_id NUMBER PRIMARY KEY,
    name   VARCHAR2(50)
    );
    ```
    

Key characteristics

- Data is persistent
- Supports constraints, indexes, triggers
- Used for core business data
- Participates fully in backup, recovery, replication

---

## Temporary Tables

Structure is permanent, data is temporary.

Types

1. Session-level temp table
    - Data exists for the session
        
        ```sql
        CREATE GLOBAL TEMPORARY TABLE temp_sales (
        order_id NUMBER,
        amount   NUMBER
        ) ON COMMIT PRESERVE ROWS;
        ```
        
2. Transaction-level temp table
    - Data cleared after each commit
        
        ```sql
        CREATE GLOBAL TEMPORARY TABLE temp_sales (
        order_id NUMBER,
        amount   NUMBER
        ) ON COMMIT DELETE ROWS;
        ```
        

---

Key characteristics

- Table definition is permanent
- Data is private to the session
- Data is auto-deleted (commit or session end)
- No need for manual cleanup
- Reduces locking and contention

---

---