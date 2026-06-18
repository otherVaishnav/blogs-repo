---
order: 8
---

# Stored Procedures

---

A **Stored Procedure** is a compiled, pre-saved block of SQL and procedural code that handles complex operations, robust business logic, and multiple sequential transactions.

### Why use Procedures?
- **Performance**: The execution plan is cached upon compilation, making subsequent calls much faster.
- **Security**: You can grant users permission to run the procedure without giving them raw access to the underlying tables.
- **Transaction Control**: Unlike Functions, Procedures allow you to use `COMMIT` and `ROLLBACK` inside them.
- **DML Operations**: Procedures are designed to handle `INSERT`, `UPDATE`, and `DELETE` statements.

**Syntax Example:**
```sql
-- Creating the procedure with input (IN) parameters
CREATE OR REPLACE PROCEDURE FireEmployee(emp_id_in IN INT) 
IS
BEGIN
    DELETE FROM employees WHERE id = emp_id_in;
    COMMIT;
END;
/ 

-- Executing the procedure from an application or terminal
EXECUTE FireEmployee(105);
```

---

### Notes & Questions

A stored procedure is a database object containing executable code (logic + SQL) to perform specific tasks.

→ It's compiled once and stored in the DB.

**→ Procedures might or might not return an output** 

→ It can be executed Independently : 

Executed using 

*→* CALL (MySQL) 

→ EXEC (SQL Server / Oracle)

→ Can contain control flow (IF, LOOP, WHILE), variables, cursors, and error handling

```sql
CREATE OR REPLACE PROCEDURE procedure_name
(
    agr_1 IN datatype,
    arg_2 OUT datatype,
    agr_3 IN OUT datatype
)
IS
    -- variable declarations
BEGIN
    -- executable statements
EXCEPTION
    -- exception handling
END procedure_name;
/
```

IN → input (default) 

OUT → output 

IN OUT → same value as input and output 

---

### To view the Procedure / Trigger / Functions :

→ USER_SOURCE table stores the stored objects owned by the current user

![image.png](Procedures/image.png)

```sql
-- use the name of the object you want to display
SELECT TEXT
FROM USER_SOURCE 
WHERE NAME = 'PROCEDURE_NAME | FUNCTION_NAME | TRIGGER_NAME ';
```

### Assignment Questions

1. Create a procedure ADD_EMPLOYEE that inserts a new employee into the EMP table.
IN Parameters: empno, ename, job, hiredate, sal, deptno.
    
    ```sql
    -- INSERT INTO
    CREATE OR REPLACE PROCEDURE ADD_EMPLOYEE 
    ( 
    	empno IN NUMBER, 
    	ename IN VARCHAR, 
    	job IN VARCHAR, 
    	hiredate IN DATE, 
    	sal IN NUMBER, 
    	deptno IN NUMBER 
    )	
    IS 
    BEGIN 
    		INSERT INTO EMP(empno, ename, job, hiredate, sal, deptno)
    		VALUES (empno, ename, job, hiredate, sal, deptno);
    		DBMS_OUTPUT.PUT_LINE('DATA INSERTED');
    END ADD_EMPLOYEE;
    
    ```
    
2. Create a procedure UPDATE_SALARY that increases the salary of a given employee by a 10 percentage.
    
    ```sql
    -- IN Parameters: empno.
    CREATE PROCEDURE UPDATE_SALARY 
    ( EMP_NO IN NUMBER ) 
    AS BEGIN 
    		UPDATE EMP 
    		SET SAL = SAL*1.1 
    		WHERE EMPNO = EMP_NO;
    		DBMS_OUTPUT.PUT_LINE('UPDATED');
    END UPDATE_SALARY;
    ```
    
3. Create a procedure DELETE_EMP that deletes an employee from EMP by empno.
    
    ```sql
    -- IN Parameters: empno.
    CREATE PROCEDURE DELETE_EMP 
    ( EMP_NO IN NUMBER ) 
    AS BEGIN 
    		DELETE FROM EMP
    		WHERE EMPNO = EMP_NO;
    END DELETE_EMP;
    ```
    
4. Create a procedure that takes deptno and a dept_name as input and updates the name of department in the dept table using deptno. 
    
    ```sql
    CREATE PROCEDURE UPDATE_DNAME 
    ( DEPT_NO IN NUMBER,
    	DEPT_NAME IN VARCHAR
    ) 
    IS 
    BEGIN 
    		UPDATE EMP
    		SET DNAME = DEPT_NAME
    		WHERE DEPTNO = DEPT_NO;
    END UPDATE_DNAME;
    ```
    
5. Create a procedure that inserts a row into the BONUS table for a given employee ( ename as input) .
    
    ```sql
    CREATE OR REPLACE PROCEDURE INSERT__BONUS 
    ( EMP_NAME IN VARCHAR ) 
    IS 
    BEGIN 
    		INSERT INTO BONUS(ENAME, JOB, SAL, COMM)
    		SELECT ENAME, JOB , SAL , COMM 
    		FROM EMP
    		WHERE ENAME = EMP_NAME;
    END INSERT__BONUS;
    ```