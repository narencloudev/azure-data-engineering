# Practice projects

## Project 1: Daily CSV ingestion
**Goal:** Copy daily CSV files from a landing area into a Bronze data lake folder.

**Build:** linked services, datasets, parameterized pipeline, Copy activity, and a schedule trigger.

**Validate:** file exists at the destination, row count is plausible, and pipeline run is successful.

## Project 2: Multi-file ingestion
**Goal:** Process multiple files from a folder.

**Build:** Get Metadata, Filter, ForEach, and Copy activity. Add a clear path for missing or invalid files.

**Validate:** each expected file is handled and failures are visible.

## Project 3: Metadata-driven ingestion
**Goal:** Use one reusable pipeline to ingest multiple configured tables or files.

**Build:** configuration source, Lookup, ForEach, parameterized child pipeline, logging, and incremental-load design.

**Validate:** adding a new configuration entry does not require duplicating the pipeline.

## Suggested portfolio evidence
- Architecture diagram
- README explaining business problem and design
- Sample input and output data (synthetic only)
- Pipeline screenshots
- Run monitoring screenshots
- Known limitations and future improvements

## Cost discipline
Use small test datasets, avoid leaving compute active, and check the current Azure pricing for any service before enabling it. Do not add optional services unless the project requirement needs them.
