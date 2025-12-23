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

# What Migrates and What Does Not

Next-Cart migrates data by reading entities from your Source store, translating them into a structure your Target store can accept, and preserving relationships where possible (for example, orders linked to customers and products).

What is migratable depends on three factors: the **source platform model**, the **target platform model**, and the **capabilities exposed by each platform** (API access, database access, export formats, and feature support).

### **Commonly migrates in most store-to-store scenarios**

#### **Catalog and merchandising**

* Products (core fields, SKUs, pricing)
* Product images (subject to access, format, and target limits)
* Variants, options, and attributes (as supported by the target model)
* Categories, subcategories, or collections (based on target structure)
* Brands and manufacturers (mapped according to platform conventions)

#### **Customers and orders**

* Customers and customer addresses
* Orders and order line items
* Order relationships (customer-to-order, product-to-order line)

#### **Content and marketing entities (when supported by the platform pair)**

* Blog posts and CMS pages
* Coupons and discount codes
* Product reviews

#### **SEO-related content (execution level, when supported)**

* Page metadata such as titles and descriptions
* URL and redirect-related inputs when your target supports implementation workflows

#### **Migrates with conditions or platform constraints**

**Customer passwords**

* Supported only for open-source to open-source migrations when the Customer Password Plugin is used.
* Supported targets include: Magento, OpenCart, PrestaShop, WooCommerce or WordPress, Joomla or VirtueMart, and Shopware.
* If the target is a cloud platform, customers should expect a password reset workflow.

**Images**

* Image migration depends on the source allowing image downloads (CDN and security layers can block retrieval).
* Targets enforce file size limits and format support. Some platforms do not support formats like WebP, SVG, BMP, or GIF.

**Order IDs**

* True order ID preservation depends on whether the target can accept imported IDs as the displayed order number.
* If not supported, the typical fallback is storing the original order ID as a reference field.

**Taxes**

* Historical tax line data can migrate, but tax rules and calculations are controlled by the target platform configuration.
* Differences in rounding and inclusive or exclusive tax display can cause apparent mismatches.

**Typically does not migrate as “data,” or requires separate platform work**

These items are usually outside a migration’s data scope because they are not accessible, not portable, or not represented in the same way on the target platform:

* Theme and storefront design, templates, and page builders
* Apps, plugins, and extensions themselves (you must install and configure equivalents on the target)
* Payment method tokens, stored cards, and most payment gateway vault data
* Email sending configuration, transactional email templates, and marketing automations
* Analytics configurations and historical reporting setups
* Platform-level settings that must be reconfigured (shipping rules, tax rules, checkout settings)
* Third-party system integrations (ERP, fulfillment, CRM) unless included as a defined custom job with clear inputs

**How to confirm what will migrate for your specific project**

1. Use the **entity selection screen** in Configuration to see what is available for your source-to-target pair.
2. Run a **Demo Migration** and validate structure and mapping on the target.
3. If a requirement is not represented in the configuration or demo outputs, treat it as a **conditional item** that may require custom logic or separate platform work.
