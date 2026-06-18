---
order: 7
---

# Single Row function ( Scalar )

---

→ SRF  takes n number of inputs and return n number of outputs

the number of input = number of outputs.

→ It executes row by row.

SRF are broadly categorized in the following types : 

1. Character functions 
2. Number functions
3. Date functions 
4. Conversion functions
5. NULL functions 
6. extras / general / Miscellaneous 

## 1. Character Functions :

Those who accepts character as an input.

1. UPPER ()
    
    → Converts the given string to uppercase.
    
    ```sql
    UPPER('string');
    ```
    
2. LOWER ()
    
    → Converts string to lowercase.
    
    ```sql
    LOWER('string');
    ```
    
3. INITCAP ()
    
    → Capitalizes first letter of each word.
    
    ```sql
    INITCAP('string');
    ```
    
4. LENGTH ()
    
    → Returns the length of the string.
    
    ```sql
    LENGTH('string');
    ```
    
5. SUBSTR ()
    
    → Extracts a substring.
    
    ```sql
    SUBSTR('main_string',start, length);
    ```
    
6. INSTR ()
    
    → Returns position of substring
    
    ```sql
    INSTR('main_string','substring' [,start, occurence])
    ```
    
7. REPLACE ()
    
    → Replaces substring.
    
    ```sql
    REPLACE('string','to_change','new_string');
    ```
    
8. CONCAT ()
    
    → Concatenates two strings.
    
    ```sql
    CONCAT('string_1','string_2');
    ```
    
9. ASCII ()
    
    → Returns ASCII of first character
    
    ASCII : **American Standard Code for Information Interchange**
    
    ```sql
    ASCII('string');
    ```
    
10. CHR ()
    
    → Returns character of given ASCII code.
    
    ```sql
    CHR(n);
    ```
    
11. TRIM()
    
    ```sql
    TRIM( [ BOTH | LEADING | TRAILING ] 'trim_char' FROM 'string');
    ```
    
    → Remove the whitespaces/char from both side.
    
    → used to remove unwanted characters
    
    **LEADING** →  removes characters from the beginning
    
    **TRAILING** → removes characters from the end
    
    **BOTH** (default) → removes from both sides  
    
    **trim_character** → character to remove
    
    **string** → the target string
    
12. LTRIM ()
    
    → Removes whitespace/char from left side.
    
    ```sql
    LTRIM ( 'string' , [char] );
    ```
    
13. RTRIM ()
    
    → Removes whitespace/char from right side.
    
    ```sql
    RTRIM ( 'string' , [char] );
    ```
    
14. LPAD () OR RPAD()
    
    → to add whitespaces/ char on left/right side
    
    → len : is the length after padding. 
    
    ```sql
    LPAD('string', len, 'to_add');
    RPAD('string', len, 'to_add');
    ```

---

## **2. Number/Numeric Functions**

1. CEIL () 
    
    → Rounds a number to next integer ( ≥ )
    
    → Round up
    
    ```sql
    CEIL(N)
    -- 4.1 -> 5 
    -- 4.9 -> 5
    ```
    
2. FLOOR ()
    
    → Rounds a number to previous integer ( ≤ )
    
    → Round down
    
    ```sql
    FLOOR(N)
    -- 4.1 -> 4 
    -- 4.9 -> 4
    ```
    
3. ROUND ()
    
    → Rounds a number to the nearest integer or 
    
    → Rounds to specified decimal places.
    
    → Oracle rounds away from zero
    
    ```sql
    ROUND(N)
    -- 4.1 -> 4
    -- 4.9 -> 5
    ```
    
4. TRUNC () 
    
    → removes the specified number of decimal values 
    
    ```sql
    TRUNC(N [,no_of_decimals])
    ```
    
5. MOD () 
    
    → Returns the remainder
    
    ```sql
    MOD(n,m);
    ```
    
6. POWER ()
    
    →  Raises a number to a power.
    
    ```sql
    POWER(n,m);
    ```
    
7. SQRT () 
    
    → Returns the square root of a non-negative number.
    
    ```sql
    SQRT(N);
    ```
    
8. SIGN ()
    
    → Returns the sign of the number
    
    ```sql
    SIGN(N) 
    -- 0 :  N = 0 
    -- 1 :  N > 0
    -- -1:  N < 0 
    ```
    

## **3. NULL**

1. NVL () 
    
    ```sql
    NVL(EXP1,EXP2)
    -- exp1 : col_name/exp 
    -- exp2 : replacement 
    ```
    
2. NVL2 ()
    
    ```sql
    NVL2(EXP1, IF_NOT_NULL, IF_NULL)
    ```
    
3. NULLIF () 
    
    ```sql
    NULLIF(exp1, exp2 )
    -- if exp1 = exp2 -> return NULL 
    -- otherwise exp1 . 
    ```
    
4. COALESCE ()
    - first not null value.
    
    ```sql
    COALESCE(exp1, exp2, exp3 ,.... )
    ```
    
---

## **4. Date Functions**

1. SYSDATE  / CURRENT_DATE 
2. SYSTIMESTAMP 
3. MONTHS_BETWEEN()
    
    ```sql
    MONTHS_BETWEEN(date1, date2)
    -- SELECT MONTHS_BETWEEN(SYSDATE, DATE '2024-01-01') FROM dual;
    ```
    
4. ADD_MONTHS()
    
    ```sql
    ADD_MONTHS(date, n)
    -- SELECT ADD_MONTHS(SYSDATE, 3) FROM dual;
    ```
    
5. NEXT_DAY()
    
    ```sql
    NEXT_DAY(date, 'DAY_NAME')
    -- SELECT NEXT_DAY(SYSDATE, 'FRIDAY') FROM dual;
    ```
    
6. LAST_DAY()
    
    → last day of the month. 
    
    ```sql
    LAST_DAY(DATE);
    ```
    
7. ROUND (Date)
    
    → Rounds to nearest month/year.
    
    ```sql
    ROUND(SYSDATE, 'MONTH'/'YEAR') 
    ```
    
8. TRUNC (Date)
    
    → Removes time portion.
    
    ```sql
    TRUNC(SYSDATE)
    ```
   
## **5. Conversion Functions**

1. TO_CHAR 
    
    ```sql
    --convert a date, number, or timestamp into a string with a specified format.
    SELECT TO_CHAR(input [, 'format' ] )
    FROM DUAL;
    ```
    
2. TO_DATE
3. TO_NUMBER

## 6. EXTRAS

1. USER
2. UID 

## FORMAT_MODELS:

- YEAR
- YYYY
- YY
- MONTH
- MON
- MM
- DAY
- DY
- DD
- D (day of the week)

---

- HH24
- HH12
- MI
- SS
- 'HH12:MI: SS' OR ‘HH24:MI:SS’

---

1. CASE() :
    
    SYNTAX: 
    
    ```sql
    CASE 
    	WHEN condition_1 THEN 'result_1'
    	WHEN condition_2 THEN 'result_2'
    	.....
    	WHEN condition_N THEN 'result_N'
    	[ELSE 'default_result']
    END
    ```