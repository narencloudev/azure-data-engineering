# Incremental Loads and Watermarks

Incremental loading moves only data changed since a previous successful load, reducing repeated work.

## Watermark concept
A watermark stores the last successfully processed boundary, such as the maximum `ModifiedDate` or a monotonically increasing ID.

## Basic pattern
1. Read the previous watermark.
2. Read source rows newer than that watermark.
3. Copy/process those rows.
4. Validate the load.
5. Update the watermark only after successful completion.

Example query:
```sql
SELECT *
FROM dbo.SourceOrders
WHERE ModifiedDate > @LastWatermark
  AND ModifiedDate <= @CurrentHighWatermark;
```

## Important design decisions
- Use a stable, indexed change column where possible.
- Define how to handle records updated with the same timestamp.
- Consider a composite watermark such as `(ModifiedDate, PrimaryKey)`.
- Account for deletes using soft-delete flags, change tracking, CDC, or periodic reconciliation.
- Update the watermark only after the target is safely committed.
- Design reruns to be idempotent.

## Practice
Design a watermark table with source name, last successful watermark, run ID, and update timestamp.
