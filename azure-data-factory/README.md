# Azure Data Factory Learning

Work through the numbered concept files in order. Use small test datasets and avoid unnecessary Azure resource runs.

## Topics
- [Adf Introduction And Architecture](concepts/01-adf-introduction-and-architecture.md)
- [Adf Factory Pipelines Activities](concepts/02-adf-factory-pipelines-activities.md)
- [Linked Services And Datasets](concepts/03-linked-services-and-datasets.md)
- [Integration Runtime](concepts/04-integration-runtime.md)
- [Copy Activity](concepts/05-copy-activity.md)
- [Parameters Variables Expressions](concepts/06-parameters-variables-expressions.md)
- [Control Flow Activities](concepts/07-control-flow-activities.md)
- [Triggers And Scheduling](concepts/08-triggers-and-scheduling.md)
- [Incremental Loads And Watermarks](concepts/09-incremental-loads-and-watermarks.md)
- [Metadata Driven Frameworks](concepts/10-metadata-driven-frameworks.md)
- [Error Handling Retries And Idempotency](concepts/11-error-handling-retries-and-idempotency.md)
- [Monitoring Logging And Alerts](concepts/12-monitoring-logging-and-alerts.md)
- [Data Lake Zones And File Formats](concepts/13-data-lake-zones-and-file-formats.md)
- [Security Managed Identity Key Vault](concepts/14-security-managed-identity-key-vault.md)
- [Git Integration And Cicd](concepts/15-git-integration-and-cicd.md)
- [Performance Cost And Best Practices](concepts/16-performance-cost-and-best-practices.md)
- [Adf End To End Practice Project](concepts/17-adf-end-to-end-practice-project.md)

-----------------------------------------------------------------------------------------------

# Azure Data Factory Learning Guide

A beginner-friendly, practical guide to Azure Data Factory (ADF). Follow the concepts first, then study activities and triggers, and finally complete the exercises and project.

## Suggested learning order
1. Read `concepts/01-adf-introduction.md` through `16-security-and-key-vault.md`.
2. Study the activity guides and understand when each activity is used.
3. Learn the three trigger types.
4. Complete beginner, intermediate, and advanced exercises in order.
5. Build the project described in `projects/README.md`.

## Core pipeline flow
**Source → Linked service → Dataset → Pipeline activity → Sink**

## Cost-conscious practice
- Prefer small sample files and short test runs.
- Stop or delete resources that are not needed.
- Check pricing before creating managed services or running data flows.
- Use existing storage/resources where practical; avoid leaving compute running.
