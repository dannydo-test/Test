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

# Before You Begin: Requirements

This page covers the practical requirements you should confirm before you run a migration. Completing these items reduces avoidable connection failures, missing data, and validation delays.

#### 1) Access and ownership prerequisites

Ensure you have access to the Source and Target stores appropriate to your connection method:

* **Admin access** for SaaS platforms (to generate API credentials where required)
* **Hosting or server access** for open-source platforms (for KitConnect deployment and database connectivity)
* A clearly identified owner for each access domain:
  * Store admin owner
  * Hosting or infrastructure owner
  * Decision owner for what data must be migrated

#### 2) Source store readiness

* Confirm the Source store is stable (no ongoing database repairs, no major upgrades mid-migration)
* Identify and document any “special structures” that may affect scope:
  * Heavy variants, custom product fields, unusual category structures
  * Custom checkout or order status workflows
  * Data stored in third-party apps rather than the platform core
* If possible, plan a change control window before final sync:
  * Avoid bulk catalog edits or app changes right before Recent Data Migration

#### 3) Target store readiness

* Ensure the Target store is accessible and you can log in reliably
* Confirm any essential baseline settings are in place (language, currency, tax rules, shipping framework) before final validation
* Understand that some items may require post-migration configuration on the Target platform side, even if the data migrates correctly

#### 4) Scope and acceptance requirements

Before you run anything beyond a demo, define:

* What data must migrate (minimum acceptable scope)
* What “pass” means for validation (sample sets, required fields, key flows)
* Which items can be handled after go-live without blocking launch

#### 5) Security hygiene you should follow

* Use least-privilege credentials when possible
* Share credentials only through approved secure channels
* After completion:
  * Delete API tokens from SaaS platforms
  * Remove KitConnect files from your server
  * Rotate any temporary admin or SFTP passwords used for migration
