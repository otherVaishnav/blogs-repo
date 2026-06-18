---
order: 17
---

# Start with and Connect By

→ Both are hierarchical query clauses. 

→ Used to query **parent–child relationships** stored in a single table. 

→ this are oracle specific, not available in standard SQL. ( use WITH RECURSIVE )

Syntax : 

```sql
SELECT column_name/exp
FROM table_name 
START WITH condition     
CONNECT BY [PRIOR] condition;
										|
		PRIOR parent_column = child_column	
```

1. START WITH 
    
    → defines the root row(s) of the hierarchy, ( **top-level parent )** 
    
    →  Can return **multiple root nodes.** 
    
    →  If you omit this clause, then Oracle uses all rows in the table as root rows
    
    eg. 
    
    ```sql
    START WITH <condn> 
    START WITH manager_id IS NULL 
    ```
    

1. CONNECT BY 
    
    → **defines the parent–child relationship**.
    
    Syntax : 
    
    ```sql
    CONNECT BY PRIOR parent_column = child_column
    ```
    
    → PRIOR ( unary operator. ) determines the **parent row.** 
    
    → The row without PRIOR is the **child row**
    
    → Depth-first order.
    
    eg. 
    
    ```sql
    CONNECT BY PRIOR emp_id = manager_id
    -- it means Parent is emp_id and Child is manager_id 
    -- Traverse downward (manager → employees)
    
    CONNECT BY PRIOR manager_id = emp_id
    -- Traverse upward (employee → manager)
    ```
    
    ### NOCYCLE :
    
      → breaks out of the loop at run time. 
    
      → if loop is found , it skips the row. 
    
    ```sql
    -- example
    SELECT SYS_CONNECT_BY_PATH(ENAME,'->')
    FROM EMP
    CONNECT BY PRIOR MGR = EMPNO;
    ---
    SELECT SYS_CONNECT_BY_PATH(ENAME,'->')
    FROM EMP
    START WITH MGR IS NULL
    CONNECT BY PRIOR EMPNO = MGR
    /
    
    ```
    
    → more hierarchical pseudo columns : 
    
    1. **CONNECT_BY_ISCYCLE :** 
        
        ⇒ returns 1 if it’s a cycle, otherwise 0. 
        
        ⇒ can be used only if connect by has NOCYCLE .
        
    2.  **CONNECT_BY_ISLEAF :** 
        
        ⇒ returns 1 if the current row is a leaf, otherwise 0. 
        
    3. **LEVEL :** 
        
        ⇒ return the level of the node in hierarchy. 
        
    4. **CONNECT_BY_ROOT** : 
    
      → ancestor rows in the hierarchy.
    
    Questions : 
    
    1. Display the complete reporting hierarchy starting from the top-level manager. Show LEVEL and indentation ‘/’ .
        
        ```sql
        SELECT LEVEL, SYS_CONNECT_BY_PATH(ENAME,'/')
        FROM EMP
        START WITH MGR IS NULL 
        CONNECT BY PRIOR EMPNO = MGR;
        ```
        
    2. For employee FORD, display the full chain of command up to the CEO.
        
        ```sql
        SELECT SYS_CONNECT_BY_PATH(ENAME,'=>') AS CHAIN_OF_COMMAND
        FROM EMP
        START WITH ENAME = 'FORD' 
        CONNECT BY EMPNO = PRIOR MGR;
        ```
        
    3. List all employees who report directly or indirectly to JONES.
        
        ```sql
        SELECT ENAME
        FROM EMP 
        START WITH ENAME = 'JONES' 
        CONNECT BY PRIOR EMPNO = MGR;
        ```
        
    4. Find the employees present at the maximum depth of the reporting hierarchy in the company.
        
        ```sql
        SELECT ENAME , LEVEL 
        FROM EMP
        WHERE LEVEL = (
        	SELECT MAX(LEVEL) 
        	FROM EMP
        	START WITH MGR IS NULL
        	CONNECT BY PRIOR EMPNO = MGR
        ) 
        START WITH MGR IS NULL 
        CONNECT BY PRIOR EMPNO = MGR;
        ```
        
    5. Identify employees who are at LEVEL 3 in the hierarchy.
        
        ```sql
        SELECT ENAME, LEVEL 
        FROM EMP 
        WHERE LEVEL = 3 
        START WITH MGR IS NULL 
        CONNECT BY PRIOR EMPNO = MGR;
        ```
        
    6. Calculate the total salary under each manager including indirect subordinates.
        
        ```sql
        -- name of employee, SAL under him 
        -- group by employee , sum of salries
        SELECT CONNECT_BY_ROOT, SAL, LEVEL
        FROM EMP 
        CONNECT BY PRIOR EMPNO = MGR;
        ```
        
    7. Find managers whose total team salary exceeds 10000.
        
        ```sql
        SELECT MGR_NAME, SUM(SAL)
        FROM (
        	SELECT CONNECT_BY_ROOT(ENAME) AS MGR_NAME, SAL
        	FROM EMP
        	CONNECT BY PRIOR EMPNO = MGR
        )
        GROUP BY MGR_NAME
        HAVING SUM(SAL) > 10000
        /
        
        ```
        
    8. For each employee, display their salary along with the total salary of their entire reporting subtree.
        
        ```sql
        SELECT ENAME, SAL , MGR_SAL
        FROM (
        	SELECT ENAME, SAL,
        				 CONNECT_BY_ROOT(SAL) AS MGR_SAL
        	FROM EMP
        	CONNECT BY PRIOR EMPNO = MGR
        )
        WHERE SAL > MGR_SAL;
        ```
        
    9. Find employees whose salary is greater than their manager’s salary anywhere in the hierarchy.
    10. Identify employees who do not manage anyone.
        
        ```sql
        SELECT ENAME , LEVEL, CONNECT_BY_ISLEAF 
        FROM EMP
        WHERE CONNECT_BY_ISLEAF = 1
        START WITH MGR IS NULL 
        CONNECT BY PRIOR EMPNO = MGR;
        ```
        
    11. Identify managers who report directly to the CEO.
        
        ```sql
        SELECT ENAME, LEVEL
        FROM EMP
        WHERE LEVEL = 2
        START WITH MGR IS NULL 
        CONNECT BY PRIOR EMPNO = MGR;
        ```
        
    
    Ref. 
    
    [https://docs.oracle.com/cd/B12037_01/server.101/b10759/queries003.htm](https://docs.oracle.com/cd/B12037_01/server.101/b10759/queries003.htm)  
    
    [https://www.oradev.com/connect_by.jsp](https://www.oradev.com/connect_by.jsp)