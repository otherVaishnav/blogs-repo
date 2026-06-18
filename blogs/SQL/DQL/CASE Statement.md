---
title: "CASE Statement"
description: "Talking about the CASE Statement in SQL."
pubDate: "2025-06-01"
---

---
<!-- # CASE Statement -->


## Types of CASE Statement:

1. Simple case 

→ multiple conditions 

```sql
CASE 
		WHEN <condn> THEN 
				-- STATEMENTS 
		WHEN <condn> THEN 
				-- STATEMENTS 
		WHEN <condn> THEN 
				-- STATEMENTS
		...
		ELSE 
				-- DEFAULT 
END CASE;
```

1. Searched case 
    
    → one expression and then the expected results. 
    
    ```sql
    CASE <expression> 
    		WHEN <result_1> THEN 
    				-- statement 
    		WHEN <result_2> THEN 
    			  --statement 
    		...
    		ELSE 
    			-- default 
    END CASE;
    ```
    

### Questions :

1. Display ENAME, JOB, and a column JOB_CATEGORY:
    - 'Management' → MANAGER, PRESIDENT
    - 'Technical' → ANALYST
    - 'Sales' → SALESMAN
    - 'Clerical' → CLERK
    
    ```sql
    SELECT ENAME, JOB , 
    				CASE 
    						WHEN JOB IN ('MANAGER', 'PRESIDENT') 
    						THEN 'Management'
    						WHEN JOB IN ('ANALYST')
    						THEN 'Texhnical' 
    						WHEN JOB IN ('SALESMAN')
    						THEN 'Sales'
    						WHEN JOB IN ('CLERK') 
    						THEN 'Clerical' 
    				 END as JOB_CATEGORY
    FROM EMP;
    ```
    
2. Display ENAME, SAL, and classify salary:
    - 'Low' → SAL < 1500
    - 'Medium' → 1500–3000
    - 'High' → > 3000
3. Display ENAME, COMM, and show:
    - 'No Commission' if COMM is NULL
    - 'Has Commission' otherwise
4. Display ENAME, HIREDATE, and classify:
    - 'Senior' if hired before 01-JAN-1982
    - 'Mid-Level' if hired in 1982
    - 'Junior' if hired after 1982
5. Display ENAME, DEPTNO, and show:
    - 10 → 'Accounting'
    - 20 → 'Research'
    - 30 → 'Sales'
6. Display ENAME, SAL, and REVISED_SAL:
    - +20% for ANALYST
    - +10% for SALESMAN
    - +5% for others
7. Display ENAME, SAL, COMM, and compute ANNUAL_INCOME:
    - If COMM is NULL → SAL * 12
    - Else → (SAL + COMM) * 12
8. Display ENAME, JOB, and assign BONUS:
    - PRESIDENT → 5000
    - MANAGER → 3000
    - ANALYST → 2000
    - Others → 1000
9. Display ENAME, SAL, and calculate TAX:
    - 30% if SAL > 3000
    - 20% if SAL between 2000–3000
    - 10% otherwise
10. Display ENAME, SAL, COMM, and calculate COMM_PERCENT:
    - If COMM is NULL → 0%
    - Else → (COMM/SAL)*100
11. Display DEPTNO and show:
    - Count of employees earning above 2500
    - Count of employees earning 2500 or below
12. Display DEPTNO and show total salary categorized as:
    - 'High Budget' if total salary > 9000
    - 'Low Budget' otherwise
13. Display JOB and show:
    - Total salary for MANAGER and PRESIDENT combined
    - Total salary for other jobs
14. Display DEPTNO and show:
    - Number of employees hired before 1982
    - Number hired in or after 1982
15. Display DEPTNO and show:
    - Count of employees with commission
    - Count of employees without commission