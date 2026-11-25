# Tumbling Window trigger

## Purpose
Starts pipeline runs for fixed, contiguous time windows. It maintains window state and supports dependencies between windows.

## Best for
Window-based processing where each interval must be processed and tracked, such as hourly partitions.

## Example
Process one hour of event data per window and depend on the previous window when required.

## Watch out
Understand window size, delay, concurrency, retries, and dependency behavior before enabling it.

## Exercise
Explain how a 1-hour window differs from a schedule trigger that fires every hour.
