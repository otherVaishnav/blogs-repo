# DDL

---

Data definition language

→ It is used to define the structure the of a database object.

→ DDL statements are auto-commit,

Types of DDL statements : 

1. CREATE 
2. RENAME 
3. DROP 
4. TRUNCATE
5. ALTER 

---

### 1. CREATE

→ It is used to create database objects ( table, views, users, etc… ) 

Syntax : 

- TABLE
    
    ```sql
    CREATE TABLE TABLE_NAME ( 
    		COL_NAME DATATYPE [ CONSTRAINT ],
    		COL_NAME DATATYPE [ CONSTRAINT ],
    		...
    		COL_NAME DATATYPE [ CONSTRAINT ]
    );
    ```
    
- USER
    
    ```sql
    CREATE USER USER_NAME 
    IDENTIFIED BY PASSWORD;
    ```
    

---

### 2. RENAME

→ It is used to change the name of database objects.

Syntax : 

```sql
RENAME OLD_NAME 
TO NEW_NAME;
```

---

### 3. DROP

→ It is used to delete a database object permanently.

Syntax: 

- TABLE
    
    ```sql
    DROP TABLE TABLE_NAME;
    ```
    
- USER
    
    ```sql
    DROP USER USER_NAME;
    ```
    

→ In oracle, DROP move the table to RECYCLE BIN instead of deleting it permanently so, from here you can either delete the table or recover it.

- FLASHBACK ( to recover the table )
    
    ```sql
    FLASHBACK TABLE TABLE_NAME 
    TO BEFORE DROP; 
    ```
    
- PURGE ( to delete permanently )
    
    ```sql
    PURGE TABLE TABLE_NAME;
    ```
    

---

### 4. TRUNCATE

→ It is used to remove all the records/data from the table permanently (but structure of the table will be their).

Syntax : 

```sql
TRUNCATE TABLE CUSTOMER; 
```

---

### 5. ALTER

→ It is used to modify the structure of the table.

What can we change : 

- add column.
- rename column.
- remove column.
- modify datatype.
- modify constraint.

1. Add Column
    
    ```sql
    ALTER TABLE TABLE_NAME 
    ADD COL_NAME DATATYPE CONSTRAINT
    ```
    
2. Rename Column 
    
    ```sql
    ALTER TABLE TABLE_NAME 
    RENAME COLUMN COL_NAME TO NEW_NAME;
    ```
    
3. Remove column 
    
    ```sql
    ALTER TABLE TABLE_NAME 
    DROP COLUMN COL_NAME;
    ```
    
4. Modify datatype
    
    ```sql
    ALTER TABLE TABLE_NAME 
    MODIFY COL_NAME NEW_DATATYPE;
    ```
    
    →  Column to be modified must be empty to change datatype.
    
5. Modify Constraint 
    - NOT NULL
        
        ```sql
        ALTER TABLE TABLE_NAME
        MODIFY COL_NAME DATATYPE NULL / NOT NULL ;
        ```
        
    - Other Constraints
        
        ```sql
        ALTER TABLE TABLE_NAME 
        ADD CONSTRAINT CON_REF_NAME CONSTRAINT_TYPE(COL_NAME); 
        
        eg.
        -- UNIQUE 
        ALTER TABLE CUSTOMER
        ADD CONSTRAINT UNI_EMAIL UNIQUE(EMAIL); 
        -- CHECK
        ALTER TABLE CUSTOMER
        ADD CONSTRAINT CH_PH CHECK(LENGTH(PH_NUM)=10);
        -- PRIMARY KEY 
        ALTER TABLE CUSTOMER
        ADD CONSTRAINT PK_EMAIL PRIMARY KEY(EMAIL);
        -- FOREIGN KEY 
        -- 1. ADD THE COLUMN IN CHILD TABLE 
        -- 2. MAKE IT FOREIGN KEY 
        ALTER TABLE CUSTOMER
        ADD CONSTRAINT FK_PID FOREIGN KEY(PID) REFERENCES PRODUCTS(PID);
        ```
        
