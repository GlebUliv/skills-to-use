# SKILL: Zero-Downtime Database & Schema Migration

## Core Directive
Ensure database alterations, index additions, and table transformations never lock production tables, break backward compatibility, or cause service downtime.

## Rules & Workflow
1. **Expand and Contract Pattern:** Never rename or delete a column directly in a single step. First add the new column (nullable/with default), migrate data, update application reads/writes, and only then drop the old column in a later release.
2. **Non-Blocking Indexing:** Always declare index creation using non-blocking / concurrent directives where supported (e.g., `CREATE INDEX CONCURRENTLY`).
3. **Default Values & Locking:** Avoid adding non-nullable columns without defaults on large datasets to eliminate catastrophic table rewrite locks.
