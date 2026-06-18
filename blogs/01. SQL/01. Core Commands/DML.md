---
title: "DML"
description: "Explore the DML section."
pubDate: "2025-06-01"
---

Data manipulation language

→ It is used to Manipulate the data present in the table.

→
DML has 3 statements :

1. INSERT
2. UPDATE
3. DELETE

---

### 1. Insert :

→ It is used to insert a new record in the table.

Syntax :

```sql
INSERT INTO TABLE_NAME [(C1,C2..CN)]
VALUES (V1,V2...VN);

```

- Here, passing column name along with the table name is optional.
- if you want to insert values in all the columns, then no need to pass column names.
    
    ```sql
    INSERT INTO TABLE_NAME
    VALUES (V1,V2...VN);
    
    ```
    
- If you want to insert values in particular columns, then add column name along with table name
    
    ```sql
    INSERT INTO TABLE_NAME(C1,C2..CN)
    VALUES(V1,V2..VN);
    
    ```
    

---

### 2. Update

→ It is used to modify an existing value

Syntax:

```sql
UPDATE TABLE_NAME
SET COL_NAME = NEW_VALUE,
		COL_NAME = NEW_VALUE,..
[ WHERE <FILTER_CONDITION> ] ;

```

→ We can pass multiple columns at once

→ WHERE is optional, if not passed, all the values in the given column will be updated

---

### 3. Delete

→  It is used to remove a particular record from the table

Syntax :

```sql
DELETE FROM TABLE_NAME
[WHERE <FILTER_CONDITION>];

```

→ Where clause is optional.

---

Questions :

1. WAQT update the salary of employee to double their salary if he is working as a manager
2. WAQT change the name of SMITH to SMIITH.
3. WAQT modify the job of KING to 'PRESIDENT'
4. WAQT change name of ALLEN to ALLEN MORGAN .
5. WAQT hike the salary of the employee to 10% . If employees earn less than 2000 as a salesman.
6. WAQT delete the employees who don’t earn commission.
7. WAQ to remove all the employees hired before 1987 in dept 20.
8. Differentiate between TRUNCATE and DELETE statements.
9. WRITE A QUERY TO INSERT 7 DEPARTMENTS IN DEPT TABLE
10. WRITE A QUERY TO UPDATE THE LOCATION OF DEPARTMENT 30 AND 10 TO THAILAND.
11. WRITE A QUERY TO DELETE ALL THE EMPLOYEES
12. WRITE A QUERY TO INSERT 5 EMPLOYEES.
13. WRITE A QUERY TO UPDATE THE SALARY OF ALL EMPLOYEES TO 10,000.
14. Write a query to increment the salaries of employee by 15%. 
15. Remove the employees working as SALESMAN. 

---

---