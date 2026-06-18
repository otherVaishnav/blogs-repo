---
title: "OFFSET FETCH"
description: "Explore the OFFSET FETCH section."
pubDate: "2025-06-01"
---

<!-- # OFFSET FETCH -->

Different ways of limiting the number of records in RESULT TABLE in different databases. 

### MySQL

```sql
SELECT col_name/exp
...
ORDER BY col_name/exp 
LIMIT n OFFSET m; 
```

### ORACLE

```sql
SELECT col_name/exp
... 
ORDER BY col_name/exp 
OFFSET m ROWS 
FETCH FIRST/NEXT n ROWS ONLY/WITH TIES;
```

1. Fetch THE TOP 5 EMPLOYEES BY HIREDATE.
2. Fetch THE EMPLOYEE HIRED AT LAST. (MOST RECENT)
3. Fetch THE EMPLOYEE EARNING HIGHEST SALARY 
4. Fetch THE EMPLOYEES EARNING 3RD AND 4TH HIGHEST SALARY 
5. Fetch THE 10TH HIGHEST SALARY 
6. Fetch THE FIRST 10 EMPLOYEES 
7. Fetch THE EMPLOYEES EARNING 5TH AND 10TH HIGHEST SALARY. (try rownum)
8. Fetch THE FIRST 9 EMPLOYEES WHEN ORDERED BY NAME (ASC)
9. Fetch THE EMPLOYEE EARNING LOWEST SALARY 
10. Fetch THE DEPARTMENT NO HAVING HIGHEST NUMBER OF EMPLOYEES
11. Fetch THE DEPARTMENT NAME HAVING HIGHEST NUMBER OF EMPLOYEES

---

---

1. Write a query to display employees from EMP table sorted by SAL in descending order, skipping the first 5 rows and returning the next 10 rows only.
2. Write a query to display the top 3 highest paid employees from EMP.
3. Write a query to display the 4 employees with the lowest salaries.
4. Write a query to return the top 5 salaries from EMP, including employees who have the same salary as the 5th employee (use WITH TIES).
5. What happens if you use FETCH FIRST 5 ROWS ONLY without an ORDER BY clause? Is the result deterministic? Explain.
6. Write a query to return the top 20 percent of employees based on salary.
7. Assume page size = 10. Write a query to fetch page 4 results from EMP ordered by EMPNO.
8. Write a query to return the top 5 employees based on annual salary (SAL * 12) using FETCH.
9. Write two queries to return the top 5 employees by salary:
    
    a) Using FETCH FIRST
    
    b) Using ROWNUM
    
10. Write a query to return the top 3 highest paid employees along with department name from EMP and DEPT tables.
11. Write a query to return the top 2 departments with the highest average salary.
12. Write a query to:
    - First sort employees by salary descending
    - Then skip top 3
    - Then fetch next 5
    - Then order those 5 results alphabetically by ENAME
13. Write a query that ranks employees by salary using RANK() and then fetches only the first 5 ranked results.
14. You are paginating employee data ordered only by SAL. Multiple employees share the same salary.
    
    Explain the issue and write a corrected query that ensures stable pagination.
    
15. Write a query to return the 2nd highest salary using OFFSET and FETCH.
16. Write a query to return the top 3 departments by number of employees.
17. What happens if:
    
    a) OFFSET value exceeds total row count?
    
    b) FETCH value exceeds remaining rows?
    
18. Write two queries to return the top 3 salaries:
    
    a) Using FETCH FIRST 3 ROWS WITH TIES
    
    b) Using RANK() in a subquery