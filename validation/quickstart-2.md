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

# Post-migration Tasks and Go-live Runbook

Use this runbook after Full Migration is validated and you are preparing to launch the Target store.

The goal is to minimize risk by controlling timing, syncing final data, and validating the live environment immediately after cutover.

#### Phase 1: Pre go-live preparation

* **Confirm target store readiness:**
  * Payments configured (test mode validated)
  * Shipping rules configured
  * Tax settings configured
  * Email sending configured
  * Core apps installed and tested
* **Confirm migration readiness:**
  * Full Migration completed successfully
  * Validation checklist passed on representative samples
  * Redirect plan prepared and validated on the target
* **Plan the cutover window:**
  * Choose a low-risk time window aligned with your order volume and internal staffing
  * Set a short change control window for catalog edits and promotions

#### Phase 2: Final sync with Recent Data Migration

* Confirm you will run Recent Data Migration on the **same project** as the Full Migration.
* Confirm connections are still valid (API tokens not expired, KitConnect accessible).
* Run **Recent Data Migration** close to launch to sync:
  * New orders and customers
  * New or updated products
  * Any other entities that changed since the last run
* After completion, validate:
  * New orders placed since the Full Migration exist on the target (sample)
  * Recent customer records exist (sample)
  * A small product sample reflects recent edits correctly

#### Phase 3: Cutover and production checks

* **Domain and DNS:**
  * Lower TTL ahead of time if your DNS strategy allows it
  * Perform domain cutover according to your DNS provider process
* Immediately after cutover, run **critical production checks**:
  * Homepage loads correctly
  * Category or collection navigation works
  * Product page renders correctly for key products
  * Checkout path works end-to-end (test order if possible)
  * Redirects work for top landing pages
  * Search and filtering behave acceptably

#### Phase 4: Post-launch monitoring and stabilization

* Monitor for the first 24 to 72 hours:
  * 404 errors and broken redirects on high-traffic pages
  * Checkout failures or payment gateway issues
  * Missing images reported by customers
  * Order confirmation emails and customer notifications
* Maintain a short stabilization backlog:
  * Fix high-impact issues first (checkout, redirects, critical product pages)
  * Defer cosmetic layout adjustments where business risk is low

#### Phase 5: Closeout

* **Security hygiene:**
  * Revoke and delete temporary API tokens
  * Remove KitConnect files from the server if used
  * Rotate any temporary passwords used for migration
* **Confirm internal documentation:**
  * Record final run timestamps
  * Record configuration version used at launch
  * Record known issues and resolution owners
