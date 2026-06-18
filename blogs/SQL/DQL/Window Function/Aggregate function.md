# Aggregate function

1. WAQTD each employee’s name, salary, along with the **total salary of all employees.**
    
    ```sql
    SELECT ENAME, SAL , 
    			SUM(SAL) OVER() AS TOTAL_SAL_ALL_EMP 
    FROM EMP;
    ```
    
2. WAQTD each employee’s name, salary, and the average salary in the same department.
    
    ```sql
    
    ```
    
3. WAQTD each employee’s name and the maximum salary in the company.
4. WAQTD each employee’s name , department no and the minimum salary in that department.
5. WAQTD each employee name along with how many employees are in their department using.

---

1. WAQTD employee name, salary, and a running total of salaries according to empno.
    
    ```sql
    SELECT ENAME, SAL , 
    				SUM(SAL) OVER(
    						ORDER BY SAL 
    				) AS RNG_TOTAL 
    FROM EMP; 
    ```
    
2. WAQTD each employee’s name, salary, and the running average salary up to that employee according to the salary order.
3. WAQTD employee name, salary, and difference between their salary and the average salary.
4. WAQTD employee name, salary, and maximum salary among all employees hired before or on that employee’s hire date.
    
    ```sql
    SELECT ENAME, SAL , HIREDATE, 
    			MAX(SAL) OVER( 
    					ORDER BY HIREDATE ASC 
    			) MX_SAL_SO_FAR
    FROM EMP;
    ```
    
5. WAQTD employee name, salary of the employees who were offered the highest salary in the company when they were hired. 
    
    ```sql
    SELECT *
    FROM ( SELECT ENAME, SAL , HIREDATE, 
    						MAX(SAL) OVER( 
    								ORDER BY HIREDATE ASC 
    						) MX_SAL_SO_FAR
    			 FROM EMP
    ) X
    WHERE SAL = MX_SAL_SO_FAR;
    ```
    
6. WAQTD each employee, show the count of employees hired so far.

---

1. WAQTD each employee’s name, department, and a cumulative total of salaries per department.
2. WAQTD the average salary of employees hired up to that employee’s hire date, per department.
3. WAQTD the highest salary seen so far per department for every employee according to the hiredate. 
4. WAQTD the lowest salary seen so far across the company ordered by EMPNO.
5. WAQTD name, sal and deptno , find how many employees earn less than or equal to the current employee’s salary. 
    
    ```sql
    SELECT ENAME, SAL , DEPTNO , 
    			 COUNT(EMPNO) OVER(
    					 ORDER BY SAL 
    			 )- 1 
    FROM EMP;
    ```