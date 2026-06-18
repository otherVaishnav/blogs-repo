# Data modeling

⇒ Data modeling is a detailed process that involves creating a visual representation of data and its relationships. 

→ It serves as a blueprint for how data is structured, stored, and accessed to ensure consistency and clarity in data management. 

### **Types of data models**

1. **Conceptual data model** 
2. **Logical data model**
3. **Physical data model**

### 1. Conceptual data model.

→ Provides a high-level view of the data. 
→ It defines key business entities (e.g., customers, products, and orders) and their relationships without getting into technical details. 

### 2. Logical data model

→ Defines how the data will be structured. 

→ This model focuses on data organization without being tied to any specific database or technology

→ It includes detailed information about the data's attributes, relationships, and constraints. 

### 3. Physical Data Model

→ Represents how data is actually stored in a database. 

→ This model defines the specific table structures, indexes, and storage mechanisms required to optimize performance and ensure data integrity. 

→ It translates the logical design into a format suitable for database systems.

## **Data Modeling Techniques**

1. **Entity-relationship (ER) modeling**
2. **Dimensional modeling**
3. **Object-oriented modeling**

## 1. **Entity-relationship (ER) modeling**

It has 3 components : 

- **Entities** (objects or things within the system).
- **Relationships** (how these entities interact with each other).
- **Attributes** (properties of the entities).

## 2. **Dimensional modeling**

→ Data is represented in terms of **facts** and **dimensions**

→ used for complex data organization 

→ famous schemas : star and snowflake schema

an example of star schema. 

→ at center we have a facts table. 

→ at ends we have dimension tables, this creates a star like pattern. 

→ in case of snow-flake schema, the dimension tables are further divided into sub_dimension tables. 

## 3. **Object-oriented modeling**

→ here data and the functions that operate on it are encapsulated as one objects. 

→ in this case, object includes both attributes (data fields) and methods (functions)

eg. 

Customer ( object ) 

attributes : 

1. id 
2. name 
3. phone_no 
4. address 

Methods : 

1. place_order()
2. cancle_order() 
3. give_feedback() 

→ This approach is particularly beneficial in object-oriented programming (OOP) languages like Java and Python, where data models can be directly mapped to classes and objects.