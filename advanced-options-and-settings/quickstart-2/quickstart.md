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

# SEO Preserve: URL Redirect Implementation

Redirect implementation ensures that old URLs from search engines, bookmarks, or marketing campaigns correctly route to the new pages after go-live.

Redirect behavior is highly dependent on the target platform, and some platforms require additional apps or modules to manage redirects.

#### What to configure in Next-Cart

1. In your migration configuration, ensure **SEO URLs or URL Redirects** are enabled (if available for your project).
2. Confirm your configuration is saved before Full Migration.

#### What to configure on the target platform

1. Confirm redirects are supported and active on the target:
   * Native redirect tool, or
   * SEO app or redirect manager, or
   * Platform module that must be installed and enabled
2. If the platform auto-generates redirects when slugs change, confirm that it does not conflict with imported redirects.

#### How to validate redirects

1. Collect a set of old URLs (from search results, sitemap, analytics, or known landing pages).
2. Test them in a clean browser session.
3. Confirm:
   * They redirect (not 404)
   * They land on the correct new page
   * They do not create redirect chains or loops

#### If redirects fail

The most common causes are:

* Redirect generation or import was not enabled in the configuration
* A required redirect module/app on the target was not installed
* Domain cutover changed URL assumptions and the redirect map no longer matches the live structure
