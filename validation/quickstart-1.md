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

# Common Data Mismatches

This page helps you classify mismatches quickly so you do not waste time chasing expected platform differences.

#### 1) Entity counts do not match

**Common causes:**

* Source includes inactive, archived, or deleted records that the target does not store in the same way
* Target merges or reshapes entities (for example, categories become collections, or attribute structures differ)
* Filters were applied (selective migration, export subset, date range)
* The comparison is being done in different views (admin list filters, pagination, “published only” views)

**What to do:**

* Compare counts using consistent scope and status filters on both platforms
* Validate by sampling records rather than relying on total counts alone
* Confirm whether the entity type has a one-to-one representation on the target

#### 2) Variants, options, or attributes look different

**Common causes:**

* The target platform has different limits or structural rules
* The target combines options differently than the source
* Certain attribute types do not exist as first-class entities on the target

**What to do:**

* Validate high-complexity products first
* Confirm the target’s constraints and how products were reshaped
* If a subset is unacceptable, the resolution is typically configuration or a defined custom handling requirement

#### 3) Missing images or broken galleries

**Common causes:**

* Target image size limits
* CDN or security layer blocks download (example: source store protected by CDN settings)
* Image folder moved to a custom path and KitConnect cannot locate it
* Unsupported image format on the target
* Target server restriction such as `allow_url_fopen` disabled for open-source targets

**What to do:**

* Identify which cause applies, fix the root condition, then re-run a limited scope migration for products with images

#### 4) Order totals do not match exactly

**Common causes:**

* Tax inclusive vs tax exclusive mode differences
* Rounding behavior differences between platforms
* The target recalculates taxes or discounts differently than the source
* Shipping and discount interaction rules differ

**What to do:**

* Confirm the target tax configuration first
* Compare line-level composition rather than totals alone
* Establish an acceptable tolerance if the business allows it, or define a strict preservation requirement if needed

#### 5) Customer passwords do not work

**Common causes:**

* Password migration is not possible when the target is SaaS
* The Customer Password Plugin is not installed or is installed incorrectly
* Source and target hashing methods do not align for the chosen plugin path

**What to do:**

* Confirm whether your scenario supports password migration at all
* If supported, confirm plugin installation and test accounts
* If not supported, validate password reset experience and customer communications plan

#### 6) Categories, collections, or navigation looks wrong

**Common causes:**

* The target platform represents taxonomy differently
* Menu and navigation are often theme- or configuration-driven and not purely data-driven
* Some category relationships cannot be preserved exactly

**What to do:**

* Validate product grouping correctness first
* Treat storefront navigation as a separate target configuration task after data correctness is confirmed

#### 7) Blog and CMS pages look “broken”

**Common causes:**

* Page builders, themes, and HTML rendering differ
* Embedded widgets and scripts do not translate
* Styling is not portable as data

**What to do:**

* Validate that content exists and is associated correctly
* Rebuild styling and layout in the target theme or page builder as a post-migration task
