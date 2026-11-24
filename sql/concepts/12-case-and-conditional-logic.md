# CASE and Conditional Logic

`CASE` returns a value based on conditions. It can be used in SELECT, ORDER BY, and other expressions.

```sql
SELECT OrderID,
       TotalAmount,
       CASE
           WHEN TotalAmount >= 10000 THEN 'High'
           WHEN TotalAmount >= 5000 THEN 'Medium'
           ELSE 'Low'
       END AS OrderCategory
FROM Sales.Orders;
```

## Searched vs simple CASE
- Searched CASE uses conditions such as `WHEN Amount > 100`.
- Simple CASE compares one expression to values, such as `CASE Status WHEN 'O' THEN ...`.

## Conditional aggregation
```sql
SELECT
    CustomerID,
    SUM(CASE WHEN Status = 'Completed' THEN TotalAmount ELSE 0 END) AS CompletedSales,
    SUM(CASE WHEN Status = 'Cancelled' THEN 1 ELSE 0 END) AS CancelledCount
FROM Sales.Orders
GROUP BY CustomerID;
```

## Notes
- Conditions are checked in order.
- The first matching branch is returned.
- Ensure all result branches have compatible data types.
- Add `ELSE` when you want an explicit fallback.

## Practice
Classify employees into salary bands and calculate completed vs cancelled order totals.
