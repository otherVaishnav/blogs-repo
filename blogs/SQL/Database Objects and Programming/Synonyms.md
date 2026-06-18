---
order: 3
---

# Synonyms

→ SQL Synonyms are database objects that act as aliases for other objects.

→  Think of a synonym as a shortcut or pointer, not a copy.

→ A synonym is a database object that provides an alternate name for another database object to simplify access and hide schema complexity.

---

### Use of Synonyms

1. Hide schema names
2. Separation of application code from database structure
3. Simplify long or ugly object names

⇒ Synonyms do NOT store data

⇒ Synonyms do NOT improve performance.

⇒ They are name mappings only. 

→ If the base object is dropped → the synonym becomes invalid.

---

### Types of Synonyms

1. Private Synonym
    - Owned by a specific user
    - Only visible to that user
        
        ```sql
        Create SYNONYM synonym_name 
        FOR object_name;
        
        DROP SYNONYM synonym_name;
        
        -------------------------------------
        Create SYNONYM emp 
        FOR hr.employees;
        ```
        
2. Public Synonym
    - Accessible to all users
    - Requires DBA privilege
        
        ```sql
        Create PUBLIC SYNONYM synonym_name 
        FOR object_name;
        
        DROP PUBLIC SYNONYM synonym_name;
        
        ----------------------------------------
        Create PUBLIC SYNONYM emp 
        FOR hr.employees; 
        ```
        

---

You can Create synonyms for:

1. Tables
2. Views
3. Sequences
4. Procedures
5. Functions

---

---

1. Create a private synonym named emp_syn for the table EMP.
2. Create a private synonym named dept_syn for the table DEPT.
3. Create a public synonym named emp_pub for the table EMP.
4. Create a synonym named salgrade_syn for the table SALGRADE.
5. Replace an existing synonym emp_syn so that it points to hr.employees.
6. Create a synonym emp_view_syn for a view named EMP_DETAILS.
7. Drop the private synonym dept_syn.
8. Drop the public synonym emp_pub.
9. Create a synonym mgr_syn that references EMP..
10. Drop the synonym emp_view_syn.