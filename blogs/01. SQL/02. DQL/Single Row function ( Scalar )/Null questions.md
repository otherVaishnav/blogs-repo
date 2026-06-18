---
title: "Null Handling Functions (Scalar)"
description: "Explore the Null Handling Functions (Scalar) section."
pubDate: "2025-06-02"
---
<!-- # Null Handling Functions (Scalar) -->

---

**Null Handling Functions** assist in dealing with `NULL` values (missing or unknown data) which can otherwise break arithmetic calculations or logic operations.

Common Null Functions:
*   **`NVL(col, value)`** (Oracle) / **`ISNULL()`** (SQL Server): Replaces a null value with a specified substitution.
*   **`COALESCE(val1, val2, ...)`**: Returns the first non-null value in the provided list.
*   **`NULLIF(val1, val2)`**: Returns NULL if both values are equal, otherwise returns the first value.

**Syntax Example:**
```sql
-- Treat a NULL commission as a 0 in calculation
SELECT name, salary + COALESCE(commission, 0) as total_compensation 
FROM employees;
```

---

### Practice Questions

---

1. WAQTD employee names and commission. If commission is NULL, WAQTD 0 .
2. WAQTD employee names and total salary (sal+comm). Handle NULL commission properly.
3. WAQTD employees whose commission is NULL.
4. WAQTD employees whose commission is NOT NULL.
5. WAQTD employee names and replace NULL job values with ‘unknown’. 
6. WAQTD employee names and salary difference from commission (handle NULL).
7. WAQTD employee names and show 100 if commission is NULL, otherwise show commission.
8. WAQTD salary + commission if commission exists , salary only if commission is NULL
9. WAQTD first non-null value among commission, salary, 0.
10. WAQTD employee names and use COALESCE to replace NULL commission with 500.
11. WAQTD employee names and show:
- 'BONUS GIVEN' if commission exists
- 'NO BONUS' otherwise
1. WAQTD employee names where total earning is more that 3000 (handle NULL correctly).
2. Use NULLIF to avoid division by zero while dividing salary by commission.
3. WAQTD employee names and salary divided by commission safely.

---