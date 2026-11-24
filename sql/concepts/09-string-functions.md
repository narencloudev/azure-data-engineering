# SQL Server String Functions

String functions transform or inspect text.

## Common functions
- `LEN(text)`: number of characters, excluding trailing spaces.
- `DATALENGTH(value)`: bytes used to represent the expression.
- `TRIM(text)`: removes leading and trailing spaces/characters (SQL Server version support applies).
- `LTRIM` / `RTRIM`: remove leading / trailing spaces.
- `UPPER` / `LOWER`: change letter case.
- `LEFT` / `RIGHT`: extract from either end.
- `SUBSTRING(text, start, length)`: extract a section.
- `CHARINDEX(find, text)`: find a substring position.
- `REPLACE(text, old, new)`: replace occurrences.
- `CONCAT(...)`: concatenate values, treating NULL as empty text.

```sql
SELECT
    CustomerName,
    LEN(CustomerName) AS NameLength,
    UPPER(TRIM(CustomerName)) AS CleanName
FROM dbo.Customers;
```

## Example: extract domain
```sql
SELECT Email,
       SUBSTRING(Email, CHARINDEX('@', Email) + 1, LEN(Email)) AS EmailDomain
FROM dbo.Customers
WHERE Email LIKE '%@%';
```

## Practice
1. Remove extra spaces from customer names.
2. Extract the first three characters of a product code.
3. Find the position of `@` in an email address.
