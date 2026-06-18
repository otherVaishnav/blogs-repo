---
title: "Date Functions (Scalar)"
description: "Explore the Date Functions (Scalar)s section."
pubDate: "2025-06-01"
---

<!-- # Date Functions (Scalar) -->

---

**Date Scalar Functions** manipulate date and time values or extract specific time elements from a timestamp. Date functions vary greatly from database to database.

Common Date Functions (Oracle / standard):
*   **`SYSDATE` / `CURRENT_DATE`**: Returns the current system date/time.
*   **`ADD_MONTHS(date, n)`**: Adds/subtracts months from a date.
*   **`MONTHS_BETWEEN(d1, d2)`**: Returns number of months between dates.
*   **`EXTRACT(MONTH FROM date)`**: Pulls a specific part (year, month, day) from a date.

**Syntax Example:**
```sql
SELECT name, hire_date, EXTRACT(YEAR FROM hire_date) as hire_year 
FROM employees;
```

---

### Practice Questions

---

1. WAQTD current system date.
2. WAQTD current date and time formatted as ‘ DD-MM-YYYY HH24:MI:SS ‘
3. WAQTD employee names and month name of hire.
4. WAQTD employee names and day of the week they were hired.
5. WAQTD employee names hired in the year 1981.
6. WAQTD employees hired in the month of February (any year).
7. WAQTD employees hired on Monday.
8. WAQTD employee names and hire date plus 30 days.
9. WAQTD employee names and hire date minus 7 days.
10. WAQTD employee names and number of days worked until today.
11. WAQTD employee names and number of months worked
12. WAQTD employees hired within the last 60 days.
13. WAQTD employees hired more than 10 years ago.
14. WAQTD employees hired before 01-JAN-1982.
15. WAQTD last day of the month in which each employee was hired.
16. WAQTD employee names and hire date after adding 6 months.
17. WAQTD employee names and hire date after subtracting 3 months.
18. WAQTD employees who worked for more than 240 month
19. Convert hire date to format yyyy/mm/dd.
20. Convert hire date to format dd-mm-yyyy
21. Convert string  ’15-02-26’ into DATE. 
22. WAQTD employees hired in the first quarter of the year.
23. WAQTD employees hired in leap year (if applicable).
24. WAQTD employees hired on the last day of a month.
25. WAQTD employees whose hire anniversary is today (day and month match).

---