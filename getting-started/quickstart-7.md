---
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Re-run a Full Migration (Re-Migration)

#### Purpose

Re-run the full migration after you adjust configuration, entities, options, or mappings, typically to correct issues discovered during demo review or after a completed full run.

#### When to use re-migration vs Recent Data Migration

* Use Re-Migration when you change the configuration or need to correct how data is mapped or structured.
* Use Recent Data Migration when the configuration is stable, and you only need to sync new or changed data since the last run.

#### Practical cautions

Re-running a full migration can impact existing data already created on the Target Store during the previous run. Before re-running:

* Confirm what will be re-imported (entities selected).
* Ensure you have a plan to avoid confusion caused by duplicate or conflicting data on the Target Store, especially if you have already started manual edits after the first run.

#### Steps (high-level)

1. Open the same migration project in **Migration Tool Management**.
2. Update configuration (entities, options, mappings).
3. Save configuration.
4. Run **Full Migration** again and validate results.
