---
order: 7
---

# Stored Functions

---

A **Stored Function** (often called a User-Defined Function or UDF) is a compiled block of code that encapsulates procedural logic and **must return a single value** (or a single table result).

Unlike Stored Procedures, Functions are designed specifically to be called inline within a SQL `SELECT` or `WHERE` statement, almost like native scalar functions (e.g., `UPPER()`).

### Key Differences from Procedures:
- **Must Return Data**: A function is required to have a `RETURN` statement.
- **Read-Only**: Stored Functions are strictly prohibited from performing DML operations (`INSERT`, `UPDATE`, `DELETE`). They can only query data.
- **Inline Invocation**: Can be nested directly inside queries.

**Syntax Example:**
```sql
CREATE FUNCTION GetAnnualBonus (salary DECIMAL)
RETURNS DECIMAL
AS
BEGIN
    RETURN salary * 0.15;
END;

-- Invoking the function directly in a query:
SELECT name, GetAnnualBonus(salary) as bonus 
FROM employees;
```

---

### Notes & Questions

A function is a named PL/SQL block stored in the database that must return exactly one value using the RETURN statement

→ functions are primarily designed to compute and return a value.

→ must return exactly one value, RETURN DATATYPE is mandatory

→ Callable in SQL statement. 

```sql
CREATE OR REPLACE FUNCTION function_name
(
    param1 IN datatype,
    param2 IN datatype
)
RETURN return_datatype
IS
    -- declarations
BEGIN
    -- executable statements
    RETURN value;
EXCEPTION
    -- exception handling
END function_name;
/

```

1. Create a function which returns the square of a given number. 
    
    ```sql
    CREATE FUNCTION NUM_SQUARE 
    ( NUM IN NUMBER ) 
    RETURN NUMBER 
    IS BEGIN 
    		RETURN NUM*NUM;
    END NUM_SQUARE;
    ```
    
2. Create a function to generate the annual salary from given salary. 
3. Create a function calculate the age using date of birth 
    
    ```sql
    CREATE FUNCTION GET_AGE(
    		DOB IN DATE
    ) 
    RETURN NUMBER
    IS 
    BEGIN 
    		RETURN FLOOR(MONTHS_BETWEEN(SYSDATE,DOB)/12);
    END GET_AGE;
    ```
    
4. Create a function which return the year of experience from the hiredates. 
    
    ```sql
    CREATE FUNCTION GET_EXPERIENCE(
    		HIRED_ON IN DATE
    ) 
    RETURN NUMBER
    IS 
    BEGIN 
    		RETURN FLOOR(MONTHS_BETWEEN(SYSDATE,HIRED_ON)/12);
    END GET_EXPERIENCE;
    ```
    
5. Create a function which hides the first 6 digits of the given phone number. 
    
    ```sql
    -- 9847123234
    -- ******3234
    CREATE OR REPLACE FUNCTION HIDE_PHONE 
    ( PHONE_NO IN NUMBER ) 
    RETURN VARCHAR 
    IS BEGIN 
    		RETURN LPAD(SUBSTR(PHONE_NO,7),10,'*');
    END HIDE_PHONE;
    ```
    

### MySQL

```sql
DELIMITER $$

CREATE FUNCTION function_name
(
    parameter_name data_type,
    ...
)
RETURNS return_data_type
BEGIN
    -- executable statements
    RETURN expression;
END $$

DELIMITER ;
```