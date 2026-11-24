# SQL Joins

Joins combine rows from tables using a related column.

## INNER JOIN
Returns matching rows from both sides.
```sql
SELECT o.OrderID, c.CustomerName
FROM Sales.Orders AS o
INNER JOIN Sales.Customers AS c
    ON o.CustomerID = c.CustomerID;
```

## LEFT JOIN
Returns every row from the left table and matching rows from the right. Unmatched right-side columns are NULL.
```sql
SELECT c.CustomerID, c.CustomerName, o.OrderID
FROM Sales.Customers AS c
LEFT JOIN Sales.Orders AS o
    ON c.CustomerID = o.CustomerID;
```

## RIGHT JOIN and FULL OUTER JOIN
- `RIGHT JOIN`: keeps every row from the right table.
- `FULL OUTER JOIN`: keeps matched and unmatched rows from both tables.

## CROSS JOIN
Returns every combination of rows (Cartesian product). Use carefully because row counts multiply.

## SELF JOIN
Joins a table to itself, for example employees to their managers.
```sql
SELECT e.EmployeeName, m.EmployeeName AS ManagerName
FROM dbo.Employees AS e
LEFT JOIN dbo.Employees AS m
    ON e.ManagerID = m.EmployeeID;
```

## Common mistakes
- Joining on the wrong columns.
- Forgetting that one-to-many relationships can multiply rows.
- Moving a right-table filter from `ON` to `WHERE` can turn a `LEFT JOIN` into inner-join-like behavior.
- Not checking duplicate keys or row counts.

## Practice
1. List all customers, including customers with no orders.
2. Find orders with no matching customer record.
3. Explain why a one-to-many join can increase the number of rows.
