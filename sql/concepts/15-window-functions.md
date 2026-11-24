# SQL Window Functions

Window functions calculate across a related set of rows while keeping individual rows in the result.

## OVER clause
```sql
SELECT
    OrderID,
    CustomerID,
    OrderDate,
    TotalAmount,
    SUM(TotalAmount) OVER (PARTITION BY CustomerID) AS CustomerTotal
FROM Sales.Orders;
```

- `PARTITION BY` divides rows into groups.
- `ORDER BY` defines order within a window.
- A frame such as `ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW` defines which ordered rows contribute.

## Ranking functions
- `ROW_NUMBER()`: unique sequential number.
- `RANK()`: ties share rank and leave gaps.
- `DENSE_RANK()`: ties share rank without gaps.
- `NTILE(n)`: distributes rows into n buckets.

## Offset functions
- `LAG()`: value from a preceding row.
- `LEAD()`: value from a following row.
- `FIRST_VALUE()` / `LAST_VALUE()`: value at a window boundary (frame definition matters).

## Running total
```sql
SELECT OrderDate, OrderID, TotalAmount,
       SUM(TotalAmount) OVER (
           ORDER BY OrderDate, OrderID
           ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
       ) AS RunningTotal
FROM Sales.Orders;
```

## Top N per group
```sql
WITH RankedOrders AS (
    SELECT *,
           ROW_NUMBER() OVER (
               PARTITION BY CustomerID
               ORDER BY TotalAmount DESC, OrderID
           ) AS rn
    FROM Sales.Orders
)
SELECT *
FROM RankedOrders
WHERE rn <= 3;
```

## Practice
1. Rank employees by salary in each department.
2. Calculate a running sales total.
3. Compare each month's sales with the previous month using `LAG`.
