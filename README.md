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
metaLinks:
  alternates:
    - https://app.gitbook.com/s/yE16Xb3IemPxJWydtPOj/getting-started/quickstart
---

# How Next-Cart Works

Next-Cart is a migration service and toolset that helps you transfer store data from one e-Commerce platform (Source Cart) to another e-Commerce platform (Target Cart) while keeping the store operational during the migration window.

A typical project follows a controlled lifecycle, which includes a Demo Migration (to validate mapping and feasibility), a Full Migration (to transfer the full agreed scope), and a Recent Data Migration (to sync changes made after the full run, typically before go-live).

At a system level, Next-Cart combines three components: a server-side migration engine, secure store connection methods (API, KitConnect, or file-based access), and an Account Dashboard where you configure, run, and monitor migrations.

Migrations run on the server side, so processing continues even if you close your browser. The result is an execution flow that is predictable for non-technical users, while still allowing technical teams to control access, scope, and verification.

#### What data is processed during migration

Depending on the platforms involved and your selected scope, Next-Cart can process common eCommerce entities such as:

* **Catalog data**: products, categories, attributes, variants or options, images
* **Customer data**: customers, addresses, customer groups (where supported)
* **Order data:** orders, order items, order statuses (where supported)
* **Content and marketing data** (where supported): blog posts, CMS pages, coupons, reviews
* **SEO-related data** (where supported): meta titles and descriptions, URLs and redirect-related inputs

#### No-downtime principle

Next-Cart is designed so your Source store can continue operating while data is copied. The migration is a “copy” process rather than a “move”.

This is why a final synchronization step (Recent Data Migration) is commonly used to bring the Target store up to date right before launch.

#### Data handling and security overview

During an active migration, Next-Cart processes store data to run migrations and support troubleshooting. Store data is retained only as long as necessary to complete migration runs and resolve issues during the applicable support window, then deleted according to the governance policies. Connection access is handled using least-privilege principles whenever possible, and you should revoke any temporary credentials after completion.

For formal details, refer to:

* **Data Security Policy**
* **Privacy Policy**
* **GDPR Compliance**
* **Terms of Service**
