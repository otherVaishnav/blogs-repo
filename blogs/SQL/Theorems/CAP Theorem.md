---
title: "CAP Theorem"
description: "Explore the CAP theorem."
pubDate: "2025-06-02"
---

<!-- # CAP Theorem -->

CAP Theorem (Brewer’s Theorem) states that a distributed data system cannot simultaneously guarantee all three of the following properties:

1. Consistency (C)
    
    → All nodes see the same data at the same time.
    
    → Every read returns the most recent write or an error.
    
2. Availability (A)
    
    → The system always responds, even if the data may be stale.
    
    → Every request receives a non-error response, regardless of which node is contacted.
    
3. Partition Tolerance (P) 
    
    → The system continues to operate despite network partitions ( message loss or delays between nodes ).
    
    → the system works despite network/node crash.
    
    → Partition tolerance is non-negotiable in real distributed systems (networks fail), so the real trade-off is C vs A. 
    

> **When a network partition occurs, a distributed system must choose either Consistency or Availability, but not both.**
> 
> 
> **CAP = C or A, given P**
> 

| Type | Guarantees | Behavior During Partition |
| --- | --- | --- |
| **CP** | Consistency + Partition Tolerance | May reject requests to keep data consistent |
| **AP** | Availability + Partition Tolerance | Always responds, 
may return old data |
| **CA** | Consistency + Availability | Works only when no partition exists ( single-node systems ) |

### Examples

- CP Systems
    - HBase, MongoDB (with majority writes), Zookeeper
        
        *Use case:* banking, inventory, critical correctness
        
- AP Systems
    - Cassandra, DynamoDB, CouchDB
        
        *Use case:* social media, analytics, high availability
        
- CA Systems
    - Traditional RDBMS (single-node)
    - Oracle DB (non-distributed mode),  ( < 19c )