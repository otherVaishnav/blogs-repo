---
title: "Understanding SQL NULL and Three-Valued Logic"
description: "Demystifying SQL NULL. Learn why NULL != NULL and how Three-Valued Logic impacts your database queries."
pubDate: 2026-06-10
---

# Understanding SQL NULL and Three-Valued Logic

In almost every programming language, checking if two empty or null variables are identical returns a straightforward boolean true. In JavaScript, `null === null` yields `true`. In Python, `None == None` is `True`.

But in relational databases and standard SQL logic, running this comparison yields a surprising result:

```sql
SELECT * FROM users WHERE middle_name = NULL;
-- Result: Empty Set (0 rows returned)
Why does this happen? Because in SQL, NULL is not a value. It is a state representing missing or unknown data.

Enter Three-Valued Logic (3VL)
Traditional logic is binary: a statement is either TRUE or FALSE. SQL, however, implements Three-Valued Logic. A condition can evaluate to TRUE, FALSE, or UNKNOWN.

Because NULL means "unknown," comparing anything to NULL results in an UNKNOWN state.

Look closely at how evaluating a query works under the hood:

Plaintext
Is Bob's middle name equal to this unknown value? 
Database answer: "I don't know." -> UNKNOWN
Since SQL WHERE clauses only return rows where the condition evaluates strictly to TRUE, rows evaluated as UNKNOWN are completely filtered out.

How to Deal with It Safely
To safely query for missing data fields, you must bypass the standard arithmetic comparison operator (=) entirely and rely on explicit state operators:

SQL
-- The correct way to check for missing data
SELECT * FROM users WHERE middle_name IS NULL;

-- The correct way to check for existing data
SELECT * FROM users WHERE middle_name IS NOT NULL;
Additionally, you can utilize the COALESCE() utility function to establish default fallback paths when encountering an unknown value:

SQL
SELECT username, COALESCE(middle_name, 'N/A') AS middle_initial FROM users;
Remember: treat NULL as a question mark, not a zero or an empty string, and your database query logic will remain bulletproof.
