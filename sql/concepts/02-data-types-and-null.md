# SQL Server Data Types and NULL

## Why data types matter
A data type defines which values a column can store and influences storage, validation, and calculations.

## Common SQL Server types
| Type | Typical use |
|---|---|
| `INT`, `BIGINT` | Whole numbers |
| `DECIMAL(p,s)`, `NUMERIC(p,s)` | Exact decimal values, such as money or measurements |
| `FLOAT`, `REAL` | Approximate floating-point values |
| `VARCHAR(n)`, `NVARCHAR(n)` | Variable-length text; `N` supports Unicode |
| `CHAR(n)`, `NCHAR(n)` | Fixed-length text |
| `DATE` | Calendar date |
| `TIME` | Time of day |
| `DATETIME2` | Date and time with fractional-second precision |
| `BIT` | 0, 1, or NULL |

## NULL
`NULL` means a value is missing, unknown, or not applicable. It is not the same as zero or an empty string.

```sql
SELECT *
FROM dbo.Customers
WHERE PhoneNumber IS NULL;
```

Use `IS NULL` / `IS NOT NULL`, not `= NULL`.

## Handling NULL
```sql
SELECT CustomerName,
       ISNULL(PhoneNumber, 'Not provided') AS PhoneDisplay
FROM dbo.Customers;
```
`ISNULL` returns a replacement when its first argument is NULL. `COALESCE` can test multiple expressions and follows data-type precedence rules.

## Good practices
- Choose the smallest suitable type without sacrificing correctness.
- Use `DECIMAL` for exact financial calculations.
- Prefer `DATE` or `DATETIME2` for new date/time design.
- Avoid storing dates as text.

## Practice
1. Choose types for customer name, birth date, order total, and active flag.
2. Return rows where an email address is missing.
