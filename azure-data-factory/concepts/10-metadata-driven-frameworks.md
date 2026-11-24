# Metadata-Driven ADF Frameworks

A metadata-driven framework uses configuration data to control reusable ingestion pipelines rather than hard-coding one pipeline per source.

## Example control table
| SourceName | SourceType | SourceObject | LoadType | TargetPath | IsActive |
|---|---|---|---|---|---|
| Orders | SQL | dbo.Orders | Incremental | raw/orders | 1 |
| Customers | SQL | dbo.Customers | Full | raw/customers | 1 |
| LabResults | CSV | lab/results | Full | raw/lab-results | 1 |

## Typical workflow
1. Lookup active configuration rows.
2. ForEach configured source.
3. Call a reusable child pipeline.
4. Read source based on source type and load type.
5. Copy to a parameterized target.
6. Validate and log status.
7. Update watermark after success.

## Benefits
- Less duplicated pipeline logic.
- Easier onboarding of new tables/files.
- Central configuration and operational visibility.
- Consistent audit and error handling.

## Risks
- Configuration becomes a critical dependency.
- Dynamic SQL and paths must be validated.
- Different source types may require different handling.
- Avoid an overly generic design that becomes hard to debug.

## Practice
Create a configuration table for three sources and design a parent/child pipeline.
