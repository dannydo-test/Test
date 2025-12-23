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

# Acceptance Criteria and Sign-off

#### Purpose

Create a clear “definition of done” so both sides can validate outcomes consistently, resolve issues efficiently, and complete the migration without ambiguity.

#### How to define acceptance criteria

A good acceptance criteria set includes:

1. **Scope completeness**

* Which entities are included
* Any intentional exclusions or filters

2. **Sample-based validation**\
   Define a realistic sampling plan:

* Products: top sellers, most complex variants, products with multiple images
* Orders: recent, mid-period, old; include refunds and cancellations if relevant
* Customers: multiple addresses, repeat buyers, recent accounts
* Content: key CMS pages and representative blog posts

3. **Pass/fail rules**\
   Use measurable statements:

* “No missing variants in the sampled set”
* “All sampled orders contain correct line items and totals match within tolerance”
* “All prioritized URLs redirect correctly to intended destinations”

4. **Issue classification**\
   Define severity so remediation is predictable:

* Blocker: prevents checkout, breaks critical navigation, corrupts order history
* High: major catalog integrity issue affecting core products
* Medium: display inconsistencies or minor mapping mismatches
* Low: cosmetic content formatting differences, minor copy issues

#### Recommended sign-off workflow

1. Confirm the run is completed (Demo, Full, or Recent Data Migration)
2. Execute the Validation Checklist on your sampling plan
3. Record findings in a single ticket:
   * Issue summary
   * Record identifiers (product IDs, order numbers)
   * Screenshots and expected results
4. Next-Cart applies fixes (configuration adjustments or custom job refinements)
5. Re-run only the necessary scope where possible
6. Re-validate and confirm sign-off

#### What sign-off means operationally

Sign-off confirms:

* The migrated dataset meets your documented acceptance criteria
* Known issues are either resolved or approved for post-launch handling
* Final sync strategy is confirmed if the source store remained live after the full run

#### Final sync and launch readiness (common requirement)

If your source store continued receiving orders after the full run:

* Plan a **Recent Data Migration** close to go-live using the same migration project
* Perform a final spot-check on:
  * new orders since the full run
  * new customers
  * any high-change catalog items
