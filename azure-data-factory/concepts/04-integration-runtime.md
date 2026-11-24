# Azure Data Factory Integration Runtime

Integration Runtime (IR) is the compute infrastructure used by ADF to provide data integration capabilities.

## Main types
- **Azure IR**: managed compute for data movement, data flows, and dispatching activities in supported scenarios.
- **Self-hosted IR**: installed on a machine or VM to access private/on-premises networks and data stores.
- **Azure-SSIS IR**: runs SQL Server Integration Services packages in Azure.

## Choosing an IR
Consider where the source and destination are located, network access, supported connectors, data volume, region, and cost.

## Self-hosted IR considerations
- Install on a supported, stable machine.
- Ensure outbound network access and required firewall rules.
- Plan high availability for production workloads.
- Keep the runtime updated and secure.

## Cost awareness
IR type, activity type, data volume, data flow compute, and execution duration affect cost. Check current Azure pricing before running workloads.

## Practice
Choose an IR for (a) Azure Blob to ADLS, (b) an on-premises SQL Server behind a firewall, and (c) a legacy SSIS package.
