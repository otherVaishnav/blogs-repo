# Relational Model

---

The **Relational Model** is a conceptual framework tailored for structuring data in a database. Proposed by Edgar F. Codd in 1970, it revolutionized how data is stored, manipulated, and queried by organizing it into tables (relations). 

It is the foundation of all Relational Database Management Systems (RDBMS) such as Oracle, MySQL, SQL Server, and PostgreSQL.

### Core Concepts of the Relational Model:

1. **Relation (Table)**
   A relation is a two-dimensional structure made up of rows and columns. In simple terms, a "table" is the physical manifestation of a relation.
2. **Tuple (Row / Record)**
   A single, horizontally aligned entry in a table representing a unique instance of the data entity. For example, a single row in an `Employee` table corresponds to one specific employee.
3. **Attribute (Column / Field)**
   A vertical entry detailing a specific property of the relation. In the `Employee` table, `Name`, `Salary`, and `Department` would be attributes.
4. **Domain**
   The set of permissible values that an attribute can take. For example, the domain for the attribute `Age` might be integers between `18` and `100`.
5. **Degree**
   The degree of a relation is the total number of attributes (columns) it contains. 
6. **Cardinality**
   The cardinality is the total number of tuples (rows) present in the relation.

### Why use the Relational Model?

- **Structural Independence**: Changes to the database structure (like adding a column to a table) do not affect applications or users interacting with the database.
- **Simplicity**: Data is organized neatly in tables. Users can easily grasp relationships between entities without understanding complex trees or pointers (which were used in older Hierarchical and Network models).
- **Data Integrity**: Enforced through primary keys, foreign keys, and referential rules to maintain data accuracy and consistency.
- **Powerful Querying**: The model supports declarative query languages like SQL, allowing users to state *what* data they want rather than explaining *how* to locate it.
