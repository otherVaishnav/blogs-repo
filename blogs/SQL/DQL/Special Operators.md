---
title: "Special Operators"
description: "Explore the Special Operators section."
pubDate: "2025-06-01"
---

<!-- # Special Operators -->


**Special Operators** provide shortcut syntax for common filtering conditions in the `WHERE` clause, making queries easier to write and read.

Key special operators:
*   **`IN (,,,)`**: Checks if a value matches any value in a list or subquery.
*   **`BETWEEN x AND y`**: Selects values within a given range (inclusive).
*   **`LIKE`**: Searches for a specified pattern in a column using wildcards (`%` for zero/more chars, `_` for exactly one char).
*   **`IS NULL`**: Checks if a column value is empty (NULL).

**Syntax Example:**
```sql
SELECT * FROM employees 
WHERE department IN ('HR', 'IT') 
AND salary BETWEEN 4000 AND 8000 
AND name LIKE 'S%';
```

---

### Practice Questions

1. Display THE EMPLOYEES WHOSE COMMISSON IS NULL. 
2. Display THE EMPLOYEES WHO DON’T HAVE A REPORTING MANAGER. 
3. Display THE SALESMAN IN DEPT 30. 
4. Display THE SALESMAN IN DEPT NUMBER 30 AND HAVING SALARY GREATER THAN 1500. 
5. Display THE EMPLOYEES WHOSE NAME STARTS WITH ‘S’ OR ‘A’
6. Display THE EMPLOYEES EXCEPT THOSE WHO ARE WORKING IN DEPT 10 & 20.
7. LIST THE EMPLOYEES WHOSE NAME DOES NOT START WITH ‘S’
8. Display THE EMPLOYEES WHO ARE HAVING REPORTING MANAGERS IN DEPT 10
9. Display THE EMPLOYEES WHOSE COMMISSION IS NULL AND WORKING AS CLERK
10. Display THE EMPLOYEES IN DEPTNO 10 OR 30 WHO DON’T HAVE A REPORTING MANAGER
11. Display THE SALESMAN IN DEPT 30 WITH SAL MORE THAN 2450
12. Display THE ANALYST IN DEPT NUMBER 20 AND HAVING SALARY GREATER THAN 2500
13. Display THE EMPLOYEES WHOSE NAME STARTS WITH ‘M’ OR ‘J’
14. Display THE EMPLOYEES WITH ANNUAL SALARY EXCEPT THOSE WHO ARE WORKING IN DEPT 30. 
15. LIST THE EMPLOYEES WHOSE NAME DOES NOT END WITH ‘ES’ OR ‘R’.
16. DISPLAY ALL THE EMPLOYEE WHO ARE 'SALESMANS HAVING ‘E’ AS THE LAST BUT ONE CHARACTER (second last) IN ENAME BUT SALARY HAVING EXACTLY 4 CHARACTER
17. DISPLAY ALL THE EMPLOYEE WHO ARE JOINED AFTER YEAR 81
18. DISPLAY ALL THE EMPLOYEE WHO HAVE JOINED IN FEB
19. LIST THE EMPLOYEES WHO ARE NOT WORKING AS MANAGERS AND CLERKS IN DEPT 10 AND 20 WITH A SALARY IN THE RANGE OF 1000 TO 3000.
20. LIST THE NAMES AND LOCATION OF THE DEPARTMENTS WHICH ARE LOCATED AT CHICAGO OR NEW YORK AND THERE NAME HAVE ‘A’.

---

---

**In operator**

1. List employees who work in **departments 10, 20, or 30**.
2. Find employees whose job is **in** CLERK OR MANAGER
3. Show employees whose **salary** is 1250 OR 1600 OR 2450.
4. List employees whose ENAME is SMITH OR JONES OR KING.
5. Find employees who received **commissions** of 300, 500, or 1400.
6. List employees whose **empno** is 7369, 7521, 7900.

**NOT IN**

1. List employees who **don’t work** in departments 10 or 20.
2. Show employees whose job is **not in** ('CLERK', 'ANALYST').
3. Display employees whose manager is **not in** (7839, 7698).
4. Find employees whose salary is **not in** (1250, 1600).
5. Show employees whose names are **not in** (’ALLEN', 'SCOTT', 'MARTIN').
6. Display employees who have **not received** commissions in (0, 300, 500).
7. Display employees whose empno is **not in** (7521, 7844, 7934).

**BETWEEN Operator**

1. List employees whose salary is **between 1000 and 3000**.
2. Show employees hired in the year 1981.
3. Display employees whose empno falls in the range **7500 and 7900**.
4. Show employees whose commission is **between 300 and 1500**.
5. Find employees whose job title is **between 'ANALYST' and 'SALESMAN'**
6. Display employees hired between the year 81 and 90.
7. Show employees with salary **between 1250 and 2850**.

---

**IS NULL / IS NOT NULL** 

1. WAQTD name , salary and commission OF THE EMPLOYEE WHO IS NOT EARNING COMM.
2. WAQTD the details of employee who is not earning salary
3. WAQTD details of employees who are getting  commission.
4. WAQTD name , sal and comm of employees who is earning commission.
5. WAQTD details of employees who does not have a manager.
6. WAQTD details of employee who have manager
7. WAQTD employee who have a department.
8. WAQTD the Names of department who have a location.

---

**LIKE Operator**

1. WAQTD employees whose name starts with 'S'.
2. WAQTD employees whose name ends with 'N'.
3. WAQTD employees whose name contains 'AR'.
4. WAQTD employees whose name has second letter 'L'.
5. WAQTD employees whose job title ends with 'MAN'.
6. WAQTD employees whose job has 'MAN' in it.
7. WAQTD employees whose job title starts with ‘MAN'. 
8. WAQTD employees whose names start with 'M' and end with 'R'.
9. WAQTD employees whose names have exactly 5 characters.
10. WAQTD employees whose job title starts with 'A' and ends with 'T'.
11. WAQTD the employees who have ‘%’ in there name.

---