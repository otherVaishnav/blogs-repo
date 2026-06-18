---
title: "E.F. Codd's Rules"
description: "Explore the E.F. Codd's Rules section."
pubDate: "2025-06-01"
---

<!-- # E.F. Codd's Rules -->

---

In 1985, Dr. Edgar F. Codd (the inventor of the Relational Model) published a set of 12 rules (numbered from 0 to 12, making it technically 13 rules). A database system must satisfy these rules to be classified as a true **Relational Database Management System (RDBMS)**.

Very few commercial databases strictly adhere strictly to *all* of Codd's rules, but they form the foundational standard for RDBMS design.

### The Rules:

**Rule 0: Foundation Rule**
The system must be capable of managing its databases entirely through its relational capabilities, not using lower-level disk access.

**Rule 1: Information Rule**
All data within the database must be represented in one, and only one way: as values within columns and rows of tables.

**Rule 2: Guaranteed Access Rule**
Every piece of data must be logically accessible by utilizing the combination of the Table Name, Primary Key, and Column Name.

**Rule 3: Systematic Treatment of Null Values**
The DBMS must uniformly support Missing or Null information, distinct from a blank space or zero, for any datatype.

**Rule 4: Dynamic Online Catalog Based on the Relational Model**
The database description (metadata) must be stored and accessed in tables just like ordinary user data, allowing users to query the schema using the same relational query language (SQL).

**Rule 5: Comprehensive Data Sublanguage Rule**
The RDBMS must support at least one well-defined language (like SQL) that handles data definition, manipulation, integrity constraints, and transaction management seamlessly.

**Rule 6: View Updating Rule**
Any view that is theoretically updatable must also be practically updatable by the database system.

**Rule 7: High-Level Insert, Update, and Delete Rule**
The system must support set-level operations. You should be able to retrieve, insert, update, or delete multiple rows using a single command, rather than working row-by-row.

**Rule 8: Physical Data Independence**
The user applications shouldn't be affected when physical storage changes (such as moving data to a new disk, or changing storage architecture).

**Rule 9: Logical Data Independence**
User applications shouldn't be affected when logical changes occur to the database structure (like adding or merging tables) provided the data required is still accessible.

**Rule 10: Integrity Independence**
Integrity constraints (like Primary and Foreign Keys) must be stored in the database catalog separate from the application programs, ensuring data validity at the source level.

**Rule 11: Distribution Independence**
The RDBMS should continue to function smoothly even if the database is distributed physically across multiple servers. Applications shouldn't realize the data is spread out.

**Rule 12: Non-Subversion Rule**
If the RDBMS provides a low-level (record-at-a-time) interface, it cannot be used to bypass the security or integrity rules established in the high-level relational language.
