# Window Functions: Ranking

---

**Ranking Window Functions** assign a sequence or rank number to each row within a partition of a result set.

*   **`ROW_NUMBER()`**: Assigns a unique, consecutive integer starting at 1. Ties receive different numbers.
*   **`RANK()`**: Assigns identical ranks to ties, but skips subsequent ranks (e.g., 1, 2, 2, 4).
*   **`DENSE_RANK()`**: Assigns identical ranks to ties, and does NOT skip subsequent ranks (e.g., 1, 2, 2, 3).

**Syntax Example:**
```sql
SELECT name, department, salary,
       RANK() OVER (PARTITION BY department ORDER BY salary DESC) as rank
FROM employees;
```

---

### Practice Questions

1. WAQTD each employee’s name, salary, and a unique row number (no partition).
2. WAQTD employee name, department, and row number within each department.
3. WAQTD each employee’s name and their rank based on salary (highest salary = rank 1).
4. WAQTD employee name, department, and rank based on salary within that department.
5. WAQTD each employee’s name and dense rank based on salary 
6. What is the difference between RANK and DENSE RANK. 

---

1. WAQTD the difference between RANK() and DENSE_RANK() for employees with duplicate salaries.
2. WAQTD each employee’s RANK, DENSE_RANK, and ROW_NUMBER (side-by-side) ordered by salary .
3. WAQTD employee names and rank them by commission.
4. WAQTD Ranks of  all employees by HIREDATE — earliest hire gets rank 1.

---

1. WAQ to divide all employees into 4 salary groups (quartiles) and display group number.
2. WAQ to divide employees in each department into 2 groups according to salary. 
3. WAQ to create 10 groups based on salary and show which group each employee belongs to.
4. WAQTD department-wise 3 performance bands based on salary.
5. WAQTD employee names and assign bonus category as per salary 
    
    1 = top 20%, 5 = bottom 20% 
    

---

1. WAQTD  the top 3 highest paid employees for each department, 
2. For each department, WAQTD  the second highest paid employee(s).
3. WAQTD  each employee’s rank in their department and also their overall company rank.
4. WAQTD the employees sharing the same salary ranks.
5. WAQTD rank of employees according to the salary and also rank according to the total earning of the employees.
6. Rank employees by HIREDATE and reverse order , highest rank at the top. 
7. WAQTD employees in the top 10% by salary.

---