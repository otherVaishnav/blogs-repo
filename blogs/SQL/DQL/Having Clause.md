---
order: 10
---

# Having Clause

It is used to filter the groups.

```sql
 SELECT GROUP_FUNCTION/ GROUP_BY_EXPRESSION 
 FROM TABLE_NAME 
 [ WHERE < FILTER_CONDITION > ] 
 GROUP BY COLUMN_NAME/ EXPRESSION 
 HAVING<GROUP_FILTER_CONDITION>; 
 
 ------------------------------------
 ## The order of execution : 
	1. FROM
	2. WHERE     (ROW BY ROW)  -- optional
	3. GROUP BY (ROW BY ROW)  -- mandatory
	4. HAVING   (GROUP BY GROUP)
	5. SELECT   (GROUP BY GROUP)
```

## WHERE

1. Where clause is used to
Filter the records.
2. Where clause executes row by
row.
3. In Where Clause we cannot Use
MRF ()
4. Where clause executes before
Group by clause.

## HAVING

1. Having clause is used to
Filter the groups.
2. Having clause executes
Group by group
3. Can use MRF ().
4. Having clause executes After
group by clause.

1. Display number of employees working in each Dept if there are at least 3 employees in each dept.
2. Display the SAL that are repeated.
3. Display SAL that are repeated exactly twice.
4. Display department number and number of employees working in the dept if the department have At least 2 emp who have Character 'A' or 'S' in their names
5. Display job and total salary of each job , if the total salary of each job is greater than 3000.
6. Display job and total salary of the employees working in the job if the employee is earning more than 1500 and the avg salary of the job should be more than 1500.
7. Display DEPTNO AND NUMBER OF CLERKS WORKING IN DEPT IF THE DEPARTMENT HAVE ATLEAST 2 CLERKS. 
8. Display DEPTNO AND TOTAL SALARY NEEDED TO PAY THE SALESMAN IF THE DEPT HAVE ATLEAST 3 SALESMAN. 
9. Display NUMBER OF EMP EARNING SAL MORE THAN 1200 IN EACH JOB AND THE TOTAL SAL NEEDED TO PAY THE JOB EXCEEDS 3500.
10. Display DEPTNO AND NUMBER OF MANAGERS WORKING ONLY IF THERE ARE 2 EMP WORKING IN EACH DEPT AS MANAGER .
11. Display JOB AND MAX SAL OF EMP IN EACH JOB IF THE MAX SAL EXCEEDS 2600
12. Display THE SALARIES WHICH ARE REPEATED IN EMP TABLE
13. Display THE HIREDATE WHICH ARE DUPLICATED IN EMP TABLE
14. Display AVG SALARY OF EACH DEPT IF AVG SAL IS LESS THAN 3000
15. Display MIN AND MAX SALARIES OF EACH JOB IF MIN SAL IS MORE THAN 1000 AND MAX SAL IS LESS THAN 5000.
16. Display THE NUMBER OF EMPLOYEE WHO WERE HIRED ON THE SAME DATE AND IN THE SAME DEPARTMENT. 
17. Display THE NUMBER OF ALL THE EMPLOYEES WHO ARE WORKING IN THE SAME DEPARTMENT AND EARNING SAME SALARIES.
18. Display THE JOB , DEPTNO ALONG WIHT NUMBER OF ALL THE EMPLOYEES WHO ARE WORKING IN THE SAME JOB AND IN THE SAME DEPARTMENT.
19. Display THE JOB WHICH HAVE MORE THAN 3 EMPLOYEES. 
20. Display THE NAME AND SALARIES OF ALL THE EMPLOYEES, IN ASCENDING ORDER OF NAME.