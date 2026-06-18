---
title: "View"
description: "Explore the View section."
pubDate: "2025-06-01"
---

<!-- # View -->

A view is a **VIRTUAL TABLE** based on the result-table of a SQL query.

It does not store data physically, instead it shows data from one or more tables.

### Advantages of Views :

- Simplifies complex queries.
- Hide table structure
- Reuse logic without repeating SQL.
- Provides column/row-level security.

**syntax:** 

```sql
CREATE [ OR REPLACE ] VIEW VIEW_NAME 
AS
SELECT ...
```

## Types of Views:

1. Simple View  
2. Complex View
3. **Inline View**
4. **Materialized View** (in Oracle)

---

### 1. Simple View

            - Based on a single table.

       - Does not contain functions, group by, etc.

            - Can be updated if the table and view have 1 to 1 relation.

       eg. 

```sql
CREATE VIEW emp_dept_view AS
SELECT empno, ename, deptno
FROM emp;
```

### 2. Complex View

Based on multiple tables, can include joins, aggregations, etc.

- JOIN
- GROUP BY
- DISTINCT
- HAVING
- Aggregate functions
- UNION / UNION ALL
- Subqueries in SELECT
    
    ```sql
    -- eg 
    CREATE VIEW emp_sal_dept_view AS
    SELECT e.empno, e.ename, e.sal, d.dname
    FROM emp e JOIN dept d ON e.deptno = d.deptno
    WHERE e.sal > 2000;
    ```
    

### **3. Materialized View** (in Oracle)

A view which can stores data. 

*Needs to be refreshed to add or update the data.

```sql
CREATE MATERIALIZED VIEW view_name
[ 
  BUILD [IMMEDIATE | DEFERRED]
  REFRESH [FAST | COMPLETE | FORCE]
  ON [COMMIT | DEMAND]
]
AS
SELECT ...
FROM ... ;
```

- **BUILD IMMEDIATE**: Create the view and populates immediately.
- **BUILD DEFERED** : Creates the view **without populating** it initially
- **REFRESH FAST** : Uses **materialized view logs** to refresh only changed rows
- **REFRESH COMPLETE**  : **Rebuilds the entire** materialized view during refresh
- **REFRESH FORCE**  : Oracle will decide.
- **ON COMMIT** : Refreshes the view whenever
- **ON DEMAND**: Refresh is **manual**, via DBMA_MVIEW.REFRESH.
    
    ```sql
    EXEC DBMS_MVIEW.REFRESH('VIEW_NAME');
    ```
    

---

example : 

```sql
CREATE MATERIALIZED VIEW MV_EMP
BUILD IMMEDIATE
REFRESH COMPLETE
ON DEMAND
AS
SELECT empno, ename, sal, deptno
FROM emp;
```

### View Operations :

1. Create a view 
    
    ```sql
    CREATE VIEW VIEW_NAME 
    AS
    SELECT ...
    FROM TABLE_NAME/view_name
    ...
    ```
    
2. View a view  ( just like tables ).
    
    ```sql
    SELECT col_name/exp
    FROM VIEW_NAME;
    ```
    
3. Modifying a View
    
    ```sql
    CREATE OR REPLACE VIEW emp_dept_view 
    AS
    SELECT col_name/exp
    FROM ... ;
    ```
    
4. Dropping a View
    
    ```sql
    DROP VIEW view_name;
    ```
    

### Questions :

### Scott

1. Create a view that shows employee names, department names, and salaries.
2. Create a view showing employees earning more than 3000. 
3. Create a view that displays employee names and their grade from SALGRADE.
4. Create a view that includes employee name, salary, and computed annual salary.
5. Create a view to find the number of employees in each department using a view.
6. Create a view to show managers and their subordinates from the EMP table.

---

---

### HR

1. Create a view EMP_VIEW1 that displays EMPLOYEE_ID, FIRST_NAME, LAST_NAME, and SALARY of all employees.
2. Create a view EMP_SALARY_VIEW that shows employee full name as EMPLOYEE_NAME, and salary as MONTHLY_SALARY.
3. Create a view IT_EMPLOYEES that displays EMPLOYEE_ID, FIRST_NAME, LAST_NAME, JOB_ID of employees who work in the IT department.
4. Create a view EMP_CONFIDENTIAL that hides the salary and commission details.
5. Create a view EMP_DEPT_VIEW that shows employee name, job_id, department_name, and location_id.
6. Create a view EMP_JOB_VIEW that displays employee name, job_title, and salary with aliases NAME, POSITION, and PAY.
7. Create a view EMP_LOCATION_VIEW showing employee name, department name, city, and country name.
8. Create a view EMP_ANNUAL_SALARY that shows employee_id, full_name, and ANNUAL_SALARY.
9. Create a view DEPT_SALARY_SUMMARY showing DEPARTMENT_NAME, TOTAL_EMPLOYEES, and AVG_SALARY.
10. Create a view EMP_UPDATE_VIEW to display EMPLOYEE_ID, FIRST_NAME, LAST_NAME, and SALARY.
11. Create a view EMP_JOB_JOIN_VIEW joining EMPLOYEES and JOBS.
12. Create a view EMP_READONLY_VIEW to show EMPLOYEE_ID, NAME, and DEPARTMENT_ID.
13. Create a view HIGH_AVG_DEPT that displays DEPARTMENT_NAME and AVG_SALARY for departments where the average salary is above 12000.
14. Create a view TOP_PAID_EMPLOYEES showing EMPLOYEE_ID, NAME, and SALARY of employees whose salary is greater than the average salary of their department.
15. Create a view EMP_HIGH_SALARY that only includes employees with SALARY > 10000.