## Why

The recipe dashboard was incorrectly implemented inside an unrelated portfolio
operations console. It needs a standalone product boundary and recipe-specific
information architecture so users never encounter domains, search visibility,
or AI operations alongside nutrition data.

## What Changes

- Create an independent Astro repository and web app with no Fleet runtime,
  navigation, styling, or shared production dependency.
- Carry forward the reconciled 278-video source snapshot while displaying only
  the 264 ingredient-bearing long-form recipes.
- Preserve creator-stated protein and calculate conservative ingredient-based
  protein, calorie, fiber, and per-100-kcal estimates with explicit coverage.
- Add a dataset-backed ingredient exclusion dropdown, removable selected
  exclusions, dietary/coverage/source filters, sortable ledger headers,
  expandable evidence, and one direct YouTube link per recipe.
- Establish a distinct responsive Recipe Index visual system, an explicit
  Epic Mint Leaves creator page and credit, and a local preview.

## Capabilities

### New Capabilities

- `recipe-nutrition-ledger`: Search, filter, sort, compare, and inspect every
  ingredient-bearing recipe with honest estimate provenance and source links.
- `standalone-product-boundary`: Run and test the Astro product without Fleet
  code, navigation, shared dependencies, or deployment infrastructure.

### Modified Capabilities

None.

## Impact

Creates a sibling local repository at `/Users/sarthak/Desktop/recipe-dashboard`
with an Astro static web app, checked-in source snapshot, tests,
OpenSpec artifacts, and design evidence. No production deployment, GitHub repo,
Fleet catalog entry, or change to the Fleet main checkout is included.
