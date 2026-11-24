# ADF Performance, Cost, and Best Practices

## Performance factors
- Source and sink throughput limits.
- Data volume and file sizes.
- Parallel copy settings and partitioning.
- Integration Runtime region and capacity.
- Network bandwidth and private connectivity.
- Transformation compute and configuration.

## Cost awareness
Costs depend on activity runs, data movement, data flow compute, IR configuration, and related Azure services. Pricing and free allowances can change; check the current Azure pricing calculator and subscription details before running workloads.

## Best practices
- Start with small test datasets.
- Parameterize reusable pipelines.
- Avoid unnecessary pipeline and activity runs.
- Prefer efficient file formats for analytics.
- Use sensible file sizes; avoid excessive tiny files.
- Monitor duration, throughput, and failure rates.
- Add validation and audit logging.
- Secure credentials and network paths.
- Make reruns safe and predictable.
- Document assumptions and operational ownership.

## Practice
Estimate which parts of a proposed pipeline may incur cost and identify low-cost ways to test it.
