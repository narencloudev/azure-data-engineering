# Error Handling, Retries, and Idempotency

## Error handling
A robust pipeline should make failures visible and preserve enough context to investigate them.

Capture:
- Pipeline run ID and activity run ID.
- Source and target names.
- Start/end timestamps and duration.
- Rows/files read and written where available.
- Status, error code, and error message.
- Retry count and watermark boundaries.

## Retries
Retries help with transient failures such as temporary service or network issues. They do not fix invalid data, wrong credentials, or broken logic. Set retry count and interval based on the failure type.

## Idempotency
An operation is idempotent when repeating it produces the same intended final state as running it once.

Ways to improve idempotency:
- Use deterministic file names and run-specific staging paths.
- Load to staging, validate, then publish.
- Use merge/upsert logic with stable business keys.
- Track processed files or batches.
- Avoid advancing watermarks before a successful target commit.

## Failure paths
Use failure dependencies or a structured child pipeline to log errors and notify responsible people. Preserve the original failure rather than masking it with a successful logging step.

## Practice
Simulate a failed copy, log the error details, and rerun without duplicating target data.
