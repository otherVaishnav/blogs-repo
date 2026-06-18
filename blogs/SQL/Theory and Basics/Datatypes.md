# Datatypes in SQL

---

Data types specify the type of data that a column can hold. Choosing the correct datatype is crucial for ensuring data integrity, optimizing storage space, and improving performance.

While different SQL database systems (like Oracle, PostgreSQL, MySQL, and SQL Server) have their own variations and specific datatypes, they broadly fall into the following categories:

### 1. Numeric Data Types
Used to store whole numbers and decimal numbers.
- **`INT` / `INTEGER`**: Stores whole numbers (e.g., `100`, `-45`).
- **`SMALLINT`**: Stores smaller whole numbers.
- **`BIGINT`**: Used for extremely large whole numbers.
- **`DECIMAL(p,s)` / `NUMERIC(p,s)`**: Stores exact decimal numbers (e.g., `DECIMAL(5,2)` allows values like `123.45`).
- **`FLOAT` / `REAL`**: Stores approximate floating-point numbers.

### 2. Character and String Data Types
Used to store text.
- **`CHAR(n)`**: Fixed-length character string. If the actual text is shorter, it is padded with spaces up to length `n`. (e.g., `CHAR(10)`).
- **`VARCHAR(n)` / `VARCHAR2(n)`**: Variable-length character string. No padding is used. It occupies exactly what is needed up to a maximum of `n` characters.
- **`TEXT` / `CLOB`**: Used to store large amounts of text data (Character Large Objects).

### 3. Date and Time Data Types
Used to store temporal values.
- **`DATE`**: Stores a date (Year, Month, Day). Example: `'2024-12-31'`.
- **`TIME`**: Stores the time of day (Hours, Minutes, Seconds).
- **`DATETIME` / `TIMESTAMP`**: Stores both date and time together. It is very useful for tracking exactly when records were created or modified.

### 4. Boolean Data Types
- **`BOOLEAN` / `BOOL`**: Stores logical values indicating `TRUE` or `FALSE`. Some systems (like older versions of Oracle) do not have a boolean datatype and use `NUMBER(1)` or `CHAR(1)` (`'Y'`/`'N'`, `1`/`0`) instead.

### 5. Binary Data Types
Used to store binary data like images, audio, or files directly in the database.
- **`BLOB`**: Binary Large Object. Used for large files.
- **`BINARY` / `VARBINARY`**: Stores smaller binary strings.
