# Curate a high-protein vegetarian collection

## Why

The current homepage is an exhaustive single-channel ledger, but most of that
inventory does not meet the owner's protein-density bar. The product is moving
toward a smaller collection of genuinely useful vegetarian dishes from quality
recipe publishers and YouTube creators, with ingredients practical in India.

## What changes

- Replace the homepage inventory with 34 egg-free vegetarian recipes whose
  published serving macros meet both thresholds: at least 10 g protein and at
  least 10 g protein per 100 kcal.
- Credit the source publisher on every row and link directly to the original
  recipe or video.
- Add recipe-format and India-fit filters while preserving ingredient search,
  multi-exclusion, and sortable nutrition columns.
- Make the default curated order food-first and place the five qualifying
  shakes or smoothies after meals, savoury components, breads, breakfasts,
  bars, and desserts.
- Present publisher macros as source-published values rather than USDA
  estimates, and expose the stated serving basis and a verification note.

## Out of scope

- Scraping every recipe from the selected publishers.
- Recalculating publisher macros from ingredient quantities.
- Guaranteeing ingredient availability in every Indian city.
- Deployment, accounts, saved filters, or medical advice.

## Impact

The homepage copy, checked data snapshot, filter model, recipe rows, evidence
panel, tests, and product documentation change. Astro remains the only
production dependency.

## Capabilities

- New: `curated-vegetarian-collection` defines the 10+10 admission gate,
  food-first composition, source provenance, and practical filters.
- Modified: `recipe-nutrition-ledger` retires the exhaustive single-channel
  requirements and preserves responsive keyboard operation for the new ledger.
