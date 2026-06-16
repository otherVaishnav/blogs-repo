---
title: "Understanding Linked List "
description: "Understanding the Linked list data structure in detail."
pubDate: 2026-06-16
---

A linked list is a linear data structure that includes a series of connected nodes.
→ Each node stores the **data** and the **address** of the next node. 

### Characteristics :

1. Dynamic Size
2. Non-Contiguous Memory Allocation
3. Sequential Access Only. 
4. Efficient Insertions and Deletions 

Advantages : 

1. Arrays have a fixed size, whereas linked lists can grow or shrink dynamically during runtime. 
2. Inserting or deleting an element in an array requires shifting elements [ O(n) ]. In a linked list, it only requires updating a few pointers (O(1) time if the position is known ) . 
3. Memory is allocated only when a new element is added.

Disadvantages : 

1. You cannot access an element directly by its index. You must traverse from the beginning (Head).
2. Each node requires extra memory to store the pointer/reference. 

### Types

1. Singly Linked List
2. Doubly Linked List
3. Circular Linked List

## 1. Singly Linked List

Standard structure of single linked list node has 

1. data. 
2. next node reference. 

```java
class Node {
    int data;
    Node next;
}
```

!image.png

!image.png

Each node points only to the *next* node. Traversal is uni-directional.

### How to operate on a linked list .

1. Adding
2. Removing 
3. Searching 

---

Time Complexity

|  | Worst case | Average Case |
| --- | --- | --- |
| **Search** | O(n) | O(n) |
| **Insert** | O(1) | O(1) |
| **Deletion** | O(1) | O(1) |

---

## 1. Doubly Linked List

Standard structure of doubly linked list node has 

1. data. 
2. next node reference. 
3. previous node reference. 

```java
class Node {
    int data;
    Node next, prev;
}
```

!image.png

!image.png

Each node links both forward and backward → traversal in both directions

Advantages : 

1. Backward traversal possible
2. Easier deletion (no need to track previous node separately)

**Operations**

1. Insert at head: O(n)
2. Search: O(n)
3. Delete: O(n)

---

## **3. Circular Linked List**

Standard structure same as singly/doubly, but last node points back to the **first node** instead of NULL.. 

```java
// structure is same as singly or doubly
class Node {
    int data;
    Node next;
}
// just the last node points towards the first node not a null. 
// ie. lastNode.next = head;
```

!image.png

### Types

1. Circular Singly Linked List
2. Circular Doubly Linked List

Advantages:

1. Any node can be a starting point — useful for round-robin scheduling
2. Whole list can be traversed from any node

Disadvantages:

1. More complex implementation
2. Risk of infinite loops if traversal not handled carefully
