---
order: 3
---

# Concatenation Operator

---

The **Concatenation Operator** (`||`) or the `CONCAT()` function is used in SQL to combine two or more strings, columns, or expressions together into a single string. 

**Syntax Example:**
```sql
-- Using the || operator (Oracle, PostgreSQL, SQLite)
SELECT first_name || ' ' || last_name AS full_name 
FROM employees;

-- Using the CONCAT() function (MySQL, SQL Server)
SELECT CONCAT(first_name, ' ', last_name) AS full_name 
FROM employees;
```

---

### Practice Questions

1. WAQTD  the details of employee in the format ‘hello <name> how are you ?’
2. WAQTD the details of department in the format ‘<dname> is located at <loc>’
3. WAQTD the employee details in the format ‘<name> is earning <sal> and working as <job>’
4. WAQTD the salgrade details in the format ‘salaries of <grade> is from <losal> to <hisal>’ 
5. Display the employee Name and salary in the format ‘mr. <name> is earning <sal>’
6. WAQTD the employee name and hiredate in the format  ‘<name> was hired on <hiredate>’.