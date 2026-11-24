# SELECT, WHERE, ORDER BY, DISTINCT, TOP

## SELECT
Choose columns to return.
```sql
SELECT OrderID, CustomerID, OrderDate
FROM Sales.Orders;
```

## WHERE
Filters rows before they are returned.
```sql
SELECT *
FROM Sales.Orders
WHERE Status = 'Completed'
  AND OrderDate >= '2026-01-01';
```

Common operators: `=`, `<>`, `>`, `>=`, `<`, `<=`, `IN`, `BETWEEN`, `LIKE`, `IS NULL`.

## ORDER BY
Sorts the final result.
```sql
SELECT OrderID, OrderDate
FROM Sales.Orders
ORDER BY OrderDate DESC, OrderID ASC;
```

## DISTINCT and TOP
```sql
SELECT DISTINCT Country FROM dbo.Customers;

SELECT TOP (10) *
FROM Sales.Orders
ORDER BY OrderDate DESC;
```
`TOP` should normally be paired with `ORDER BY` when you need a predictable top-N result.

## LIKE patterns
- `'A%'`: starts with A.
- `'%son'`: ends with son.
- `'%data%'`: contains data.
- `'_a%'`: second character is a.

## Logical query processing
A useful simplified order is `FROM`/`JOIN`, `WHERE`, `GROUP BY`, `HAVING`, `SELECT`, `DISTINCT`, `ORDER BY`, then `TOP`. This explains why a SELECT alias is generally unavailable in `WHERE`.

## Practice
1. Return the five newest orders.
2. Find customers whose names begin with S.
3. Return unique customer countries.
