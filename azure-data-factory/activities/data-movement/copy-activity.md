# Copy activity

## Purpose
Copy activity moves data from a supported source to a supported sink. It is commonly used for ingestion and data replication.

## Typical configuration
1. Select a source dataset and linked service.
2. Select a sink dataset and linked service.
3. Configure mapping, format, and copy behavior as needed.
4. Debug with a small sample.
5. Monitor rows read/written and errors.

## Example
Copy `incoming/orders.csv` from a storage container to `bronze/orders/` in a data lake.

## Common mistakes
- Incorrect file path or permissions.
- Source and sink format mismatch.
- Assuming a successful copy guarantees clean business data.
- Copying large data during repeated debug runs without checking cost.

## Exercise
Copy a small CSV to a destination folder and verify the file contents.
