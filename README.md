# C³ Accessory Price Tag Generator

Self-contained HTML tool that prints Blufox accessory fact tags at 4" × 1.375",
14 to a US Letter sheet, matching the `BFM Accessory_FactTags_4x1.375_multi` template.

**Live:** https://blufoxmobile.github.io/Price-Tag-Generator/

- 60 numbered scan slots — scan and it advances to the next box automatically
- Search by product name or SKU for the items with no barcode on file
- Paste a list of UPCs into any slot to fill many at once
- Vector PDF output with a shared hairline cut grid, 14 tags per sheet

## Updating prices each month

Pricing lives in the `PRODUCT_DATA` array inside `index.html`, built from the monthly
**Accessory Fact Tag Prices** spreadsheet (Product SKU / Product Name / Default Price / Bar Code).

Notes on that spreadsheet:

- Some rows carry **two comma-separated barcodes** for one product — register both.
- Some rows have an unusable Bar Code (`0` or `#N/A`). Those products are reachable
  through the search box by name or SKU instead.
- The Bar Code column is numeric, so **leading zeros are lost**. UPC lookups normalise
  by stripping non-digits and then leading zeros, so a 12- or 13-digit scan both match.
- Product Name is truncated at 100 characters at source.

Current data: **September 2026 — 1,373 products.**
