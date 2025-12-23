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

# Select What to Migrate

Selecting entities determines which data types Next-Cart will move from your Source Cart to your Target Cart.

For a first full migration, you typically select all entities required to fully rebuild your store’s operational state in the new platform. For later runs, you can narrow the selection to reduce duplication and processing time.

#### How to select entities

1. **Open your migration project** (the same project used for your Demo Migration, if applicable).
2. Go to the **configuration screen** and locate the **Entities** section.
3. Select the entity types you want to migrate. Common entities include:
   * Products
     * Reviews
   * Categories or Collections
   * Customers
   * Orders
   * Coupons or Discount Codes
   * Posts
   * Pages
4. Save your selection before moving to mapping and options.

#### Practical selection rules

* **Avoid broken relationships**

Orders usually reference customers, products, shipping, taxes, and discounts. If you migrate orders, you should also migrate the supporting entities needed for those orders to render correctly on the target.

* **Validate with a Demo first**

Your Demo Migration should include enough entities to verify data structure, mapping, and feasibility before you run a Full Migration.

* **Narrow scope for follow-up runs**

For later runs (including Recent Data Migration), select only the entities that actually changed since the last run, when that aligns with your update plan.
