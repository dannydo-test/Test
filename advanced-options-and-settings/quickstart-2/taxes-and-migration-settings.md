# Taxes and Migration Settings

Taxes are highly platform-dependent. Migration can move tax-related data stored in products and orders, but migration does not replace the need to properly configure your target platform’s tax rules, rounding, inclusion mode, and jurisdiction logic.

**What to decide before migrating taxes**

* **Historical accuracy vs. target recalculation**

Some platforms store tax values as order line calculations, while others recompute from rule sets. Decide whether your priority is preserving historical totals exactly, or allowing the target platform to recompute taxes based on new rules.

* **Tax-inclusive vs tax-exclusive display**

Confirm how the source store presents prices and whether the target must match that behavior.

* **Rounding behaviors**

Minor differences in rounding can create apparent mismatches in totals.

**Recommended workflow**

1. **Document your current tax setup** (regions, tax-inclusive setting, rounding, shipping taxability).
2. **Configure tax settings** to match your intended go-forward behavior.
3. Run a **Demo Migration** that includes representative orders and products.
4. Validate:
5. Product pricing display behavior
6. Order totals and tax line integrity
7. Shipping and discount interactions with tax totals
8. If mismatches exist, adjust target tax configuration first, then re-validate.
