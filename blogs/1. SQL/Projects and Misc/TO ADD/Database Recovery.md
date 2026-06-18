---
title: "Database Recovery"
description: "Explore the database recovery section."
pubDate: "2025-06-01"
---


<!-- ![image.png](Database%20Recovery/image.png) -->

<!-- [prerequisite ](/07projectsandmisc/to-add/database-recovery/prerequisite) -->

ref : 

[https://docs.oracle.com/en/database/oracle/oracle-database/19/bradv/introduction-backup-recovery.html#GUID-7D5CF571-0B7A-46D7-B9DC-CD15F3A4C34F](https://docs.oracle.com/en/database/oracle/oracle-database/19/bradv/introduction-backup-recovery.html#GUID-7D5CF571-0B7A-46D7-B9DC-CD15F3A4C34F) 

→ the process of restoring a database to a correct and consistent state after a failure. 

→ Failures can corrupt a database, cause data loss, or make it unavailable. 

→ Database recovery ensures data integrity, consistency, and minimal downtime.

### **Why is Database Recovery Important?**

1. Protects against data loss due to system crashes, power failures, or software errors.
2. Ensures data consistency using transactions and recovery techniques.
3. Minimizes downtime to maintain business continuity.
4. Allows rollback of incorrect or incomplete transactions.

## **Types of Database Failures:**

1. **Transaction Failure**
2. **System Crash (Soft Failure)**
3. **Disk Failure (Hard Failure)**
4. **Media Failure**
5. **Catastrophic Failure**

### 1. **Transaction Failure :**

Occurs when a transaction cannot be completed due to : 

**→ Logical errors** (e.g., division by zero, constraint violations).

**→ Deadlocks** (when two transactions wait for each other to release resources).

**→ System crashes** during execution.

### 2. **System Crash (Soft Failure) :**

Happens due to:

→ Operating system crash.

→ Hardware failure (CPU, RAM, Disk failures).

→ Power failure causing unsaved transactions to be lost.

### 3. **Disk Failure (Hard Failure)**

Happens due to:

→ Physical damage to the storage device (HDD/SSD failure).

→ Bad sectors causing partial data corruption.

### 4. Media failure

→ Occurs when database storage (disk/tape) is damaged beyond repair. 

### 5. **Catastrophic Failure**

→ Happens due to **natural disasters (fire, flood, earthquake), cyberattacks, or accidental deletion of data.** 

## **Database Recovery Techniques**

**recovery techniques:** 

1. **Backup-Based Recovery**
2. **Log-Based Recovery (Using Transaction Logs)**
3. **Shadow Paging**
4. **Checkpoint Mechanism**
5. **Deferred Update (No Undo, Only Redo)**
6. **Immediate Update (Undo + Redo Required)**
7. **ARIES (Algorithms for Recovery and Isolation Exploiting Semantics)**

### **1. Backup-Based Recovery**

Full Backup : Copies the entire database at a specific point in time.

Incremental Backup : Stores only changes made since the last backup.

Differential Backup : Stores changes since the last full backup.

Cold Backup : Taken when the database is offline.

Hot Backup : Taken when the database is running (common in real-time systems). 

eg, 

```sql
sqlCopyEditBACKUP DATABASE my_database 
TO DISK = 'D:\backup\my_database.bak'
WITH FORMAT, MEDIANAME = 'SQLServerBackups';
```

---

---

ref  : 
[https://drbtaneja.com/database-recovery/](https://drbtaneja.com/database-recovery/) 

[https://www.geeksforgeeks.org/dbms/database-recovery-techniques-in-dbms/](https://www.geeksforgeeks.org/dbms/database-recovery-techniques-in-dbms/)