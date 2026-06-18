---
title: "Index"
description: "Explore the Index section."
pubDate: "2025-06-01"
---
<!-- # Index -->

Index is a database object that improves query performance by providing quick access to rows in a table.

- It allows faster retrieval of data.
- Reduces full table scans for searches.
- Indexes are automatically created on primary key and unique constraint columns.
- It affects only the speed of execution.

—> Drawback : 

- extra space to store index
- Slow Writes ( DML )
    - The database must update the index when DML occurs on the indexed data

### Types of Indexes:

1. Key Structure ( number of cols ) 
2. Uniqueness ( data present )
3.  Physical ( storage )

⇒ also Based on the Structure 

```sql
INDEX
 ├─ Based on Physical ( storage )
 │   ├─ Clustered
 │   └─ Non-Clustered  (default)
 │
 ├─ Based on Key Structure ( number of cols )
 │   ├─ Single Column 
 │   └─ Composite 
 │
 ├─ Based on Uniqueness ( data present )
 │   ├─ Unique
 │   └─ Non-Unique  (default)
 │
 └─ Based on the INDEX Structure
		 ├─ B - Tree    (default) -- O(log N)
		 ├─ Bitmap                --  low cardinality column 
     ├─ Hash                  --  O(1) 
     ├─ Full-Text             -- searching large text fields  
     ├─ Function-Based        -- add a index on fnction 
```

## 1. Based on Physical ( storage )

1. Clustered 

          → physical order 

          → we can have only one Clustered index on a table. 

          → not present in Oracle. ( but you can have a primary key on IOT [ Index Organized Table ] )

```sql
-- Oracle equivalent
CREATE TABLE table_name (
   col1 NUMBER PRIMARY KEY,
   col2 VARCHAR2(100)
) ORGANIZATION INDEX;  
---------
CREATE CLUSTERED INDEX index_name 
ON table_name(col_name)

```

1. NON- Clustered (default ) 
    
         → logical ( pointers ) 
    
    → we can have many non-clustered index on a single table. 
    
    → A non-clustered index is an index structure that is stored separately from the table data.
    
    → In Oracle, every normal index you create with CREATE INDEX is non-clustered by default.
    
    → It contains index keys + ROWID pointers to the actual rows in the table.
    
    ```sql
    CREATE INDEX index_name 
    ON table_name(col_name);
    ```
    

### 2. Based on Key Structure ( number of cols )

1. Single Column 
    
    ```sql
    CREATE INDEX index_name
    ON table_name(column_name);
    ```
    
2. Composite Column 
    
    ```sql
    CREATE INDEX index_name
    ON table_name (column_name1, column_name2);
    ```
    

### 3. Based on Uniqueness ( data present )

1. Unique 
    
    ```sql
    CREATE UNIQUE INDEX index_name
    ON table_name(column_name);
    ```
    
2. Non - Unique ( default ) 
    
    ```sql
    CREATE INDEX index_name
    ON table_name(column_name);
    ```
    

### 4. Based on Index Structure

→ Different structures for storing the INDEX 

1. B- Tree ( default )

          → O(log n) 

    → oracle default 

1. Hash    
    
          → O(1) 
    
    → memory efficient , uses hash function instead if tree 
    
    → Only equality searches. okay for exact match
    
    → cannot handle range .
    
    → not present in oracle. 
    
    ```sql
    CREATE INDEX idx_hash 
    ON users USING HASH (username);
    ```
    
2. Bit map 

           → bits ( binary ) 

           → used for columns with low cardinality 

     → Bitmap indexes are bad for high-concurrency OLTP

---

### Questions :

1. Create a non-unique index on JOB .
    
    ```sql
    CREATE INDEX emp_job 
    ON EMP(job);
    ```
    
2. Create a unique index on **EMPNO**.
    
    ```sql
    CREATE UNIQUE INDEX emp_empno 
    ON EMP(EMPNO);
    ```
    
3. Create a composite index on DEPTNO and JOB.
4. Create an index on DNAME.
5. Create an index named emp_sal_idx on sal .
6. Create a index on ENAME which can be used while comparing names in uppercase.
    
    ```sql
    CREATE INDEX emp_ename_upper 
    ON EMP(UPPER(ENAME));
    ```
    
7. Write SQL to check existing indexes on EMP (data dictionary query).
8. Write query to see index status from USER_INDEXES.
9. Drop index emp_sal_index.