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

# Customer Password Plugin

Customer passwords are typically stored as **irreversible** **hashes** on **most platforms**.

Password migration is only possible in specific scenarios because cloud platforms typically prevent access to password hashes and do not allow overriding login logic.

#### When password migration is supported

Password migration is supported when:

* **Source is open-source**
* **Target is an open-source platform that supports the Customer Password Plugin**

In this scenario, the migration transfers password hashes and the plugin enables the target store to verify old hashes during login.

#### How the plugin works

On login, the plugin:

1. Takes the password entered by the customer on the target store.
2. Applies the same hashing algorithm used by the source store.
3. Compares the result with the migrated hash.
4. If they match, login succeeds. The password may then be re-hashed using the target store’s native method for future logins.

#### Installation workflow

1. Confirm your migration includes the **Customer Password Plugin** option in your account dashboard.
2. Download it from **Account Dashboard → Migrations → Additional Modules**.
3. Install the plugin on the target store.
4. Test with a known customer account whose password you can verify.

#### If the source or target is cloud-based

Cloud-based platforms generally require customers to **reset passwords** on first login. Plan the transition accordingly (password reset flow, customer comms, optional social login configuration).
