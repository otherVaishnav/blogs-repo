# TO ADD

[***Database Recovery**](/07projectsandmisc/to-add/database-recovery)

1. MySQL Storage Engines 
2. Database Design Patterns.
3. OLTP vs OLAP schema design - overview.
4. Star and snowflake schemas - overview
5. BASE 
6. Recovery 
7. Time travel queries 
8. CASCADE 
9. Unpivot  
10. DBMS Architecture (1-tier, 2-tier, 3-tier)
    - Client–Server architecture
    - Storage Engine concepts
    - Buffer cache / Shared pool (Oracle)
    - WAL (Write-Ahead Logging – PostgreSQL)
    - Redo / Undo logs
    - Tablespaces & Datafiles
    - Physical vs Logical storage
    - MVCC (Multi-Version Concurrency Control)

---

---

- Transactions & Concurrency Control (Deep Level)
    
    ---
    
    - Isolation levels (READ UNCOMMITTED, READ COMMITTED, REPEATABLE READ, SERIALIZABLE)
    - Phantom reads, Dirty reads, Non-repeatable reads.
    - Locking (Row-level, Table-level)
    - Deadlocks (detection & resolution)
    - Optimistic vs Pessimistic locking
    - Two-phase locking (2PL)

---

---

- Advanced Query Processing
    
    ---
    
    - Execution plans (EXPLAIN PLAN)
    - Cost-based optimizer (CBO)
    - Index types: ( add more details and diagrams for )
        - B-Tree
        - Bitmap index
        - Hash index
        - Clustered vs Non-clustered
    - Partitioning:
        - Range
        - List
        - Hash
        - Composite
    - Materialized Views
    - Query rewrite

---

---

Advanced SQL Standards

---

- MERGE statement
    - Recursive CTE (WITH RECURSIVE)
- LATERAL joins
- JSON support in SQL
- XML support
- Array data types (Postgres)
- Generated columns
- Updatable views

---

---

Database Design (Beyond Normalization)

---

- ER Modeling (Strong/Weak entities)
- Cardinality & Participation constraints
- Functional Dependencies
- 1NF → 5NF + BCNF (deep proofs)
- Denormalization strategies
- Surrogate vs Natural keys
- Data warehousing concepts:
    - OLTP vs OLAP
    - Star schema
    - Snowflake schema
    - Fact & Dimension tables
    - Slowly Changing Dimensions (SCD Types 1–6)

---

---

Distributed Databases

---

- Replication (Master–Slave, Multi-master)
- Sharding
- Horizontal vs Vertical scaling
- Consensus algorithms (Raft, Paxos)
- Eventual consistency
- Distributed transactions (2PC, 3PC)

---

---

Backup, Recovery & High Availability

---

- Full / Incremental backups
- Point-in-time recovery
- Log shipping
- Failover & clustering
- Replication lag
- Disaster recovery strategies

---

---

Security

---

- Roles & privileges (deep)
- Row-level security
- Encryption at rest
- Encryption in transit (SSL/TLS)
- SQL Injection prevention
- Auditing

---

---

Performance Engineering

---

- Index selectivity
- Cardinality estimation
- Join algorithms:
    - Nested loop
    - Hash join
    - Merge join
- Statistics & ANALYZE
- Connection pooling
- Caching layers

---

---

NoSQL & Modern Databases  

---

- Key-value stores
- Document databases
- Column-family databases
- Graph databases
- When to choose NoSQL over RDBMS