---
order: 6
---

# Set Operators

TYPES : 

1. UNION ALL
2. UNION
3. INTERSECT
4. MINUS

1. UNION ALL : 
    
    → It will combine the result table of two queries. 
    
2. UNION : 
    
    → It will combine the result table of two queries. 
    
    → It will remove the duplicate records. 
    
    → arrange the records in ascending order ( first column ). 
    
3. INTERSECT : 
    
    → It will return the same/matching rows from both the result table. 
    
    → It will remove the duplicate records. 
    
    → arrange the records in ascending order ( first column ). 
    
4. MINUS :
    
    → It will REMOVE  the same/matching rows from FIRST the result table. 
    
    → It will remove the duplicate records. 
    
    → arrange the records in ascending order ( first column ). 
    

SYNTAX : 

```sql
FIRST QUERY 
SET OP 
SECOND QUERY;
```

RULES : 

1. The number of columns in both the queries ( SELECT ) must be same. 
2. The datatype of corresponding columns must be same. 

USE SET OPERATORS

---

1. WAQTD names of employees from department 10 combined with names of employees from department 20.
2. List names and sal of employees from department 10 combined with names and sal of employees from department 20, including any duplicates.
3. List sal, hiredate of employees that appear in both department 10 and department 20.
4. List names of employees from department 10 that do not appear in department 20.
5. List department numbers that are present in both the EMP and DEPT tables.
6. List department numbers that are present in the EMP table but do not appear in the DEPT table.
7. List names of employees from department 30 combined with names of employees from department 40, also remove duplicates.
8. List names of employees from departments 10, combined with dept 20, combined with 30 including duplicates.
9. List department names that have no matching employee names.
10. List names of employees that occur in both department 10 and 30.
11. WAQTD unique department numbers from emp table (without using distinct)
12. WAQTD the Combined department numbers from the EMP and DEPT tables. ( without repeatation )
13. WAQTD all department numbers from both EMP and DEPT, including duplicates.
14. WAQTD the department numbers that exist in both EMP and DEPT.
15. WAQTD the department numbers present in DEPT but not used in EMP.
16. WAQTD all unique jobs from EMP combined with all unique department names from DEPT.
17. WAQTD the HIREDATES of employees who salary is greater than 2000 along with all the HIREDATES of employees working in dept 30 (using set operators ).
18. WAQTD the names of employees who are working as clerk but not in the dept 10.
19. WAQTD the employee numbers who are not managers.
20. WAQTD the employee numbers who are managers.
21. WAQTD the job OR name of the department if the job title and department name is same.