---
title: "TRIGGERS"
description: "Explore the TRIGGERS section."
pubDate: "2025-06-01"
---

<!-- # TRIGGERS -->

→ a stored program that automatically executes when a specified DML event occurs on a table.

BEFORE : Executes before DML affects the row

AFTER : Executes after DML affects the row

flow : 

1. Before trigger 
2. DML operation 
3. After trigger 

```sql
CREATE OR REPLACE TRIGGER trigger_name
BEFORE | AFTER
INSERT | UPDATE | DELETE
ON table_name
[FOR EACH ROW]       
BEGIN
    -- trigger body
END;
---------------
ALTER TRIGGER trigger_name DISABLE;
ALTER TRIGGER trigger_name ENABLE;
```

### Inside triggers :

Allowed:

- DML on other tables
- SET values
- IF / CASE
- CALL stored procedures

Not Allowed:

- Modifying the same table that fired the trigger
- COMMIT / ROLLBACK
- START TRANSACTION

eg.

1. Create a BEFORE INSERT trigger on table emp that sets salary to 0 if a NULL value is inserted into the salary column.
    
    ```sql
    
    ```
    
2. Create an AFTER UPDATE trigger on table emp that inserts emp_id, OLD.salary, NEW.salary, and the current timestamp into a table named emp_salary_audit.
3. Create a BEFORE UPDATE trigger on table orders that automatically recalculates total_amount as quantity multiplied by unit_price.
4. Create a BEFORE INSERT trigger on table students that raises an error if the age value is less than 18 using SIGNAL.
5. Create a BEFORE DELETE trigger on table employees that stores the deleted row details into a table named employees_backup.
6. Create two BEFORE INSERT triggers on table product such that:
    - the first trigger increases the price by 10 percent
    - the second trigger increases the updated price by 5 percent
        
        Ensure the execution order is correct.
        
7. Create a BEFORE UPDATE trigger on table accounts that prevents the balance from becoming negative.
8. Create a BEFORE INSERT trigger on table attendance that automatically sets status to 'PRESENT' when check_in_time is not NULL.
9. Create a BEFORE UPDATE trigger on table emp that allows the update only if NEW.dept_id is equal to OLD.dept_id; otherwise raise an error.
10. Create a BEFORE INSERT trigger on table orders that prevents insertion if the same order_id already exists in the table, without using any constraints.