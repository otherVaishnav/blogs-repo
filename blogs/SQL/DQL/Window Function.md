---
order: 19
---

# Window Function

→ Window functions allow us to perform calculations on a set of related rows i.e window without grouping them into one row.   

→ this are Like MRF but, 

number of inputs = number of outputs. 

→ GROUP BY / GROUP FUNCTIONS reduces the number of rows WINDOW FUNCTIONS does not reduce number of rows.

general syntax : 

```sql
function_name( [ col_name/exp ] ) OVER( 
			[ PARTITION BY col/exp ] 
			[ ORDER BY col/exp ]
			[ ROWS/RANGE BETWEEN frame_start AND frame_end ] 
)
```

1. PARTITION BY 
    
     - divides the result set into logical groups. 
    
     - Like GROUP BY but doesn’t reduce the number of rows.
    
2. ORDER BY 
    
    - defines order within the partition. 
    
3. ROWS / RANGE 
    
    - defines the window frame. 
    
    - how many rows before/after current row to include
    

### Types of Window functions

1. Aggregate functions. 
2. Ranking functions.
3. Value functions 

## 1. Aggregate functions

→ Mostly for running analytics  ( running totals, moving averages, cumulative counts, etc. )

→ Aggregates without reducing the number of rows. 

1. MIN
2. MAX
3. SUM
4. AVG
5. COUNT

```sql
MAX(COL_NAME/EXP) OVER (
  [PARTITION BY col_or_expr]
  [ORDER BY col_or_expr]
  [ROWS | RANGE BETWEEN frame_start AND frame_end]
)
-- expression is mandatory 
-- partition by, order by and rows/range is optional 
```

[Aggregate function ](/04advancedqueries/window-function/aggregate-function)

## 2. Ranking functions

→ Assign ranks or sequence numbers to rows within each partition.

→ Order by is mandatory. 

1. ROW_NUMBER  
2. RANK 
3. DENSE_RANK 
4. NTILE 

```sql
-- ROW_NUMBER , RANK , DENSE_RANK 
RANKING_FUNCTION() OVER (
    [PARTITION BY col/exp]
    ORDER BY col/exp
);
-- NTILE
-- n is mandatory. 
NTILE(n) OVER(
		[ PARTITION BY col/exp ] 
		ORDER BY col/exp 
)
```

### ORDER BY is mandatory.

![image.png](Window%20Function/image.png)

[Ranking ](/04advancedqueries/window-function/ranking)

## 3. Value functions

→ Access specific values from other rows within the window frame.

1. FIRST_VALUE 
2. LAST_VALUE 
3. NTH_VALUE 
4. LAG 
5. LEAD 

```sql
-- FIRST_VALUE, LAST_VALUE 
-- col / exp is mandatory 
VALUE_FUNCTION(col/exp) 
OVER ( 
	 [PARTITION BY col_or_expr]
   [ORDER BY col_or_expr]
   [ROWS | RANGE BETWEEN frame_start AND frame_end]
);

-- NTH VALUE, 
-- order by is mandatory while using ROWS/RANGE in OVER 
NTH_VALUE(col/exp , N) 
OVER ( 
		[PARTITION BY col_or_expr]
    [ORDER BY col_or_expr]
    [ROWS | RANGE BETWEEN frame_start AND frame_end]
);

-- LAG , LEAD 
-- ORDER BY IS MANDATORY AND 
-- ROWS/RANGE IS NOT ALLOWED 
VALUE_FUNCTION( col/exp , N [, default_value] )
OVER (
    [PARTITION BY col_or_expr]
    [ORDER BY col_or_expr]
);
```

![image.png](Window%20Function/image%201.png)

### Frame START and END

- UNBOUNDED PRECEDING
- N PRECEDING
- CUREENT
- N FOLLOWING
- UNBOUNED FOLLOWING

[Value ](/04advancedqueries/window-function/value)

---