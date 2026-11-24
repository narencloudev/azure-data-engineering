# Indexes and Query Performance

## What is an index?
An index is a data structure that helps SQL Server locate rows without scanning the entire table in many cases. Indexes consume storage and add work to data modifications.

## Common index types
- **Clustered index**: defines the row storage order at the leaf level; a table can have one.
- **Nonclustered index**: separate structure containing key values and row locators; a table can have multiple.
- **Unique index**: enforces uniqueness.
- **Filtered index**: indexes rows meeting a predicate.

```sql
CREATE INDEX IX_Orders_CustomerID_OrderDate
ON Sales.Orders (CustomerID, OrderDate)
INCLUDE (TotalAmount);
```

## Practical tuning workflow
1. Identify the slow query and business requirement.
2. Capture the actual execution plan and runtime metrics.
3. Check row estimates, scans/seeks, joins, sorts, spills, and key lookups.
4. Review predicates and join conditions.
5. Check indexes and statistics.
6. Change one thing at a time and compare results.

## Good practices
- Avoid `SELECT *` in production queries.
- Return only required rows and columns.
- Keep predicates sargable where possible (avoid wrapping indexed columns in functions unnecessarily).
- Do not add indexes blindly; measure write and storage impact.

## Practice
Inspect an execution plan for a filtered query and explain the operators you see.
