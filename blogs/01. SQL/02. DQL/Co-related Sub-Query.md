---
title: "Co-related Subqueries"
description: "Explore the Co-related Subqueries section."
pubDate: "2025-06-01"
---

<!-- # Co-related Subqueries -->

---

A **Correlated Subquery** is a subquery that depends on the outer query for its values. Unlike a regular subquery which is evaluated once, a correlated subquery is evaluated row-by-row for *each* record processed by the outer query.

**Syntax Example:**
```sql
-- Find employees whose salary is above their specific department's average
SELECT e1.name, e1.salary, e1.department
FROM employees e1
WHERE e1.salary > (
    SELECT AVG(salary) 
    FROM employees e2 
    WHERE e1.department = e2.department
);
```

---

### Practice Questions

1. Display the employees who earn more than the average salary of their department.
2. Display employees whose salary is greater than their manager's salary.
3. Display the employees who joined the earliest in their department.
4. Display the employee names who do not have the minimum salary in their department.
5. Display the employees whose salary is greater than the average salary of all employees with the same job title.
6. Display THE NAME OF EMPLOYEE WHO IS EARNING SALARY MORE THAN ALTEAST ONE EMPLOYEE IN HIS DEPARTMENT.