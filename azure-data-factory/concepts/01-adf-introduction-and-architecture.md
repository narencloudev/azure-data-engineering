# Azure Data Factory: Introduction and Architecture

## What is Azure Data Factory?
Azure Data Factory (ADF) is a cloud data integration service used to orchestrate and automate data movement and transformation workflows. ADF pipelines can connect to many data stores and services.

## Core architecture
A typical ADF workflow contains:
1. **Pipeline**: logical workflow made of activities.
2. **Activity**: a unit of work, such as copying data or running a notebook.
3. **Linked service**: connection information for a data store or compute service.
4. **Dataset**: describes the structure or location of data used by an activity.
5. **Integration Runtime (IR)**: compute/infrastructure bridge used for data movement, dispatching activities, or connecting to private networks.
6. **Trigger**: starts a pipeline on a schedule, event, or manual basis.
7. **Monitoring**: shows pipeline and activity execution details.

## Typical data flow
Source system → ADF pipeline → Copy/transform activity → Data Lake landing zone → downstream processing/reporting.

## ADF is an orchestrator
ADF coordinates movement and execution. It is not itself a general-purpose database or a replacement for every processing engine. Heavy transformations may run in Databricks, SQL, or other compute services.

## Practice
Draw a simple architecture that copies daily CSV files from a source folder into an ADLS Gen2 raw container.
