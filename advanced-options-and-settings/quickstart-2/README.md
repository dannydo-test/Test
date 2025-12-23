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

# Additional Options

Additional options adjust migration behavior. Enable only what you actually need, because some options depend on target platform capabilities or may change how your data appears post-migration.

#### Common options you may see in Configuration

Depending on your source-target pair, options can include items such as:

* **Continue the previous migration**
* **Clear data on your Target Store before migrating**
* **Import description images to the Target Store**
* **Migrate SEO URLs**
* **Preserve Order IDs (where supported)**
* **Migrate images**
* **Migrate metadata**
* **Platform-specific switches relevant to the target cart**

#### Option selection principles

* **Prefer correctness over completeness**

If an option introduces uncertainty, validate with Demo results before applying it to Full Migration.

* **Enable only target-compatible options**

Some targets accept direct URL structures and metadata cleanly, others require additional platform configuration.

* **Treat options as part of your reusable setup**

Your configuration is intended to carry forward to Full Migration and later Recent Data Migration within the same project.
