# Character Functions (Scalar)

---

**Character (or String) Scalar Functions** operate on a single string input and return a single character or numeric value per row. They are used extensively to format, manipulate, and extract substrings.

Common Character Functions:
*   **`UPPER()` / `LOWER()` / `INITCAP()`**: Changes case.
*   **`LENGTH()`**: Returns string length.
*   **`SUBSTR()` / `SUBSTRING()`**: Extracts a portion of a string.
*   **`INSTR()` / `CHARINDEX()`**: Returns the numerical position of a substring.
*   **`TRIM()`**: Removes leading and trailing spaces.

**Syntax Example:**
```sql
SELECT UPPER(name) as name_caps, SUBSTR(phone, 1, 3) as area_code 
FROM customers;
```

---

### Practice Questions

---

1. WAQTD employee names in uppercase.
2. WAQTD employee names in lowercase.
3. WAQTD employee names with only the first letter capitalized.
4. WAQTD the first 4 characters of each employee name.
5. WAQTD the last 2 characters of each employee name.
6. WAQTD employee names along with their length.
7. WAQTD employee names padded to 10 characters using ‘#' on the right.
8. WAQTD employee names padded to 10 characters using ‘#’ on the left.
9. Replace all occurrences of the letter ‘A’ with ‘X’ in employee names.
10. WAQTD employee names that contain the letter ‘A’. 
11. WAQTD employee names where the second character is ‘A’. 
12. WAQTD employee names that contain at least two ‘A’.
13. WAQTD employee names and the position of the letter ‘R'.
14. WAQTD employee names that end with ‘N’ using SUBSTR. 
15. WAQTD employee name and job concatenated with a hyphen ‘-’ . 
16. WAQTD employee name and salary as a single string separated by ‘:’
17. WAQTD employee names enclosed within brackets.
    
    Example:  [ scott ] 
    
18. WAQTD employee names prefixed with “Mr.  “ 
19. WAQTD department name and location combined as deptname(location) .
20. WAQTD employee names where the first and last characters are the same.
21. WAQTD employee names that are palindromes.
22. WAQTD employee names where the third character is a vowel.
23. WAQTD employee names with all vowels replaced by ‘_ ‘.
24. WAQTD employee names and count how many times ‘A’ appears in each name.
25. WAQTD employee names sorted by their length.
26. WAQTD employee names trimmed to 3 characters (first) and converted to lowercase.
27. WAQTD employee names formatted as:
    
    First 2 letters uppercase + remaining lowercase.
    
28. WAQTD employee names where the ASCII value of the first character is greater than 75.
29. WAQTD employee names ordered by the ASCII value of their first character ( desc order ).

# Number functions

---

1. WAQTD employees whose salary is divisible by 500.
2. WAQTD employees whose salary is not divisible by 100.
3. WAQTD employees whose salary squared is greater than 10,000,000.
4. WAQTD employees whose square root of salary is greater than 40.
5. WAQTD department-wise rounded and truncated average salary.