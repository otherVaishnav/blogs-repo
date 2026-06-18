---
order: 13
---

# Joins

### 1. Cross / Cartesian JOIN.

- Cartesian / Cross join the records of table 1 will merge with all the records of table 2.

Syntax: 

```sql
-- ANSI 
SELECT COL_NAME / EXP 
FROM TABLE_1 
CROSS JOIN TABLE_2;
```

NOTE:

1. The no. of column present in result table will be equal to the summation of column present in both the table.
2. The no. of records present in result table will be equal to the product of ROWS present in both the table.

Questions : 

1. Fetch THE NAME AND DEPARTMENT NAME OF THE EMPLOYEE. 
2. Display all combinations of employees and departments.
3. List all EMPNO and LOC combinations.
4. Count total rows returned by the cross join of EMP and DEPT.
5. WAQDT the details from a CROSS JOIN of EMP AND DEPT and sort the result by ENAME.
6. Fetch the list showing every department name combined with every employee name starting with ‘S’.
7. Fetch THE DEPARTMENT NUMBERS FROM employee and department TABLE.
8. Show job titles with all combinations of department names.
9. Generate a list of all possible EMPNO and DEPTNO pairings.
10. Show all combinations of employee names and salary grades.
11. Create a Cartesian product between EMP and SALGRADE tables.
12. Pair each department with every possible hire date from EMP.

---

### 2. INNER / EQUI JOIN

- Returns **only the matching rows** from both tables based on the **join condition.**

```sql
-- ANSI SYNTAX
SELECT COL_NAME/EXP
FROM TABLE_1 
INNER JOIN TABLE_2 
ON <JOIN_CONDITION>;
```

JOIN CONDITION : used to specify the condition on which you want to join the tables.

1. Fetch THE DETAILS OF THE EMPLOYEE ALONG WITH THE DEPARTMENT.
2. Fetch NAME OF THE EMPLOYEE AND HIS DEPARTMENT NAME.
3. Fetch THE NAME, SALARY AND LOCATION OF THE EMPLOYEE WHO ARE EARNING MORE THAN 2000.
4. Fetch NAME , DEPARTMENT NAME AND HIREDATE OF EMPLOYEE WHO ARE WORKING IN RESEARCH DEPARTMENT AND HIRED BEFORE 1987.
5. Fetch ENAME AND DEPTNO AND DNAME OF EMPLOYEES WHO ARE WORKING AS MANAGER. 
6. Fetch ENAME AND SALARY ALONG WITH DEPT DETAILS OF EMPLOYEES WHO ARE WORKING IN DEPT 10.
7. Fetch THE NAME OF DEPARTMENT AND THE NUMBER OF EMPLOYEES WORKING IN THEM.
8. Fetch THE NAMES OF EMPLOYEE WORKING IN RESEARCH DEPARTMENT.
9. Fetch THE AVERAGE SALARY OF  EMPLOYEES WHO’S LOCATION IS DALLAS.
10. DISPLAY THE NAME , SAL, DEPARTMENT NAME AND LOCATION OF EMPLOYEES IN THE ASCENDING ORDER OF ENAME.
11. Fetch THE NAME AND SALARY AND DEPARTMENT NAME OF EMPLOYEE WHO ARE EARNING MORE THAN 1500.
12. Fetch THE NAME , DEPARTMENT NAME AND SALARY OF EMPLOYEE WHO ARE HIRED AFTER  01-JAN-1985.
13. Fetch THE DEPARTMENT NAME, AVG SALARY AND THE MAX SALARY OF EMPLOYEES WORKING IN THAT DEPARTMENT.
14. Fetch ENAME, DNAME for employees working in department numbers 10 or 30.

Note : 

- Filters out unmatched rows.
- Join condition must be specified using ON ( ANSI ) or WHERE ( oracle ).
- **Filter nulls/unmatched records by default.**

---

## 3. OUTER JOIN

- IT IS USED TO FETCH UNMATCHED RECORDS ALONG WITH MATCHING RECORDS
    
    ### Types of Outer join
    
    - LEFT OUTER JOIN
    - RIGHT OUTER JOIN
    - FULL OUTER JOIN

### 1. LEFT OUTER JOIN

1. → It will fetch the matching records from both the table and unmatched records form LEFT TABLE. 

```sql
-- ANSI 
SELECT col_name / exp
FROM table_1 
LEFT JOIN table_2
ON <JOIN_CONDITION>;

-- ORACLE 
SELECT col_name / exp
FROM table_1, table_2
WHERE table_1.COL_NAME = table_2.COL_NAME(+);
```

### 2. RIGHT OUTER JOIN

1. → It will fetch the matching records from both the table and unmatched records form RIGHT TABLE. 

```sql
-- ANSI 
SELECT col_name / exp
FROM table_1 
RIGHT JOIN table_2
ON <JOIN_CONDITION>;

-- ORACLE  
SELECT col_name / exp
FROM table_1, table_2
WHERE table_1.COL_NAME(+) = table_2.COL_NAME;
```

Questions:

1. Fetch all the details of departments and their employees, including departments with no employees.
2. Fetch department names and employee names, even if no employee exists.
3. Fetch all DEPT locations with the employees working there.
4. Fetch DEPTNOs and matching EMPNOs, including departments without any employee.
5. Fetch department names and job roles if any assigned.
6. Fetch hiredates  of employees and department name ( or NULL ) 
7. Fetch all departments and total number of employees if present. ( count for operations department should be 0 ). 
8. Fetch DEPTNO and ENAME, including DEPTNOs without employees.
9. Fetch departments if they have a MANAGER working in it.
10. Fetch all department names with average salary if any employee exists.

### 3. FULL OUTER JOIN

- It will return all matching records from both table, and unmatched records from both table.

```sql
-- ANSI 
SELECT col_name / exp  
FROM table_1 
FULL JOIN table_2
ON <JOIN_CONDITION>; 
```

Questions : 

1. Fetch employee names and department names, including unmatched records.
2. Fetch employee and department data where either may be missing.
3. Fetch all employee names and department locations.
4. Fetch  employee names and department names for all, including those without matches.
5. Fetch  EMPNO and DNAME for all combinations including NULLs.
6. Fetch  employees without departments and departments without employees.
7. Fetch  EMP and DEPT data for all valid and invalid mappings.
8. Fetch  EMP's ENAME and DEPT's LOC even if there’s no match.
9. Fetch  employee names with department numbers or NULL.
10. Fetch  departments with or without employees.
11. Fetch  employees AND LOCATION IF EXISTS who are not assigned to any department.
12. Fetch  all EMP and DEPT data with unmatched entries clearly visible.
13. Fetch unmatched employees and unmatched departments in one query.
14. Fetch all hire dates and department locations together.
15. Fetch all job titles with all department names. 

### Natural Join

- Only ANSI Syntax is there.

```sql
-- ANSI 
SELECT col_name/exp
FROM table_1
NATURAL JOIN table_2;
```

→ It will show two behavior :

1. CROSS JOIN : when there is no common/matching  column in two tables.
2. INNER JOIN  : when there is a common//matching  column. 

Questions

1. Use NATURAL JOIN to show EMP and DEPT details.
2. Display employee name and department name using NATURAL JOIN.
3. Show ENAME, JOB, LOC using EMP and DEPT natural join.
4. Join EMP and DEPT with NATURAL JOIN and list all fields.
5. Use NATURAL JOIN to get ENAME and DEPTNO.
6. Display DNAME and JOB using EMP and DEPT.
7. List employees and department locations using NATURAL JOIN.
8. Show employee details along with department location.(if possible).
9. Display ENAME, SAL, LOC, DNAME using NATURAL JOIN.
10. Use NATURAL JOIN to display EMP and SALGRADE details.

---

## 5. Self Join.

→ Joining a table to itself.

→ we create 2 copies of the same table and perform join on them.

```sql
-- ANSI 
SELECT COL_NAME / EXP 
FROM table_name A1 
JOIN table_name A2
ON A1.COL_NAME = A2.COL_NAME; 

-- ORACLE 
SELECT COL_NAME / EXP 
FROM table_name A1, table_name A2
WHERE A1.COL_NAME = A2.COL_NAME;
```

Questions : 

1. Fetch DETAILS OF THE EMPLOYEE AND THEIR MANAGER.
2. Fetch NAME OF THE EMPLOYEE AND HIS MANAGER.
3. Fetch NAME OF THE EMPLOYEE AND HIS SALARY ALONG WITH MANAGER NAME & SALARY.
4. Fetch ename , manager's name along with their deptno If employee is working as clerk.
5. Fetch ename and manager's name along with their job if emp and manager are working for same designation .
6. Fetch ename, salary, manager's name, manager's salary If manager earns more than employee. 
7. Fetch ename and manager's name along with manager's commission if manager earns commission.
8. Fetch NAME OF THE EMPLOYEE AND MANAGER'S DESIGNATION IF MANAGER WORKS IN DEPT 10 OR 20
9. Fetch THE NAME OF MANAGERS AND NUMBER OF EMPLOYEES WORKING UNDER HIM.
10. Fetch EMP NAME AND HIS HIREDATE ALONG WITH  MANAGER'S HIREDATE IF EMPLOYEE WAS HIRED BEFORE 1982.
11. Fetch EMP NAME AND MANAGER'S COMM IF EMPLOYEE WORKS AS SALESMAN AND MANAGER WORKS IN DEPT 30
12. Fetch EMP NAME AND MANAGER NAME AND THEIR SALARIES IF EMPLOYEE EARNS MORE THAN MANAGER
13. Fetch EMP NAME AND HIREDATE , MANAGER NAME AND HIREDATE IF MANAGER WAS HIRED BEFORE EMPLOYEE
14. Fetch EMP NAME AND MANAGER NAME IF MANAGER IS WORKING AS ACTUAL MANAGER.   
15. Fetch EMP NAME AND MANAGER NAME ALONG WITH THEIR ANNUAL SALARIES IF EMPLOYEE WORKS IN DEPT 10 , 20 AND MANAGER'S SAL IS GREATER THAN EMPLOYEES SALARY.
16. Fetch EMPLOYEE'S NAME AND MANAGER'S DESIGNATION FOR ALL THE EMPLOYEE
17. Fetch EMPLOYEE'S NAME AND MANAGER'S SALARY FOR ALL THE EMPLOYEES IF MANAGER'S SALARY ENDS WITH 50.
18. Fetch THE NAME OF EMPLOYEE, HIS MANAGER’S NAME AND HIS MANAGER’S MANAGER NAME.

---

# Nested Joins

→ USED TO JOIN MORE THAN 2 TABLES. 

```sql
-- ANSI 
SELECT COL_NAME / EXP
FROM TABLE_1 
JOIN_TYPE TABLE_2 ON <JOIN_CONDITION>
JOIN_TYPE TABLE_3 ON <JOIN_CONDNTION>
JOIN_TYPE TABLE_4 ON <JOIN_CONDITION> 
			....
;

-- ORACLE 
SELECT COL_NAME/ EXP 
FROM TABLE_1, TABLE_2, TABLE_3,....
WHERE <JOIN_CONDTION> AND <JOIN_CONDTION> AND  .....(N-1);
```

1. Fetch THE FIRST NAME AND LAST NAME OF ALL THE EMPLOYEES
2. Fetch THE FIRST NAME OF EMPLOYEE AND DEPARTMENT NAME
3. Fetch THE FIRST NAME OF EMPLOYEE AND DEPARTMENT NAME AND CITY OF THE DEPARTMENT. 
4. Fetch THE FIRST NAME , NAME OF CITY AND THE NAME OF THE COUNTRY
5. Fetch THE NAME OF DEPARTMENT AND THE JOB TITLES.
6. DISPLAY THE COUNTRIES , REGION THE COUNRTY IS PERSENT IN AND THE CITIES PERSENT IN THE COUNTRY.
7. COUNT THE NUMBER OF DEPARTMENTS PRESENT IN ALL COUNTRYS. 
8. Fetch THE DEPARTMENTS WHICH HAVE MORE THAN 14 EMPLOYEES
9. Fetch THE FIRST NAME OF EMPLOYEE ARRANGED ACCORDING TO THERE JOB TITLE
10. Fetch THE FIRST NAME OF EMPLOYEE AND ALL HIS PREVIOUS JOB TITLES 
11. Fetch THE FIRST NAME AND LAST NAME OF EMPLOYEE ALONG WITH THE DEPARTMENTS THAT THE EMPLOYEE USED TO WORK. 
12.  Fetch THE NAME OF REGIONS AND THE NUMBER OF COUNTRIES PRESENT IN THEM
13. Fetch THE CITY AND THE DEPARTMENTS PRESENT THERE IN DESCENDING ORDER OF CITY.
14. Fetch THE NAME OF DEPARTMENT AND THE NUMBER OF EMPLOYEES IF THE DEPARTMENT HAVE MORE THAN 10 EMPLOYEES.

---

---

---