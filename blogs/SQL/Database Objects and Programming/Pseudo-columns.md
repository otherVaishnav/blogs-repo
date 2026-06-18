---
order: 4
---

# Pseudo-columns

**Pseudocolumns** are the false columns that are present in each and every table  

- They must be called explicitly
- **Pseudocolumns** cannot be seen without calling them explicitly.
- you can select from Pseudocolumns, but you cannot insert, update, or delete their values

### Types of Pseudo columns :

1. ROWID
2. ROWNUM

## 1. ROWID

→ ROWID is an 18-digit address in which the record is present.

KEY POINTS : 

1. ROWID is generated at the time of insertion of records.
2. ROWID is one of the ways to access the records.
3. ROWID is unique & it is not null.
4. ROWID is present for each and every record.
5. ROWID cannot be inserted, updated or deleted
6. ROWID is static in nature.
7. ROWID can be used to identify a record uniquely from the table when there is no key attribute or primary key.

---

## 2. ROWNUM

→ ROWNUM acts as serial number to the result table.

NOTE:

1. ROWNUM is used as record number that is assigned to the result table.
2. ROWNUM is dynamic in nature.
3. ROWNUM is generated at the time of execution.
4. ROWNUM always starts with 1.
5. ROWNUM get incremented after it is assigned.
6. ROWNUM cannot be duplicated & it’s unique.

Q. Fetch ROWNUM ALONG WITH ALL THE DETAILS OF EMP.

Q. Fetch FIRST 3 RECORDS.

Q. Fetch THE 3RD RECORD FROM THE EMP TABLE.

Questions : 

1. Fetch THE NAMES AND SALARY OF FIRST 5 EMPLOYEES.
2. Fetch THE NAMES AND HIREDATE AND COMMISSION OF FIRST 8 EMPLOYEES.
3. Fetch THE NAMES AND JOB OF 5TH EMP.
4. Fetch THE NAMES AND SALARY OF 11TH EMP.
5. Fetch THE NAMES AND JOB AND DEPTNO OF 8TH AND 7TH EMP.

---

---

1. Fetch THE NAMES OF FIRST 7 EMPLOYEE IN THE COMPANY. 
2. Fetch THE NAMES AND SALARY OF EMPLOYEE EARNING MAX SALARY.
3. Fetch THE EMPNO, NAMES AND DEPTNO OF TOP 10 EMPLOYEE EARNING MAX SALARY.
4. Fetch THE DEPARTMENT NUMBER WHICH HAS MAXIMUM NUMBER OF EMPLOYEES.
5. Fetch THE DETAILS OF FIRST 5 EMPLOYEE EARNING TOP 5 SALARIES.