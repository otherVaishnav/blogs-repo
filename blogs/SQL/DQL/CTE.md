---
order: 15
---

# CTE

→ It’s a temporary table which can be used in SQL statement

→ Scope is limited to only one SQL statement.  

Syntax : 

```sql
WITH CTE_NAME AS ( 
			SELECT ...
)
SELECT ... 
```

→ To simplify complex joins/subqueries

→ To improve code clarity

We can define multiple CTE’s in a single query using comma 

```sql
WITH CTE_NAME AS ( 
			SELECT ... 
), CTE_NAME_2 AS ( 
			SELECT ...
), CTE_NAME_3 AS ( 
			SELECT ...
)

SQL STATEMENT ... 
```

---

---

1. Using SCOTT schema, write a CTE to calculate the average salary of all employees. Then display employees whose salary is greater than that average.
    
    ```sql
    SELECT CTE_AVGSAL AS (
    		SELECT AVG(SAL) AVG_SAL
    		FROM EMP
    ) 
    SELECT *
    FROM EMP 
    WHERE SAL > ( SELECT AVG_SAL
    							FROM CTE_AVGSAL ) ; 
    ```
    
2. Using HR schema, write a CTE that retrieves department-wise average salary. Then display only those departments where the average salary is greater than 10000.
3. Using SCOTT schema, create a CTE that joins EMP and DEPT and returns employee name, salary, and department name. From that CTE, fetch only employees working in SALES.
4. Using HR schema, create a CTE that calculates annual salary (salary * 12) for each employee. From the CTE, display the top 5 employees based on annual salary using FETCH.
5. Using SCOTT schema, write a CTE to count number of employees in each department. From that result, return only departments having more than 3 employees.
6. Using HR schema, create two CTEs:
    - First CTE: Employees hired after 2005
    - Second CTE: Employees earning more than 8000
        
        Display employees who satisfy both conditions.
        
7. Using SCOTT schema, write a CTE that ranks employees by salary using RANK(). Then select employees having rank <= 3.
8. Using HR schema, write a CTE to compute total salary expense per department. Then return the department with the highest total salary.
9. Using SCOTT schema, write a recursive CTE to display employee hierarchy (EMPNO, ENAME, MGR) starting from KING.
10. Using HR schema, write a recursive CTE to show the reporting structure starting from the employee whose EMPLOYEE_ID = 100.
11. Using SCOTT schema, create a CTE that finds the second highest salary in each department.
12. Using HR schema, write a CTE that calculates department-wise salary rank using DENSE_RANK(). Then fetch only departments whose highest salary rank is 1.
13. Using SCOTT schema, write a CTE that:
    - Calculates department-wise average salary
    - Joins back with EMP
    - Displays employees earning above their department average
14. Using HR schema, create a CTE that:
    - Calculates total employees per job
    - Calculates average salary per job
        
        From that result, return jobs having more than 5 employees and average salary greater than 7000.
        
15. Using SCOTT schema, write multiple CTEs where:
    - First CTE calculates department salary totals
    - Second CTE calculates company-wide average department total
    - Final query returns departments whose total salary is above company average.
16. Using HR schema, write a CTE that assigns ROW_NUMBER() to employees ordered by salary within each department. From that CTE, return top 2 employees per department.
17. Using SCOTT schema, write a recursive CTE to generate numbers from 1 to 20 without using any table.
18. Using HR schema, create a CTE to identify departments with no employees.
19. Using SCOTT schema, write a CTE that detects duplicate salaries within the same department.
20. Using HR schema, write a CTE that:
    - Calculates running total of salary ordered by hire_date
    - Returns employees where cumulative salary exceeds 500000.