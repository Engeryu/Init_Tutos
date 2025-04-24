# 📘 SQL Cheat Sheet
**Author:** Gaspard-Fauvelle Angel  
**License:** [CC BY-NC-SA 2.0](https://creativecommons.org/licenses/by-nc-sa/2.0/)  

## Table of Contents
- [🧩 CRUD (Data Manipulation)](#🧩-CRUD-(Data-Manipulation))
- [🔎 Filter Clause and its operators](#🔎-Filter-Clause-and-its-operators)
- [Sorting Clause and its options](#Sorting-Clause-and-its-options)
- [Grouping Clause and its filter](#Grouping-Clause-and-its-filter)
- [🧰 Other Useful Clauses](#🧰-Other-Useful-Clauses)
- [Aggregation Functions](#Aggregation-Functions)
- [Joins](#Joins)
- [DDL Functions (Data Definition Language)](#DDL-Functions-(Data-Definition-Language))
- [🔐 DCL (Data Control Language)](#🔐-DCL-(Data-Control-Language))
- [🔐 Constraints](#🔐-Constraints)
- [🔁 Transactions](#🔁-Transactions)

---

### 🧩 CRUD (Data Manipulation)
| **Clauses**    | **Category**    | **Description**                                                         |
|----------------|------------------|-------------------------------------------------------------------------|
| `SELECT`       | Read             | Retrieves data from one or more tables.                                |
| `INSERT INTO`  | Create           | Adds new rows of data to a table.                                      |
| `UPDATE`       | Update           | Modifies existing data in one or more rows of a table.                 |
| `DELETE FROM`  | Delete           | Deletes rows of data from a table.                                     |

---

### 🔎 Filter Clause and its operators
| **Clause/Operator** | **Category** | **Description**                                                       |
|---------------------|--------------|-----------------------------------------------------------------------|
| `WHERE`             | Filter       | Specifies a condition to filter the returned rows.                   |
| `AND`               | Operator     | Combines multiple conditions, all must be true.                      |
| `OR`                | Operator     | Combines multiple conditions, at least one must be true.             |
| `NOT`               | Operator     | Reverses the result of a condition.                                  |
| `IN`                | Operator     | Checks if a value is in a list.                                      |
| `BETWEEN`           | Operator     | Selects a range of values.                                           |
| `LIKE`              | Operator     | Pattern matching search (using `%`, `_`).                            |
| `IS NULL`           | Operator     | Checks if a value is `NULL`.                                         |
| `IS NOT NULL`       | Operator     | Checks if a value is not `NULL`.                                     |
| `EXISTS`            | Operator     | Checks for the existence of rows in a subquery.                      |
| `NOT EXISTS`        | Operator     | Checks for the non-existence of rows in a subquery.                  |

---

### Sorting Clause and its options
| **Clause/Option** | **Category** | **Description**                                 |
|------------------|--------------|-------------------------------------------------|
| `ORDER BY`       | Sort         | Sorts the results by one or more columns.       |
| `ASC`            | Option       | Ascending order (default).                      |
| `DESC`           | Option       | Descending order.                               |

---

### Grouping Clause and its filter
| **Clause**  | **Category** | **Description**                                           |
|-------------|--------------|-----------------------------------------------------------|
| `GROUP BY`  | Grouping     | Groups rows with the same values.                         |
| `HAVING`    | Filter       | Filters groups created with `GROUP BY`.                   |

---

### 🧰 Other Useful Clauses
| **Clause**              | **Category** | **Description**                                               |
|-------------------------|--------------|---------------------------------------------------------------|
| `LIMIT` / `TOP`         | Limiting     | Limits the number of results.                                |
| `OFFSET` / `FETCH NEXT` | Pagination   | Skips a specific number of results.                          |
| `AS`                    | Alias        | Renames a table or column within the query.                  |
| `DISTINCT`              | Selection    | Eliminates duplicate values.                                 |
| `UNION`                 | Combination  | Combines multiple queries, removing duplicates.              |
| `UNION ALL`             | Combination  | Combines multiple queries, keeping duplicates.               |
| `VIEW`                  | Object       | Creates a virtual view.                                      |
| `PROCEDURE` / `FUNCTION`| Object       | Creates a stored procedure or function.                      |

---

### Aggregation Functions
| **Function** | **Category** | **Description**                      |
|--------------|--------------|--------------------------------------|
| `COUNT()`    | Aggregation  | Number of rows.                      |
| `SUM()`      | Aggregation  | Sum of numeric values.              |
| `AVG()`      | Aggregation  | Average of values.                  |
| `MIN()`      | Aggregation  | Minimum value.                      |
| `MAX()`      | Aggregation  | Maximum value.                      |

---

### Joins
| **Join**           | **Category** | **Description**                                                                 |
|-------------------|--------------|---------------------------------------------------------------------------------|
| `JOIN`            | Join         | Combines rows from multiple tables.                                             |
| `INNER JOIN`      | Join         | Returns rows with matches in both tables.                                      |
| `LEFT JOIN`       | Join         | All rows from the left + matching ones from the right.                         |
| `RIGHT JOIN`      | Join         | All rows from the right + matching ones from the left.                         |
| `FULL OUTER JOIN` | Join         | All rows from both tables (with or without match).                             |
| `CROSS JOIN`      | Join         | Cartesian product of two tables.                                               |

---

### DDL Functions (Data Definition Language)
| **Command**        | **Category** | **Description**                                     |
|--------------------|--------------|-----------------------------------------------------|
| `CREATE TABLE`     | DDL          | Creates a new table.                                |
| `ALTER TABLE`      | DDL          | Modifies the structure of a table.                  |
| `DROP TABLE`       | DDL          | Deletes a table.                                    |
| `CREATE DATABASE`  | DDL          | Creates a new database.                             |
| `ALTER DATABASE`   | DDL          | Modifies a database.                                |
| `DROP DATABASE`    | DDL          | Deletes a database.                                 |
| `CREATE INDEX`     | DDL          | Creates an index to speed up searches.              |
| `DROP INDEX`       | DDL          | Deletes an index.                                   |

---

### 🔐 DCL (Data Control Language)
| **Command** | **Category** | **Description**                                  |
|-------------|--------------|--------------------------------------------------|
| `GRANT`     | DCL          | Grants privileges to a user or role.             |
| `REVOKE`    | DCL          | Revokes privileges.                              |

---

### 🔐 Constraints
| **Constraint** | **Category** | **Description**                                 |
|----------------|--------------|-------------------------------------------------|
| `PRIMARY KEY`  | Constraint   | Uniquely identifies a row.                      |
| `FOREIGN KEY`  | Constraint   | Links two tables.                               |
| `UNIQUE`       | Constraint   | All values must be unique.                      |
| `NOT NULL`     | Constraint   | Prevents `NULL` values.                         |
| `CHECK`        | Constraint   | Enforces conditions on values.                 |
| `DEFAULT`      | Constraint   | Sets a default value.                           |

---

### 🔁 Transactions
| **Command**         | **Category** | **Description**                                                                 |
|---------------------|--------------|----------------------------------------------------------------------------------|
| `START TRANSACTION` | Transaction  | Starts a transaction.                                                           |
| `COMMIT`            | Transaction  | Commits the transaction.                                                        |
| `ROLLBACK`          | Transaction  | Rolls back the transaction.                                                     |
| `SAVEPOINT`         | Transaction  | Partial savepoint within a transaction.                                         |
| `TRUNCATE`          | Transaction  | Deletes data and metadata without rollback possibility.                         |

---

_Edited : 2025/04/22_