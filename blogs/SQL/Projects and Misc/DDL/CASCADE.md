# CASCADE

CASCADE is an optional clause used with certain DDL statements to automatically propagate an action from a parent object to dependent child objects. 

Used with : 

- DROP
- DELETE
- UPDATE  ( not in oracle, pk is not expected to change in oracle )

### ON DROP :

→ When dropping a table that is referenced by foreign keys in other tables, Oracle prevents the drop. 

→ Using ’CASCADE CONSTRAINT’  automatically drops the dependent foreign key constraints.

|→ it drops the constraint, not the data. 

```sql
DROP TABLE parent_table CASCADE CONSTRAINT;
```

→ child table will still have the data, the constraint from DDL will be removed. 

### ON DELETE :

→ ‘ON DELETE CASCADE ‘ is specified while adding foreign key. 

→ It automatically deletes child rows when the parent row is deleted.

```sql
CREATE TABLE emp (
    empno NUMBER PRIMARY KEY,
    ename VARCHAR2(20),
    deptno NUMBER,
    CONSTRAINT fk_dept
        FOREIGN KEY (deptno)
        REFERENCES dept(deptno)
        ON DELETE CASCADE | SET NULL 
);

-- OR 
ALTER TABLE emp
ADD CONSTRAINT fk_DEPTNO 
FOREIGN KEY ( DEPTNO ) 
REFERENCES DEPT(DEPTNO)
ON DELETE [ CASCADE | SET NULL ] ;
-- CASCADE REMOVE THE ENTIRE ROW, 
-- SET NULL sets the values of FK to NULL 
```

→ CASCADE can be used along with TRUNCATE also but ORACLE doesn’t support it. 

```sql
TRUNCATE TABLE table_name CASCADE;
```

→ CASCADE  “ON UPDATE” is also not supported in ORACLE 

```sql
-- syntax is same as delete, just replace delete with update
```

→ we can implement the cascading using triggers also ( on update trigger ). 

```sql
CREATE TRIGGER trigger_name 
AFTER | BEFORE 
UPDATE ...
```