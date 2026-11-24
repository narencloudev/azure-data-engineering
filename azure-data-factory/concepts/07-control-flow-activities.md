# ADF Control-Flow Activities

Control-flow activities determine how pipeline steps are coordinated.

## Lookup
Reads a small configuration result, often from a control table or file. It can return a first row or an array of rows depending on configuration.

## Get Metadata
Returns metadata about a file, folder, or supported dataset, such as existence, size, child items, or structure information.

## ForEach
Loops over an array of items. Sequential execution is useful when order matters; parallel execution can improve throughput but requires care with shared state and source limits.

## If Condition
Runs one branch when an expression is true and another when false.

## Execute Pipeline
Calls a child pipeline and can pass parameters. This helps build reusable modular workflows.

## Wait, Until, and Filter
- Wait pauses for a configured duration.
- Until repeats activities until a condition is met or limits are reached.
- Filter selects items from an input array.

## Practice
Use Lookup to read three table names, ForEach to process them, and Execute Pipeline to call a reusable child pipeline.
