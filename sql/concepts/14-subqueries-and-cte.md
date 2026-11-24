# Subqueries and Common Table Expressions (CTEs)

## Subquery
A query nested inside another query. It can appear in SELECT, FROM, or WHERE.
```sql
SELECT *
FROM Sales.Orders
WHERE TotalAmount > (
    SELECT AVG(TotalAmount) FROM Sales.Orders
);
```

## EXISTS
Checks whether a subquery returns at least one row.
```sql
SELECT c.CustomerID, c.CustomerName
FROM Sales.Customers AS c
WHERE EXISTS (
    SELECT 1
    FROM Sales.Orders AS o
    WHERE o.CustomerID = c.CustomerID
);
```

`NOT EXISTS` finds rows with no matching row. It is often a clear choice for anti-join logic.

## CTE
A named query expression scoped to one statement.
```sql
WITH CustomerSales AS (
    SELECT CustomerID, SUM(TotalAmount) AS Revenue
    FROM Sales.Orders
    GROUP BY CustomerID
)
SELECT *
FROM CustomerSales
WHERE Revenue > 10000;
```

## Recursive CTE
A recursive CTE references itself and is useful for hierarchies. Use an appropriate termination condition and consider `MAXRECURSION`.

## CTE vs temporary table
A CTE is not automatically materialized or persisted. A temporary table stores rows in tempdb and can be indexed or reused across statements.

## Practice
Find customers whose sales exceed the average customer sales. Rewrite a subquery using a CTE.
