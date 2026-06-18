---
title: "Query Optimizations"
description: "Explore the Query Optimizations section."
pubDate: "2025-06-01"
---

<!-- # Query Optimizations -->
List of techniques and best practices to optimize SQL queries for better performance and efficiency.

1. No SELECT * 
    
    → why fetch useless data !!! 
    
2. Use Index 
    - join condition
    - WHERE conditions
    - GROUP BY
    - ORDER BY

→ Be carefull though : 

- It slow downs DML ( insert, update, delete ).
- Composite Index order.
- functions break index usage.

1. Try to use WHERE before JOIN. 
    
    → less rows, faster join. 
    
2. Use EXISTS over IN for subqueries. 
    
    ```sql
    IN : 
    SELECT col/exp
    FROM t1
    WHERE id IN ( SELECT id 
    					    FROM t2 )
    
    EXISTS : 
    SELECT col/exp
    FROM t1
    WHERE EXISTS ( SELECT 1 
    							 FROM table_name
    							 WHERE t1.id = t2.id )
    ```
    
3. Avoid Corelated subqueries. 
4. Inner is faster than LEFT
5. Use limiting 
6. GROUP BY is expensive, use when required. 
7. Partition Tables if possible.