# EMP - DEPT

1. Create a table named DEPARTMENTS with the following columns:
    - DEPT_ID (Number, primary key)
    - DEPT_NAME (Varchar2(50), not null)
    - LOCATION (Varchar2(50))
2. Create a table named EMPLOYEES with the following columns:
    - EMP_ID (Number, primary key)
    - EMP_NAME (Varchar2(50), not null)
    - SALARY (Number(8,2))
    - DEPT_ID (Number, foreign key referencing DEPARTMENTS table)
    - JOIN_DATE (Date, default as current date)
3. Create a table named PROJECTS with columns:
    - PROJ_ID (Number, primary key)
    - PROJ_NAME (Varchar2(100))
    - START_DATE (Date)
    - END_DATE (Date)
    - BUDGET (Number(10,2))

Constraints:

1. Add the following constraints while creating or later using ALTER:
    - SALARY must be greater than 10000
    - PROJ_NAME should be unique
    - LOCATION should not be null
    - END_DATE must be greater than START_DATE
2. Display all constraints of the EMPLOYEES table using the data dictionary.
3. Drop the foreign key constraint from the EMPLOYEES table, then recreate it with ON DELETE CASCADE.
4. Add a new column PHONE_NUMBER (Varchar2(15)) to the EMPLOYEES table.
5. Modify the data type of SALARY to Number(10,2).
6. Rename column EMP_NAME to FULL_NAME.
7. Drop column PHONE_NUMBER from EMPLOYEES.
8. Rename table PROJECTS to COMPANY_PROJECTS.
9. Truncate all records from the EMPLOYEES table (ensure structure remains).
10. Drop the DEPARTMENTS table completely from the database.
11. Create a table STUDENT with these requirements:
    - Columns: ROLL_NO, NAME, AGE, EMAIL, COURSE
    - ROLL_NO → primary key
    - AGE must be between 18 and 30
    - EMAIL must be unique
12. Create a table COURSE:
    - Columns: COURSE_ID, COURSE_NAME, DURATION, FEES
    - Make COURSE_ID as primary key and COURSE_NAME unique.
13. Add a foreign key in STUDENT table referencing COURSE_ID of COURSE table.
14. Rename the column COURSE_NAME in COURSE to TITLE.