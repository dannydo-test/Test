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

# Mapping Options

Mapping controls how fields and values from your Source Cart translate into your Target Cart. Even when entity selection is correct, incorrect mapping can cause issues such as wrong visibility, wrong statuses, missing taxonomy structure, or incorrect tax classification.

#### What mapping typically includes

Mapping commonly applies to:

* Attribute or field alignment (source field to target field)
* Status and visibility values
* Tax classes
* Brand and manufacturer fields
* Product option structures (variants, options, attributes)

#### How to review mapping

1. Navigate to the **Advanced** **Attributes Mapping** in your migration configuration.
2. Review mappings that affect high-impact store behavior first:
   * Target Cart Options
   * Language Mapping
   * Location Mapping
   * Order Payment Status
   * Order Fulfillment Status
3. Keep mapping decisions consistent with your Demo results.
4. Save mapping changes and document any non-standard requirements you expect to repeat later.

#### When mapping becomes “custom”

If your source store relies heavily on custom fields, extensions, or platform-specific data structures, mapping may require custom logic rather than a simple source-to-target alignment.

In those cases, define the requirement precisely (field name, entity type, expected target placement, examples) before proceeding.

And connect with Next-Cart via Live Chat or Submit a Ticket to request "Custom Job" or "Custom Migration" and we will handle your custom request for the migration.
