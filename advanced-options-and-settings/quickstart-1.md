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

# Migrate Only Specific Data

By default, selecting an entity usually migrates **all records** of that entity type supported by the source and target pair.

When you need to migrate only a **subset** of data, you should define that scope explicitly, because partial migrations can introduce gaps if dependencies are not accounted for.

#### Common “specific data” scenarios

You may want selective migration when:

* You only need certain entity types (for example: **Products + Categories only**).
* You need filters such as **date range** (for example: last 6 months of orders).
* You need a specific segment (for example: a defined catalog subset).
* You need special modifications that change how data is structured.

#### How to scope a selective migration request

When you need a selective migration that goes beyond standard entity selection, document the scope in a clear, testable format:

* **Entities included:** (Products, Categories, Customers, Orders, etc.)
* **Filter logic:** (date range, status, SKU list, category list, customer group)
* **Dependency expectations:** (include linked customers for migrated orders, preserve parent-child product relationships)
* **Acceptance criteria:** (what “correct” looks like in the target store)

#### Dependency warning

Selective migration is most risky when filtering **orders** or **customers**. If you migrate only part of order history, confirm how you will handle:

* Customers referenced by migrated orders
* Products referenced by migrated orders
* Discounts, taxes, and shipping lines referenced by migrated orders

If you cannot define a safe scope that preserves these relationships, keep the migration broad and control the post-migration presentation through platform configuration instead.
