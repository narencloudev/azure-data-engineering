# SQL Command Categories: DDL, DML, DQL, DCL, TCL

## DDL — Data Definition Language
Defines or changes database objects.
```sql
CREATE TABLE dbo.Departments (
    DepartmentID INT PRIMARY KEY,
    DepartmentName VARCHAR(100) NOT NULL
);

ALTER TABLE dbo.Departments ADD Location VARCHAR(100);
```
`DROP` removes an object. `TRUNCATE TABLE` removes all rows while retaining the table structure.

## DML — Data Manipulation Language
Changes table data.
```sql
INSERT INTO dbo.Departments (DepartmentID, DepartmentName)
VALUES (10, 'Analytics');

UPDATE dbo.Departments
SET DepartmentName = 'Data Analytics'
WHERE DepartmentID = 10;

DELETE FROM dbo.Departments
WHERE DepartmentID = 10;
```
Always verify the `WHERE` condition before running `UPDATE` or `DELETE`.

## DQL — Data Query Language
Retrieves data, primarily with `SELECT`.
```sql
SELECT DepartmentID, DepartmentName
FROM dbo.Departments;
```

## DCL — Data Control Language
Manages permissions.
```sql
GRANT SELECT ON dbo.Departments TO reporting_user;
```

## TCL — Transaction Control Language
Controls transaction boundaries.
```sql
BEGIN TRANSACTION;
UPDATE dbo.Accounts SET Balance = Balance - 100 WHERE AccountID = 1;
UPDATE dbo.Accounts SET Balance = Balance + 100 WHERE AccountID = 2;
COMMIT;
```
Use `ROLLBACK` instead of `COMMIT` if validation fails.

## TRUNCATE vs DELETE vs DROP
- `DELETE`: removes selected rows (or all rows if no filter); can fire delete triggers.
- `TRUNCATE`: removes all rows, generally deallocating data pages; no `WHERE`.
- `DROP`: removes the table object itself.
Transaction behavior and restrictions depend on the database engine and constraints.

## Practice
Classify `CREATE`, `INSERT`, `SELECT`, `GRANT`, and `ROLLBACK`. Explain when you would use each.
