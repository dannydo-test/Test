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

# Managed Migration Onboarding

#### Purpose

Establish a complete, executable setup so the Next-Cart team can run your Demo, Full, and (if needed) Recent Data Migration efficiently, with minimal back-and-forth.

#### What you prepare (customer responsibilities)

Provide the following before execution begins:

1. **Store access and ownership**

* Source store admin access (or API credentials, depending on connection method)
* Target store admin access (or API credentials)
* Hosting or server access details if KitConnect is required
* A named point of contact for approvals and questions

2. **Migration scope**

* Entities to migrate (products, categories or collections, customers, orders, content, coupons, reviews, redirects)
* Any scope limitations (date ranges, subsets, exclusions)
* Any business rules that affect behavior (for example: what order statuses must map)

3. **Target readiness (minimum)**

* Target store is accessible and stable
* Core settings that affect validation are decided (currency, language, tax mode)
* Any required apps or modules that impact data behavior are installed (for example: redirect management, customer password plugin if applicable)

4. **Validation requirements**

* Your acceptance criteria (what “pass” means)
* Your sampling expectations (which products or orders must be tested)
* Your go-live window (if there is a fixed deadline)

#### What Next-Cart executes (team responsibilities)

* Validate credentials and connectivity
* Run Demo Migration (or equivalent validation run)
* Apply standard configuration adjustments based on findings
* Run Full Migration after approval
* Assist with validation and remediation until the defined acceptance criteria are met
* Run Recent Data Migration if required before launch, within the purchased usage period

#### Recommended onboarding workflow

1. **Kickoff confirmation**
   * Confirm Source and Target platforms
   * Confirm connection method(s): API, KitConnect, export-based
   * Confirm migration project identifier (migration name or ID)
2. **Access verification**
   * Credentials tested
   * KitConnect installed if required
   * Export formats confirmed if file-based
3. **Demo run**
   * Demo executed
   * Demo findings summarized
   * Customer confirms whether gaps are acceptable, configurable, or require **"Custom Job"**
4. **Full run**
   * Full Migration executed
   * Validation performed against agreed checks
5. **Final sync (if needed)**
   * Recent Data Migration executed close to go-live
   * Final spot-check performed

#### What to include when you contact support during onboarding

To avoid delays, include:

* Migration project name or ID
* Source and target URLs
* Store login credentials (when needed)
* A short description of the request (onboarding, demo review, full run scheduling)
* Any hard deadlines and time zone
