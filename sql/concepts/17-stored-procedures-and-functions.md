# Stored Procedures and User-Defined Functions

## Stored procedures
A stored procedure is a named database routine that can accept parameters and execute multiple statements.
```sql
CREATE OR ALTER PROCEDURE reporting.usp_GetOrdersByCustomer
    @CustomerID INT
AS
BEGIN
    SET NOCOUNT ON;

    SELECT OrderID, OrderDate, TotalAmount
    FROM Sales.Orders
    WHERE CustomerID = @CustomerID;
END;
GO

EXEC reporting.usp_GetOrdersByCustomer @CustomerID = 101;
```

## User-defined functions
Functions return a scalar value or a table and can be used in expressions or queries depending on function type.

## Procedure vs function
- Procedures are invoked with `EXEC` and can perform broader procedural work.
- Functions return a value/table and are subject to restrictions on side effects.
- Do not assume a scalar UDF is always fast; execution behavior depends on SQL Server version and query shape.

## Parameters and safety
Use parameters instead of concatenating untrusted text into dynamic SQL. For dynamic SQL, use `sp_executesql` with parameters.

## Practice
Create a procedure that accepts a date range and returns orders in that range.
