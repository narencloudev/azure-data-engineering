# SQL Introduction

## What is SQL?
SQL (Structured Query Language) is used to define, query, manipulate, and control data in relational database systems. In this learning pack, examples use Microsoft SQL Server (T-SQL).

## Relational database basics
- A **database** is an organized collection of data.
- A **table** stores data in rows and columns.
- A **row** represents one record.
- A **column** represents one attribute.
- A **schema** is a logical container for database objects, such as `Sales.Orders`.

## Example
```sql
SELECT OrderID, CustomerID, OrderDate
FROM Sales.Orders;
```
This returns selected columns from the `Sales.Orders` table.

## SQL command families
- DDL: define objects (`CREATE`, `ALTER`, `DROP`, `TRUNCATE`).
- DML: change rows (`INSERT`, `UPDATE`, `DELETE`, `MERGE`).
- DQL: retrieve data (`SELECT`).
- DCL: permissions (`GRANT`, `DENY`, `REVOKE`).
- TCL: transaction control (`BEGIN TRANSACTION`, `COMMIT`, `ROLLBACK`).

## Remember
SQL is declarative: you describe the result you need, and the database engine chooses an execution strategy.

## Practice
1. Explain the difference between a database, schema, table, row, and column.
2. Write a query that selects three columns from a table.
