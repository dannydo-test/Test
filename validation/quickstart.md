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

# Validation Checklist

Use this checklist in three passes:

1. **Demo Validation**: structure and mapping correctness on a sample.
2. **Full Validation**: completeness and relationship integrity across the full scope.
3. **Pre Go-live Validation**: final sync confirmation and production readiness checks.

#### A. Baseline checks

* Confirm you are validating the **correct Target environment** (staging vs production).
* Confirm you validated the output of the **correct run** (Demo vs Full vs Recent Data Migration).
* Confirm your configuration (entities, mappings, options) matches what you intended to migrate.

#### B. Catalog validation

**Products**

* Spot-check a representative sample:
  * Top sellers
  * Most complex variants or options
  * Products with multiple images
  * Products with special pricing or sale rules
* Verify:
  * Title, description, SKU, price, inventory (if included)
  * Variant combinations and option labels
  * Product status and visibility rules
  * Image presence and correct association

**Categories or collections**

* Verify navigation logic:
  * Category hierarchy or collection grouping appears as expected
  * Products are assigned to the correct groups
  * Category or collection URLs are accessible

#### C. Customer validation

* Spot-check customer records:
  * Contact fields and addresses
  * Customer groups or segmentation (if applicable)
* Validate customer access behavior:
  * If both source and target are open-source and you use the Customer Password Plugin, confirm login works for at least one test account.
  * If your target is SaaS or password carryover is not supported, confirm the password reset workflow operates correctly.

#### D. Order validation

* Spot-check orders across different time periods and statuses:
  * Recent, mid-range, older orders
  * Cancelled, refunded, partially fulfilled, completed
* Verify:
  * Customer-to-order linking
  * Line items, quantities, discounts, shipping lines
  * Totals consistency within expected tolerance
  * Status mapping and fulfillment history expectations

#### E. Content and marketing data validation (if in scope)

* Blogs and CMS pages:
  * Page count and key pages exist
  * Layout differences are understood (platform rendering often differs)
* Coupons or discount codes:
  * Core rules exist (but verify the target platform’s discount engine behavior)
* Reviews:
  * Check sample products with reviews and ensure review associations remain correct

#### F. SEO execution validation (redirects and URLs)

* Confirm URL structure expectations for the target platform.
* Validate redirects using a priority list:
  * Top organic landing pages
  * High-performing paid landing pages
  * Top product and category URLs
* Confirm:
  * No 404 for high-value pages
  * Redirects land on the correct destination
  * No loops or excessive redirect chains

#### G. Store functionality validation (Target platform readiness)

These checks are often the difference between a successful launch and a “migration issue” that is actually platform configuration.

* Checkout and payments configured and testable (in test mode where possible)
* Shipping rules and rates configured
* Tax settings configured for go-forward operation
* Email sending and transactional templates configured
* Critical apps and integrations installed and confirmed (ERP, fulfillment, analytics, subscription tools)

#### H. Sign-off criteria

Before go-live, document a short set of acceptance criteria, such as:

* Representative sample validation passed for products, customers, and orders
* Redirect coverage validated for prioritized URL set
* Checkout path tested end-to-end
* Known issues are triaged and assigned to either “must fix” or “post-launch”
