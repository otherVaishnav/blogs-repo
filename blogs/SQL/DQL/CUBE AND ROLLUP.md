---
order: 16
---

# CUBE AND ROLLUP

→ Used along with the group by clause, 

→ Both are extension to the group by clause. 

→ They can be used to perform aggregation on the combination of grouped columns. 

### CUBE :

→ CUBE produces all combinations of groupings, including subtotals for each combination and a grand total.

→ 2^n rows

→ multidimensional analysis, where you need to see the aggregate for all combinations of the grouped columns

Syntax: 

```sql
SELECT col_name/exp
FROM table_name
WHERE <condition>
GROUP BY CUBE(col_1,col_2,col_3,...)
..

GP BY : col_1, col_2, col_3
while using cube : 2^n rows
CUBE  : col_1, col_2, col_3       
				col_1, col_2,   X 
				col_1,   X  , col_3
				col_1,   X  ,   X 
				X    , col_2, col_3
				X    , col_2,   X 
				X    ,   X  , col_3 
				X    ,   X  ,   X
				

```

### Rollup :

→ Finds the sub totals and grand totals of the grouped columns and then successively rolling up to higher level. 

→ ROLLUP produces subtotal and grand total only for each hierarchical level (one level at a time)

→ used when you have a hierarchy of data

```sql
SELECT col_name/exp
FROM table_name
WHERE <condition>
GROUP BY ROLLUP(col_1,col_2,col_3,...)
..
/*
GP : col_1, col_2, col_3
ROLLUP : col_1, col_2, col_3          -> total 
				 col_1, col_2,   X            -> subtotals 
				 col_1,   X  ,   X            -> subtotals 
				 X    ,   X  ,   X            -> grand total
```

GROUPING() : 

→ tells you whether the column is real or a result of combination. 

```sql
0 : actual data, real.
1 : result of combination. 
```

GROUPING_ID() : 

→ shows which columns are aggregated.

→ It combines multiple GROUPING() values into one number. 

→ USES BINARY LOGIC : 

| GROUPING(deptno) | GROUPING(job) | GROUPING_ID(deptno, job) |
| --- | --- | --- |
| 0 | 0 | 0  - details  |
| 0 | 1 | 1  - dept total |
| 1 | 0 | 2 - job total |
| 1 | 1 | 3 - grand total |

## CUBE assignment :

---

### SCOTT :

1. Write a query to display total salary by DEPTNO and JOB using GROUP BY CUBE.
2. Display count of employees by JOB and DEPTNO using CUBE.
3. Show sum of SAL grouped by DEPTNO only, JOB only, and both together using a single query.
4. Find average salary by JOB and DEPTNO including all subtotal combinations.
5. Display salary totals by DEPTNO, JOB, and LOC (join with DEPT) using CUBE.
6. Using GROUP BY CUBE (DEPTNO, JOB) , filter the result to show only subtotal rows (exclude detailed rows).
7. Write a query that shows detailed rows,subtotals, grand total of JOB and SALARY. 
8. Using CUBE, calculate total salary and total commission together by DEPTNO and JOB.

### HR :

1. Display total salary by DEPARTMENT_ID and JOB_ID using CUBE.
2. Count employees by JOB_ID and DEPARTMENT_ID including all subtotals.
3. Show average salary using GROUP BY CUBE(JOB_ID, DEPARTMENT_ID).
4. Join EMPLOYEES and DEPARTMENTS and show salary totals by:
    
    department
    job
    both
    grand total
    
5. Display only the subtotals of THE SALARY AND DEPTARMTN_ID.
6. Display salary totals by DEPARTMENT_NAME and CITY using CUBE.
7. return only: (DEPARTMENT_ID, JOB_ID)
    
    department-level totals
    job-level totals (exclude grand total and detail rows).
    
8. Create a single query using CUBE that replaces all of the following:
    
    total salary by department
    total salary by job
    total salary by department & job
    overall salary total.
    

---

---