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

# Custom Migration Inputs

#### Purpose

Collect precise requirements and examples so the Next-Cart team can implement and validate custom handling through a **Custom Job** package.

Custom work is most successful when requirements are documented as testable rules, not general descriptions.

#### What qualifies as “custom” in practice

Custom Job is typically required when you need one or more of the following:

* Custom fields not supported by standard mapping
* Data that lives in extensions, plugins, or third-party apps (not in core entities)
* Transformations (for example: splitting products, merging attributes, rewriting option structures)
* Special handling of relationships (for example: non-standard category logic)
* Platform-specific constraints requiring engineered restructuring
* You have special, customized modification requests for the Migration Tool

#### Required inputs checklist (provide all that apply)

**1) Custom scope definition**

* Entity type(s) impacted (products, customers, orders, content)
* Field names and where they exist in the source (database field, metafield, custom attribute, plugin table, export column)
* Expected destination in the target (native field, metafield, custom attribute, tag, custom table)

**2) Rule specification (write it as “if/then”)**

Provide rules in a format the team can implement and test:

* If **\[source condition]** then map to **\[target field]** with **\[transformation]**
* Example format:
  * If source attribute `brand_name` exists, then write to target vendor field, normalized to title case
  * If product type is “bundle,” then map to grouped structure with child items preserved as line items (if supported)

**3) Examples (mandatory)**

Provide at least:

* 3 representative examples (normal cases)
* 3 edge cases (worst or most complex cases)\
  Examples should include:
* Source screenshots or exports
* Expected target result screenshots or descriptions
* Product IDs, order IDs, or customer IDs that can be found in both systems

**4) Data access required for custom extraction**

Depending on platform, custom work may require:

* Database access (read-only where possible)
* Export files that include custom columns
* Plugin or extension data sources
* API scopes beyond the default

**5) Validation definition for custom outputs**

Define how you will confirm the custom job is successful:

* Which records must be checked
* Which fields must match
* Acceptable tolerances or known limitations
* What constitutes a blocker vs a post-launch fix

#### Custom job execution workflow (high level)

1. Requirements intake and confirmation (scope, rules, examples)
2. Feasibility check and dependency confirmation (access and platform constraints)
3. Demo-level implementation validation (prove mapping and logic on a sample)
4. Full run execution
5. Validation against acceptance criteria
6. Final sync plan (Recent Data Migration) if needed

#### How to submit custom requirements efficiently

Use a single ticket thread per custom job, with:

* One section per requirement
* Clear field names and expected destinations
* Example IDs and expected results
* Attachments (exports, screenshots, schema notes where applicable)
