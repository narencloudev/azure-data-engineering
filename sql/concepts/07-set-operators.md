# UNION, UNION ALL, INTERSECT, EXCEPT

Set operators combine the results of two queries. Each query must return the same number of columns in compatible data types and corresponding order.

## UNION
Combines results and removes duplicate rows.
```sql
SELECT CustomerID FROM Sales.CurrentCustomers
UNION
SELECT CustomerID FROM Sales.ArchivedCustomers;
```

## UNION ALL
Combines results and keeps duplicates. It is usually less work than `UNION` because duplicate elimination is not required.
```sql
SELECT CustomerID FROM Sales.CurrentCustomers
UNION ALL
SELECT CustomerID FROM Sales.ArchivedCustomers;
```

## INTERSECT
Returns distinct rows present in both query results.

## EXCEPT
Returns distinct rows from the first result that are absent from the second.

## UNION vs JOIN
- `UNION` stacks compatible result sets vertically.
- `JOIN` combines columns horizontally using a relationship.

## Practice
Create two simple result sets and compare the output of `UNION` and `UNION ALL`.
