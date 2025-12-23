# Order ID Preservation

Preserving order IDs means keeping your historical order identifiers consistent after migration, so internal teams and customers can reference the same order numbers across systems.

Whether this is possible depends on the target platform and how it manages order numbering.

#### What to validate first

* Can the target platform accept imported order IDs as the primary order number?
* If not, can you configure a plugin, module, or native setting to align order numbering?
* If neither is possible, can you store the original order ID as a reference field?

#### Recommended workflow

1. **Check target feasibility** before running Full Migration.
2. If supported, toggle the **Preserve Order IDs** in the Additional Options.
3. Run a **Demo Migration with orders** and verify:
   * Admin order number display
   * Customer-facing order number display (account pages and emails)
4. If true preservation is not supported:
   * Store the old order ID in a reference field (for example: “Original Order ID”)
   * Ensure it is searchable by staff and visible where needed for support workflows
