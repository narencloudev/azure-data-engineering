# Views and Temporary Tables

## Views
A view is a saved query exposed like a table.
```sql
CREATE VIEW reporting.vw_CustomerOrders
AS
SELECT c.CustomerName, o.OrderID, o.OrderDate, o.TotalAmount
FROM Sales.Customers AS c
JOIN Sales.Orders AS o ON o.CustomerID = c.CustomerID;
```
Query it with `SELECT * FROM reporting.vw_CustomerOrders`.

Views can simplify access and provide a stable reporting interface. A regular view generally stores its definition, not a separate copy of query results. Indexed views have special requirements.

## Temporary tables
Temporary tables are created in `tempdb`.
- `#LocalTemp`: visible within the current session and relevant nested scope.
- `##GlobalTemp`: visible to other sessions while it exists.

```sql
CREATE TABLE #HighValueOrders (
    OrderID INT,
    TotalAmount DECIMAL(12,2)
);

INSERT INTO #HighValueOrders
SELECT OrderID, TotalAmount
FROM Sales.Orders
WHERE TotalAmount > 10000;

SELECT * FROM #HighValueOrders;
```

## Table variables
`DECLARE @T TABLE (...)` creates a table variable. Its optimization and behavior differ from temp tables; choose based on workload and test performance.

## Practice
Create a view for reporting and a temporary table for a multi-step analysis.
