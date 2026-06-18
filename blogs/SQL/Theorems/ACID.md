# ACID

### Transactions :

→ It is a collection of operations (reads and writes) that are treated as a single logical operation.

1. Atomicity : ALL or NONE.
2. Consistency : Valid state, before and after transaction.
3. Isolation : All transactions are independent.
4. Durability : once saved, changes survive system failure.

## 1. Atomicity

→ ALL or NONE 

→ A transaction must be fully completed or not done at all.

→ If any part of the transaction fails, the entire transaction is rolled back.

---

## 2. Consistency

→ the database remains in a valid state

→ All integrity constraints (PK, FK, CHECK, NOT NULL, triggers) must hold before and after the transaction.

Consistency is enforced by:

- Constraints
- Triggers

---

## 3. Isolation

→ Concurrent transactions should not interfere in a way that violates consistency. ie , Intermediate states of a transaction must not be visible to other transactions.

→ Ensures data integrity in concurrent environments.

→ Concurrent transactions should behave as if they were executed one at a time (i.e. serially).

### **Problems Without Isolation:**

1. Dirty reads
    
    ⇒ A transaction reads data written by another transaction that has not yet committed. 
    
    ⇒ may cause due to READ UNCOMMITTED.
    
2. Non-repeatable reads 
    
    ⇒ A row read twice within the same transaction returns different values because another transaction modified and committed it.
    
    ⇒ may cause due to READ COMMITTED.
    
3. Phantom reads
    
    ⇒ A transaction re-executes a query returning multiple rows and finds new rows inserted by another committed transaction. 
    

### **Isolation Levels :**

1. READ UNCOMMITTED : 
    
    → Can read un-committed data 
    
    → in this case there is almost no isolation. it allows : 
    
    - Dirty reads
    - Non-repeatable reads.
    - Phantom reads.
    
2. READ COMMITTED
    
    → Can only read committed data.
    → in this case 
    
    - No dirty reads
    - Non-repeatable reads possible
    - Phantom reads possible

1. REPEATABLE READ
    
    → Rows read cannot change within the transaction.
    
    → but, phantom reads possible (per SQL standard). 
    
2. SERIALIZABLE. 
    
    → Behavior is equivalent to transactions running one after another (serial execution).
    
    → Strongest isolation level 
    

---

### 4. Durability

→ Once committed, always there

→ Once a transaction is committed, its changes are permanent, even if there's a crash or power loss. 

**Implementation Mechanism:**

- Write-Ahead Logging (WAL)
- Redo logs
- Checkpointing