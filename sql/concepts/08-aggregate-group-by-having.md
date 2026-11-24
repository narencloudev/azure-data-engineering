# Aggregate Functions, GROUP BY, HAVING

## Aggregate functions
Aggregates calculate one result from multiple rows:
- `COUNT(*)`: counts rows.
- `COUNT(column)`: counts non-NULL values.
- `SUM(column)`: adds values.
- `AVG(column)`: calculates the average of non-NULL values.
- `MIN` / `MAX`: smallest / largest value.

```sql
SELECT CustomerID,
       COUNT(*) AS OrderCount,
       SUM(TotalAmount) AS Revenue,
       AVG(TotalAmount) AS AverageOrder
FROM Sales.Orders
GROUP BY CustomerID;
```

## GROUP BY
Creates groups based on one or more columns. Every selected expression must generally be aggregated or included in the grouping.

## HAVING vs WHERE
- `WHERE` filters individual rows before grouping.
- `HAVING` filters groups after aggregation.

```sql
SELECT CustomerID, SUM(TotalAmount) AS Revenue
FROM Sales.Orders
WHERE OrderDate >= '2026-01-01'
GROUP BY CustomerID
HAVING SUM(TotalAmount) > 10000;
```

## Practice
1. Count orders per month.
2. Find customers with more than five orders.
3. Calculate total sales by product category.
