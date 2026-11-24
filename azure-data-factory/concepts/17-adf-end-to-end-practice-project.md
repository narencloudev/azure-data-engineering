# ADF Practice Project: Metadata-Driven File Ingestion

## Scenario
A data team receives daily CSV files from several business partners. New source folders are added over time. The team needs a repeatable ingestion process with audit logging and safe reruns.

## Target architecture
Partner CSV folders → ADF parent pipeline → configuration lookup → ForEach → reusable child pipeline → ADLS raw zone → audit log.

## Functional requirements
1. Read active source definitions from a configuration table or controlled metadata file.
2. Process each configured source.
3. Check whether expected files exist.
4. Copy files into source-specific raw folders.
5. Record run status, timestamps, and error details.
6. Support reruns without creating duplicate outputs.
7. Send or expose failure notifications.
8. Keep credentials out of source control.

## Suggested phases
- Phase 1: manual single-file copy.
- Phase 2: parameterized pipeline and dataset.
- Phase 3: metadata lookup and ForEach.
- Phase 4: audit logging and failure handling.
- Phase 5: incremental file processing and idempotent reruns.
- Phase 6: documentation and Git-based version control.

## Deliverables
- Architecture diagram.
- Pipeline and dataset inventory.
- Metadata/control table design.
- Audit table design.
- Test cases for success, missing file, invalid file, and rerun.
- Cost notes and limitations.

## Portfolio honesty
Document only the services and features actually implemented. Clearly label planned extensions.
