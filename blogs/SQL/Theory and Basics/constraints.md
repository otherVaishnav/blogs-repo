# constraints

→ rules assigned to columns. 

1. UNIQUE
    - Prevents duplicate values in a column.
    - Allows NULL values.
    - A column can have multiple NULLs, but all non-NULL values must be unique.
    
2. NOT NULL
    - Prevents NULL values in a column.
    - Ensures a value must be provided for every row.
    
3. CHECK
    - Used to enforce additional validation rules on column data.
    
    Syntax:
    CHECK (condition)
    
    - If the condition evaluates to TRUE, the value is accepted.
    - If the condition evaluates to FALSE, the value is rejected.
    - The condition must be a boolean expression.
    
4. PRIMARY KEY
    - Uniquely identifies each record in a table.
    
    Characteristics:
    
    - Does not allow duplicate values (UNIQUE).
    - Does not allow NULL values (NOT NULL).
    - Implicitly creates a UNIQUE index.
    - A table can have only one PRIMARY KEY.
    - Can be defined on a single column or multiple columns (composite key).
    
5. FOREIGN KEY
    - Used to establish a relationship between two tables.
    - Enforces referential integrity.
    
    Characteristics:
    
    - Allows duplicate values.
    - Allows NULL values.
    - A table can have multiple FOREIGN KEY constraints.
    - A FOREIGN KEY column references a PRIMARY KEY or UNIQUE key
    in the parent table.
    - Defined in the child table.
    - Also known as a Referential Integrity Constraint.
6. DEFAULT :