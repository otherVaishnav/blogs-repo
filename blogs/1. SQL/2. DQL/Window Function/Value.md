---
title: "Window Functions: Value"
description: "Explore the Window Functions: Value section."
pubDate: "2025-06-01"
---

<!-- # Value -->

```sql
### Frame START and END

- UNBOUNDED PRECEDING
- N PRECEDING
- CUREENT
- N FOLLOWING
- UNBOUNED FOLLOWING
```

1. WAQTD each employee’s name and the previous employee’s salary.
    
    ```sql
    -- LAG => 1 
    -- FIRST_VALUE => ROWS BETWEEN 1 PRECIDING AND CURRENT 
    		LAG(SAL,1)
    		
    FIRST_VALUE(SAL) OVER( 
    		ORDER BY NULL 
    		ROWS BETWEEN 1 PRECIDING AND CURRENT ROW
    )
    ```
    
2. WAQTD each employee’s name and the next employee’s salary.
3. For each employee, WAQTD the first employee’s name in the company.
4. For each employee, WAQTD the last employee’s name in the company.
5. WAQTD each employee’s name and the second employee’s name overall.

---

1. WAQTD each employee’s name, department, and previous employee in the same department.
2. WAQTD each employee’s name, department, and next employee’s salary in the same department.
3. For each department, WAQTD the first hired employee.
4. For each department, WAQTD the latest hired employee.
5. For each department, WAQTD the third employee by salary.

---

1. WAQTD the salary of the second next employee; if no such employee exists, show the current employee’s salary.
2. WAQTD each employee’s current salary, previous salary, and the difference between them.
3. WAQTD each employee’s current salary, next salary, and the difference between them.
4. WAQTD the minimum salary in the department and calculate how far each employee’s salary is from that minimum.

---

1. WAQTD the second employee name within a moving frame of three rows.
2. WAQTD previous, current, and next employee names in one result.
3. WAQTD the first and last hired employee in each department.
4. For each department, WAQTD employee name, salary, and the range of salary.

---

1. Find employees whose salary is higher than the previous employee’s salary.
2. Find employees whose salary less compared to the next employee.
3. For each department, find the difference between the highest and lowest salary.
4. For each department, WAQTD employee name, salary, and the average salary of the previous two employees.
5. WAQTD the median employee by salary in each department.

---