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

# Choose Your Connection Method

Every migration begins by determining how Next-Cart will connect to your Source and Target environments.

The correct connection method depends on whether a platform is SaaS-hosted, open-source and self-hosted, or requires a file-based transfer.

#### Connection methods

**1) API connection**

Most common for SaaS platforms. You grant access using API keys, tokens, or app credentials generated in the platform’s admin environment.

**2) KitConnect (bridge script)**

Used primarily for open-source platforms where direct database-level connectivity is needed. KitConnect is deployed to your hosting environment to enable secure access for migration processing.

**3) File-based transfer (export files, FTP or SFTP)**

Used when a platform supports exporting data to files, when hosting constraints make other methods impractical, or when specific assets must be handled through file access.

#### What you need for each method

**API connection: what to prepare**

* Admin access to generate credentials
* Any required scopes or permissions enabled for the needed data domains
* A plan to revoke the token after migration is complete

Then proceed to: **API Credential Guides**

**KitConnect: what to prepare**

* Hosting access to upload files to your store environment
* Ability to locate or provide database connection information if required by your platform
* A plan to remove the KitConnect directory after completion

Then proceed to:

* **KitConnect Setup**

**File-based transfer: what to prepare**

* Export capability from your current platform (CSV, XML, XLS, SQL, or platform export format)
* If using FTP or SFTP:
  * Host, port, username, password or key-based auth
  * Correct directory path and permissions
* A defined mapping expectation for how export fields correspond to the Target platform

Then proceed to:

* **Export Data Guides**

#### Minimum connection validation before you run a migration

Before starting a demo or full run, confirm:

* Credentials are valid and have the required permissions
* The store endpoints resolve consistently (no intermittent DNS or SSL issues)
* If using KitConnect, confirm files are reachable and permissions are correct
* If using FTP or SFTP, confirm directory access and file read permissions
