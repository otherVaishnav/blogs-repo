---
title: "Multi-Row (Aggregate) Functions"
description: "Explore the Multi-Row (Aggregate) Functions section."
pubDate: "2025-06-01"
---

<!-- # Multi-Row (Aggregate) Functions -->

---

**Multi-row functions** (also known as Aggregate functions) perform a calculation on a set of rows and return a single summary value. They are frequently used with the `GROUP BY` clause.

Common Aggregate Functions:
*   **`SUM()`**: Returns the total sum of a numeric column.
*   **`AVG()`**: Returns the average value.
*   **`COUNT()`**: Returns the number of rows.
*   **`MAX()` / `MIN()`**: Returns the max/min value in a column.

**Syntax Example:**
```sql
SELECT department, SUM(salary) AS total_payroll 
FROM employees 
GROUP BY department;
```

---

### Practice Questions

1. Display maximum salary given to a manager.
2. Display Total salary given to dept 10.
3. Display number of employees earing more than 1500 in dept 20.
4. Display number of employee having 'E' in their names.
5. Display minimum salary given to the employees working as clerk in Dept 10 or 20 .
6. Display number of employees hired after 1982 and before 1985 into Dept 10 or 30.
7. Display number of employees getting commission.
8. Display maximum salary given to employees if the emp has character 'S' in the name and works as a Manager in dept 10 with a salary more than 1800. 
9. Display NUMBER OF EMPLOYEES GETTING SALARY LESS THAN 2000 IN DEPTNO 10
10. Display TOTAL SALARY NEEDED TO PAY EMPLOYEES WORKING AS CLERK
11. Display AVERAGE SALARY NEEDED TO PAY ALL EMPLOYEES
12. Display NUMBER OF EMPLOYEES HAVING 'A' AS THEIR FIRST CHARACTER
13. Display NUMBER OF EMPLOYEES WORKING AS CLERK OR MANAGER
14. Display TOTAL SALARY NEEDED TO PAY EMPLOYEES HIRED IN FEB
15. Display NUMBER OF EMPLOYEES REPORTING TO 7839 (MGR)
16. Display NUMBER OF EMPLOYEES GETTING COMISSION IN DEPTNO 30
17. Display AVG SAL , TOTAL SAL , NUMBER OF EMPS AND MAXIMUM SALARY GIVEN TO EMPLOYEES WORKING AS PERSIDENT
18. Display NUMBER OF EMPLOYEES HAVING 'A' IN THEIR NAMES
19. Display NUMBER OF EMPS AND TOTAL SALARY NEEDED TO PAY THE EMPLOYEES WHO HAVE 2 CONSICUTIVE L's IN THEIR NAMES.
20. Display NUMBER OF DEPARTMENTS PRESENT IN EMPLOYEE TABLE.
21. Display NUMBER OF EMPLOYEES HAVING CHARACTER 'Z' IN THEIR NAMES.
22. Display NUMBER OF EMPLOYEES HAVING '$' IN THEIR NAMES.
23. Display TOTAL SALARY GIVEN TO EMPLOYEES WORKING AS CLERK IN DEPT 30
24. Display NUMBER OF DISTINCT SALARIES PRESENT IN EMPLOYEE TABLE
25. Display MINIMUM SALARY GIVEN TO THE EMPLOYEES WHO WORK IN DEPT 10 AS MANAGER  OR A CLERK. 

---