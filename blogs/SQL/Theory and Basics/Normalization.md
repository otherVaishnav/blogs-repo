---
title: "Normalization"
description: "Explore the normalization section."
pubDate: "2025-06-02"
---

<!-- # Normalization -->

1. Attributes 
2. Functional Dependencies 
3. Normalization.

## Attributes ( COLUMNS )

→ characteristics of an object .

Types of Attributes 

1. Key Attribute 
2. Non - key attribute 
3. Prime key attribute 
4. Non - prime key attribute 
5. Composite key attribute 
6. Super key attribute 
7. Foreign key attribute 

---

1. Key Attribute ( candidate key ) : 
    
    → The attribute which can be used to identify a record uniquely, is known as key attribute.
    
    → We can have multiple key attributes in a table.
    
2. Non-key attributes : 
    
    → The attributes which can not be used to identify a record uniquely is known as non-key attribute.
    
    → We can have multiple non-key attributes in a table.
    
3. Prime key attributes : 
    
    → The key attribute which is selected to identify the record uniquely, is prime key attribute 
    
    → We can have only one prime key attribute in the table.
    
4. Non - prime key attribute ( alternate key ) :
    
    → The key attributes other than Prime - key attribute are known as non - prime key attribute.
    
    → We can have multiple non - prime key attribute
    
5. Composite key attribute :
    
    → The combination ( or set ) of two or more non key attributes, which is used to identify the records uniquely from the table is known as composite key attribute.
    
    → We can create a composite key when no key-attribute is present in the table.
    
6. Super key attribute : 
    
    → The set of all key attributes is known as Super key attribute.
    
7. Foreign key attribute : 
    
    → When a key attribute of one table behaves as an non-key attribute in other table to establish a relationship is known as foreign key attribute.
    
    → We can have multiple Foreign - key attributes. 
    

---

## Functional Dependencies

→ A relation where an attribute determines another attribute.

Types of Functional Dependencies :

1. Total functional Dependency
2. Partial functional Dependency 
3. Transitive functional Dependency 
1. Total Functional Dependency 
    
    → Total functional dependency exists when all the attributes in a table depend on a single key attribute.
    
2. Partial functional Dependency : 
    
    → Partial functional dependency exists when a non-key attribute depend on a part of composite key attribute.
    
3. Transitive functional Dependency : 
    
    → Transitive functional dependency exists when a non-key attribute depend on  another non-key attribute which itself is depend on a key-attribute. 
    

---

---

 

# Normalization

→ It is a process of converting a Large table into Smaller tables in order to remove redundancies and Anomalies by identifying their Functional Dependencies.
Or
The process of decomposing a table into its Normal Form is known as Normalization.

REDUNDANCY: - The repetition of unwanted values  is known redundancy. 

ANOMALIES: - The side effect occurs due to DML operations.

### LEVELS OF NORMAL FORM:

- First Normal Form ( 1NF )
- Second Normal Form ( 2NF )
- Third Normal Form ( 3NF )
- Boyce - Codd Normal Form ( BCNF ) or ( 3.5 NF )

→ A table without redundancies and anomalies are said to be in Normal Form.

> If any table is reduced to 3NF, then that table is said to be Normalized
> 

### 1. FIRST NORMAL FORM (1NF)

For a table to be in the first normal from : 

- Multivalued data should not be present. ( 1st rule of EF Codd )
- It should have no duplicate records.

### 2. SECOND NORMAL FORM (2NF)

For a table to be in the Second Normal form : 

- It should be in 1NF.
- It should not have partial functional dependency.

### 3. THIRD NORMAL FORM (3NF)

For a table to be in the Third Normal Form: 

- Table should be in 2NF.
- It should not have a Transitive Functional Dependency.

---

### 3.5  BOYCE - CODD NORMAL FORM ( BCNF) - 3.5 NF

Stricter version of 3NF 

- Table should be in 3NF
- If A → B ( A determines B ) , then A should be a key attribute ( or super key ).
- i.e. a non-key can should not determine other non-key.

---