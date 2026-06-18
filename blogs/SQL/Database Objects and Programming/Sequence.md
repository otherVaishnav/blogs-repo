---
title: "Sequence"
description: "Explore the Sequence section."
pubDate: "2025-06-01"
---

<!-- # Sequence -->

---

A **Sequence** is a database object (most prominent in Oracle) that generates a continuous sequence of numeric values. It is commonly used to automatically generate primary key values for new rows.

### Key Characteristics:
- Independent of tables: A single sequence can be used across multiple tables.
- Performance: Generates values extremely fast, stored in cache to minimize disk I/O.
- Behavior: You can specify an increment value, max value, and tell it to cycle back to the start.

**Syntax Example:**
```sql
CREATE SEQUENCE emp_id_seq
START WITH 100
INCREMENT BY 1
NOCACHE
NOCYCLE;

-- Accessing the generated values:
INSERT INTO employees (emp_id, name) 
VALUES (emp_id_seq.NEXTVAL, 'Alice');
```

---

### Notes & Questions

- a database object from which is used to generate unique integers.
- You can use sequences to automatically generate primary key values.

→ Sequence numbers are generated independently of tables, so the same sequence can be used for one or for multiple tables. 

→ Sequences guarantee uniqueness, not gap-free values.

→ After a sequence is created, you can access its values in SQL statements with

1. the CURRVAL pseudocolumn, which returns the current value of the sequence, or
2. the NEXTVAL pseudocolumn, which increments the sequence and returns the new value.

NEXTVAL must be referenced **before** CURRVAL in a session.

### Privileges

→ To create a sequence in your own schema ⇒ CREATE SEQUENCE. 

→ To create a sequence in another user's schema ⇒ CREATE ANY SEQUENCE. 

```sql
CREATE SEQUENCE sequence_name
  [INCREMENT BY n]
  [START WITH n]
  [MAXVALUE n | NOMAXVALUE]
  [MINVALUE n | NOMINVALUE]
  [CYCLE | NOCYCLE]
  [CACHE n | NOCACHE]
  [ORDER | NOORDER];
```

### DEFAULT VALUES :

→ An ascending sequence that starts with 1 and increases by 1 with no upper limit.

If no options are specified:

- INCREMENT BY 1
- START WITH 1
- NOMAXVALUE
- NOMINVALUE
- NOCYCLE
- CACHE 20 (default cache in Oracle)
- NOORDER

### **INCREMENT BY**

→ Specify the interval between sequence number. 

→ can be any positive ( ascending ) or negative ( descending ) integer, but it cannot be 0

→ this value must be less than the difference of MAXVALUE and MINVALUE. 

→ defaults to 1.

### **START WITH**

→ first sequence number to be generated. 

→ This value is not necessarily the value to which an ascending or descending cycling sequence cycles after reaching its maximum or minimum value, respectively. 

⇒ ( start with > minvalue ) or ( start with < maxvalue )

### MAXVALUE

→ To create a sequence that ****stops at a predefined limit : 

→ specify a value for the MAXVALUE parameter. 

### NOCYCLE.

→  Any attempt to generate a sequence number once the sequence has reached its limit results in an error.

### CYCLE

→ restart after the limit is reached. 

→ After an ascending sequence reaches its maximum value, it generates its minimum value and vice-versa. 

### CACHE :

→ Specify how many values of the sequence the database preallocates and keeps in memory for faster access. 

### ORDER :

→ guarantee that sequence numbers are generated in order of request.

## Using a Sequence.

```sql
sequence_name.NEXTVAL 
```

### in INSERT

```sql
INSERT INTO emp (empno, ename)
VALUES (emp_seq.NEXTVAL,'RAHUL');
```

### in SELECT

```sql
SELECT emp_seq.NEXTVAL
FROM dual;
```

### Altering Sequence

```sql
ALTER SEQUENCE seq_name
INCREMENT BY n;   -- or any other change 
```

### Dropping Sequence

```sql
DROP SEQUENCE emp_seq;
```

⇒ Add assignment. 

## Theory based

1. Define a sequence. How is it different from an identity column?
2. Explain the difference between NEXTVAL and CURRVAL.
3. Why do sequences generate gaps?
4. What is the purpose of CACHE?
5. Explain the difference between CYCLE and NOCYCLE.
6. What happens if START WITH is greater than MAXVALUE?
7. Why should ORDER be avoided in high concurrency systems?
8. Can multiple tables use the same sequence? Explain.
9. What privilege is required to create a sequence in another schema?
10. What error occurs if CURRVAL is used before NEXTVAL?

---

## Query based

1. Create a sequence named std_seq starting at 1000 and incrementing by 5.
2. Create a descending sequence invoice_seq starting at 5000, decreasing by 10.
3. Create a sequence order_seq that:
    - Starts at 1
    - Increments by 1
    - Stops at 100
    - Does not cycle
4. Create a sequence with:
    - Increment by 2
    - Cache 50
    - Cycle enabled
5. Write an INSERT statement using emp_seq.NEXTVAL
6. Display the current value of emp_seq.
7. Alter emp_seq to increment by 20.
8. Drop a sequence named temp_seq.

---