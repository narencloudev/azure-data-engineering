# Copy Activity

Copy Activity moves data from a source to a sink.

## Main configuration
- Source: connector, table/query or file path, and read options.
- Sink: destination connector, table/path, and write behavior.
- Mapping: source-to-sink column mapping.
- Performance: partitioning, parallel copies, staging, and fault-tolerance options where supported.

## Common patterns
- Database table → lake Parquet.
- CSV file → ADLS raw folder.
- REST API → landing storage.
- One storage account → another storage account.

## File formats
Common lake formats include delimited text, JSON, Avro, ORC, and Parquet. Parquet is columnar and often useful for analytics.

## Incremental vs full copy
- Full load copies the complete selected dataset.
- Incremental load copies only records/files considered new or changed according to a defined change-detection strategy.

## Reliability
Validate row counts, schema, file sizes, and business totals. Configure retry and timeout thoughtfully; retries can repeat work if the operation is not idempotent.

## Practice
Copy a CSV file to an ADLS raw folder and verify the output path and row count.
