# Data Lake Zones and File Formats

## Common lake zones
- **Raw / Bronze**: source-aligned data retained with minimal changes.
- **Verified / Silver**: validated, cleaned, standardized, and deduplicated data.
- **Business-ready / Gold**: curated data shaped for reporting and consumption.

Zone names vary by organization. Define the meaning and quality contract for each layer.

## File formats
- CSV: human-readable and simple, but weakly typed and often larger.
- JSON: flexible and useful for nested records.
- Parquet: compressed columnar format suited to analytical workloads.
- Delta Lake: table format built on Parquet with a transaction log and features such as ACID transactions and schema enforcement/evolution in supported engines.

## Folder design
Organize by source, entity, and sometimes ingestion date, for example:
`raw/erp/orders/ingest_date=2026-11-24/`

## ADF's role
ADF can orchestrate copies and transformations between zones. Databricks, SQL engines, or other services may perform more complex transformations.

## Practice
Design raw, verified, and business-ready paths for orders and customers.
