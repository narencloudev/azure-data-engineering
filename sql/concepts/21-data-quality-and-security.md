# Data Quality, Security, and Safe SQL

## Data quality dimensions
- Completeness: required values are present.
- Validity: values follow allowed formats/ranges.
- Uniqueness: duplicate business records are controlled.
- Consistency: related fields agree.
- Accuracy: values reflect the real-world entity.
- Timeliness: data arrives when expected.

## Example checks
```sql
-- Duplicate business keys
SELECT Email, COUNT(*) AS RowCount
FROM dbo.Customers
GROUP BY Email
HAVING COUNT(*) > 1;

-- Missing required values
SELECT COUNT(*) AS MissingCustomerNames
FROM dbo.Customers
WHERE CustomerName IS NULL;
```

## Security basics
- Grant least privilege.
- Prefer roles over one-off user permissions.
- Avoid embedding passwords or secrets in scripts.
- Use parameterized queries to reduce SQL injection risk.
- Audit access and changes according to organizational policy.

## Practice
Write checks for null business keys, duplicate records, invalid amounts, and dates outside an expected range.
