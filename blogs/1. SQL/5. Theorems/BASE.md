---
title: "BASE Theorem"
description: "Explore the BASE theorem ."
pubDate: "2025-06-01"
---


<!-- # BASE -->

**→ Basically Available Soft State Eventually Consistent**

→ BASE prioritizes availability and partition tolerance over strict consistency. 

→ It’s an AP system according to CAP theorem. 

## BA : Basically Available

→ The system guarantees availability. 

→ every request receives a response (success or failure), even during partial system failures.

→ it means, Some nodes may fail, but the system continues operating, 

→ here the responses may not reflect the most recent write. 

→ an AP system. 

eg . 

Apache Cassandra, Amazon DynamoDB

## S : **Soft State**

→ The system state may change over time, even without new input.

→ as consistency isn’t the priority, different replicas may temporarily store different values.

→ but Data propagates gradually, ie. the system reaches consistency eventually ( hard state ). 

so during this time period the system stays in Soft State. 

## **E Eventually Consistent**

→ All nodes will eventually converge to the same value ( ie become consistent ) .

eg . MongoDB ( relaxed consistency),  Amazon DynamoDB

Use ACID when:

→ Data correctness is critical

→ Transactions must be strictly reliable

eg : banking systems

Use BASE when:

→ System must scale horizontally

→ High availability is required

→ Slight data staleness is acceptable

eg : large distributed platforms ( Instagram )