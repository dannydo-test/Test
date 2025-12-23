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

# Review Demo Results

#### Purpose

Verify that the demo data arrived correctly, is usable on the Target Store, and that any gaps are classified correctly before you configure and run the full migration.

#### What to review (quick validation checklist)

Log in to your **Target Store admin** and inspect the migrated sample:

* **Products**
  * Titles, descriptions, SKUs, pricing
  * Main images and gallery images
  * Variants and options (size, color) behave as expected
* **Categories / Collections**
  * Hierarchy appears correctly (parent-child where applicable)
  * Demo products appear in expected categories or collections
* **Customers and Orders**
  * Customer records exist with correct contact info
  * Orders are linked to the correct customers and products
* **Content**
  * Blog posts and key CMS pages are present
* **SEO basics (if business-critical)**
  * Check URL structure and basic metadata behavior on the Target platform

#### How to interpret gaps

When you find an issue, it generally falls into one of two categories:

1. **Configuration or mapping adjustment**
   * Something that can be corrected through entity selection, migration options, or attribute/field mapping.
2. **Custom Migration requirement**
   * Non-native or highly customized scenarios (third-party app data, complex custom fields, special transformation rules) that require custom jobs.

#### Output of this step

Before moving on, you should be able to state:

* “Connections work.”
* “The core structure looks correct or is fixable via configuration.”
* “Any non-standard needs are identified early (Custom Migration inputs).”
