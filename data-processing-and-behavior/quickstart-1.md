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

# Platform Data Model Notes

Different platforms model the same business concepts in different ways. Next-Cart migrates data by translating between these models, but some differences have no perfect one-to-one mapping.

This page explains the most common platform model mismatches that affect results, how they typically appear after migration, and how to validate them.

#### 1) Categories, subcategories, and collections

Platforms vary in how they represent catalog organization:

* Some platforms use strict category trees (parent and child taxonomy).
* Others rely on collections or dynamic groupings.

**What to expect**

Category structures may appear as collections, or collection logic may require additional configuration on the target platform.

**Validation focus**

Confirm products appear in the intended groupings and navigation menus point to valid groupings.

#### 2) Variants, options, and attributes

Variant systems differ by:

* Maximum variants per product
* How options are combined
* Whether attributes are first-class catalog entities or product-level fields

**What to expect**

Products with complex option combinations may be reshaped to fit the target limits.&#x20;

**Validation focus**

Test representative products, especially those with many variant combinations, and confirm pricing, SKUs, and stock behave correctly.

#### 3) Product identifiers and uniqueness rules

Targets vary in how they treat:

* SKU uniqueness
* Product handles or slugs
* Internal IDs and import keys

**What to expect**

The target may auto-generate new handles or normalize slugs, which can affect SEO execution plans.

**Validation focus**

Confirm product URLs, SKUs, and any “primary key” behavior match target requirements.

**4) Customer accounts and password portability**

Cloud platforms generally do not allow password portability because password hashes are not available and login logic cannot be overridden.

**What to expect**

Password resets on first login for many cloud targets.

**Validation focus**

Confirm customer records migrated, then confirm the password reset flow works as expected.

#### 5) Orders, statuses, and fulfillment models

Order models differ in:

* Status naming and state transitions
* Fulfillment and shipment record structures
* Refund and credit memo representations

**What to expect**

Order statuses may map to nearest equivalents rather than matching labels exactly, and some fulfillment history may be represented differently.

**Validation focus**

Validate a sample of orders across different statuses and edge cases (refunded, partially shipped, cancelled).

#### 6) Discounts, coupons, taxes, and totals

Discount logic and tax storage can differ materially:

* Discount stacking rules
* Tax inclusive versus exclusive display
* Rounding and jurisdiction handling

**What to expect**

Historical totals can look different if the target recalculates taxes or discounts differently, even when line data is present.

**Validation focus**

Compare representative orders and verify that your target’s rules are configured for your go-forward model.

How to use these notes during execution

* Use them during Demo review to identify structural mismatches early.
* Use them during Configuration to adjust mapping options where available.
* Use them during Validation to set realistic acceptance criteria for model differences that do not have perfect equivalence.
