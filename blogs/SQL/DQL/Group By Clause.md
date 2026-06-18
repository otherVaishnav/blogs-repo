---
title: "Group By Clause"
description: "Explore the Group By Clause section."
pubDate: "2025-06-01"
---

<!-- # Group By Clause -->

---

The **`GROUP BY`** clause in SQL is used to divide rows in a table into smaller groups based on identical values in one or more columns. It is exclusively used alongside aggregate functions (`COUNT`, `SUM`, `AVG`, `MAX`, `MIN`) to perform calculations on each group rather than the whole table.

**Syntax Example:**
```sql
SELECT department, COUNT(job) as number_of_jobs
FROM employees
GROUP BY department;
```

---

### Practice Questions

1. Display NUMBER OF EMPLOYEES WORKING IN EACH DEPARTMENT.
2. Display MAXIMUM SALARY GIVEN TO EACH JOB.
3. Display MAX SAL & MIN SAL OF THE EMPLOYEE IN EACH DEPT IF THE EMPLOYEE NAME STARTS WITH CHARACTER A.
4. Display number of employees working in each dept except the Employee working as analyst.
5. Display number of employees getting commission in each dept.
6. Display the average salary paid to each job.
7. Display the HIREDATE without repetition, i.e unique hire-dates. ( without distinct/set op )
8. Display the salaries without repetition.
9. Display the number of employees working in each department along with the total money spent on salaries, minimum salary, maximum salary and average salary in each department.
10. Display NUMBER OF EMPLOYEES WORKING IN EACH DEPARTEMENT EXCEPT PRESIDENT 
11. Display TOTAL SALARY NEEDED TO PAY ALL THE EMPLOYEES IN EACH JOB
12. Display NUMBER OF EMPLOYEEES WORKING AS MANAGER IN EACH DEPARTMENT
13. Display AVG SALARY NEEDED TO PAY ALL THE EMPLOYEES IN EACH DEPARTMENT EXCLUDING THE EMPLOYEES OF DEPTNO 20
14. Display NUMBER OF EMPLOYEES HAVING CHARACTER 'A' IN THEIR NAMES IN EACH JOB
15. Display NUMBER OF EMPLOYEES AND AVG SALARY NEEDED TO PAY THE  EMPLOYEES WHO SALARY IN GREATER THAN 2000 IN EACH DEPT
16. Display TOTAL SALARY NEEDED TO PAY AND NUMBER OF SALESMANS 
    
    IN EACH DEPT
    
17. Display NUMBER OF EMPLOYEES WITH THEIR MAXIMUM SALARIES IN EACH JOB

18. Display MAXIMUM SALARIES GIVEN TO AN EMPLOYEE WORKING IN EACH DEPT
    
19. Display NUMBER OF TIMES A SALARIES IS PRESENT IN EMPLOYEE TABLE
20. Display THE REPEATED SALARIES 

---