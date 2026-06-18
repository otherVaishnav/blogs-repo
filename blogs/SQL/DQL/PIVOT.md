---
title: "PIVOT"
description: "Explore the PIVOT section."
pubDate: "2025-06-01"
---


<!-- # PIVOT -->

Pivot : Converting rows into columns. 

Use Case : 

1. To summarize the data. 
2. Want fixed number of categories. 
3. For creating reports. 

SYNTAX : 

```sql
SELECT * 
FROM table_name/source_table 
PIVOT (
		aggregate_function(col_name)
		FOR pivot_column IN (
				value_1 AS alias_1,
				value_2 AS alias_2, 
				value_3 AS alias_3,
				.....
		)
); 			
```

## source table

```sql
SELECT row_title, category , to_aggregate 
FROM table_name;
```

eg. 

1. DISPLAY THE NUMBER OF SALESMAN, ANALYST AND CLERK IN EVERY DEPARTMENT.   
    
    ```sql
    SELECT DEPTNO , SALESMAN , ANALYST, CLERKERK
    FROM (
         SELECT DEPTNO , JOB, EMPNO
         FROM EMP
    ) src_table
    PIVOT (
    	COUNT(EMPNO)
    	FOR JOB IN (
    		'SALESMAN' AS SALESMAN,
    		'ANALYST'  AS ANALYST,
    		'CLERK' AS CLERK
    	)
    ) summary ;
    ```
    
1. HIGHEST SALARY OF EACH JOB IN EVERY DEPARTMENT. 
    
    ```sql
    SELECT DEPTNO, Salesman, Analyst, Clerk, Manager 
    FROM ( 
    		SELECT DEPTNO , JOB , SAL, EMPNO 
    		FROM EMP
    ) src_table 
    PIVOT ( 
    		MAX(SAL) 
    		FOR JOB IN ( 
    				'SALESMAN' AS Salesman,
    				'ANALYST'  AS Analyst,
    				'CLERK' AS Clerk,
    				'MANAGER' AS Manager
    	 ) 
    ) summary_table;
    ```
    
2. Write a query to display total salary of SALESMAN, ANALYST, and CLERK in each department using PIVOT.
3. Display the maximum salary of SALESMAN, MANAGER, and ANALYST in each department.
4. Display the number of employees hired in each department for the years 1980 and 1981 using PIVOT.
5. Show total commission (COMM) of SALESMAN and ANALYST department-wise using PIVOT.
6. Display average salary of CLERK and MANAGER in each department.
7. Write a PIVOT query to display count of employees in departments 10, 20, and 30 for each job.
8. Display minimum salary of employees in department 10, 20, and 30 for each job using PIVOT.
9. Write a query that shows total salary paid to employees under each manager (MGR), pivoted by JOB (SALESMAN, CLERK, ANALYST).
10. Display count of employees per job category for department 30 only using PIVOT.
11. Create a pivot report showing total salary department-wise, where JOB categories are columns (CLERK, SALESMAN, MANAGER, ANALYST).
12. Write a PIVOT query to display highest salary of each JOB in every department.
13. Display total salary for each hire year (e.g., 1980, 1981, 1982), pivoted department-wise.
14. Write a query that:
    - Extracts hire year from HIREDATE
    - Counts employees
    - Pivots result year-wise (1980, 1981, 1982).
15. Create a PIVOT report showing:
    - Department-wise
    - Average salary
    - Columns as JOB
    - Ordered by department number.
16. Display total commission department-wise where JOB categories are pivoted columns. Handle NULL commission properly.
17. Write a PIVOT query that:
    - Shows number of employees
    - For departments 10 and 20 only
    - Columns should be JOB categories.
18. Write a PIVOT query to display total salary for MANAGER and ANALYST only, grouped department-wise.
19. Create a PIVOT report that:
    - Uses SUM(SAL)
    - Includes only departments having more than 3 employees (use subquery before pivot).
20. Write a query to compare:
    - COUNT(EMPNO)
    - SUM(SAL)
        
        In the same PIVOT result for each JOB (multiple aggregate functions).
        
21. Create a PIVOT query that:
    - First joins EMP and DEPT
    - Then displays department name
    - Then pivots total salary by JOB.

## Interview stuff

1. Why must aggregate functions be used inside PIVOT?
2. What happens if a pivoted value (e.g., 'PRESIDENT') does not exist in a department?
3. Why must pivot values be explicitly listed in Oracle PIVOT?
4. Compare PIVOT vs GROUP BY with CASE expressions.
5. What are limitations of Oracle PIVOT clause?
6. Can we use expressions inside FOR column? Explain.
7. Why is a subquery often required before PIVOT?
8. What happens if duplicate rows exist in the source table before pivoting?