# TCL

TCL statements are used to manage the changes made by DML statements 

Types of TCL statements 

1. COMMIT 
2. ROLLBACK
3. SAVEPOINT

---

### 1. COMMIT

→ It is used to make the changes permanent (save) into the database.

Syntax : 

```sql
COMMIT ;
```

→ After commit, changes become permanent, 

---

### 2. Rollback

→ It is used to get back to the latest saved state.

Syntax : 

```sql
ROLLBACK [TO SAVEPOINT_NAME] ; 
```

→ SAVEPOINT is optional. 

→ if SAVEPOINT IS PASSED, the database rollbacks to that point, otherwise it rollbacks to the last COMMIT. 

---

### 3. SAVEPOINT

→ It is used to create a restoration point.

Syntax 

```sql
SAVEPOINT Savepoint_name;
```

1. ROLLBACK AND GO TO THE LATEST COMMIT.
2. INSERT 3 DEPARTMENTS, JUST THE NO AND NAME.
3. CREATE A SAVEPOINT NAMES EMP_THREE.
4. UPDATE THE SALARIES OF EMPLOYEE EARNING MORE THAN 4000 TO 3000.
5. CREATE SAVEPOINT SAL_UPDATES.
6.  DELETE ALL THE EMPLOYEES
7. CREATE SAVEPOINT NO_EMP.