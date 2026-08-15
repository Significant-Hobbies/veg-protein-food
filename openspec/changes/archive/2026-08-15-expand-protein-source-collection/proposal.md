# Expand the protein-source collection

## Why

The 10+10 admission rule naturally favors concentrated vegetarian protein
sources. Soya/TVP, tofu, tempeh, seitan, whey, and protein powder are acceptable
ingredients, but the collection currently underuses that permission and does
not let users distinguish the protein strategy behind each dish.

## What changes

- Expand the collection from 34 to at least 50 recipes using additional
  egg-free vegetarian foods with source-published same-serving macros.
- Admit whey and other protein powders explicitly alongside soy, tempeh,
  seitan, dairy foods, and legumes.
- Add a protein-source filter and show the primary protein strategy on every
  recipe row and details panel.
- Add only non-drink recipes in this expansion; keep the drink count fixed at
  five and keep all drinks after food in the default curated order.
- Prefer candidates practical with Indian ingredients or clearly label the
  specialist dependency.

## Out of scope

- Treating protein powder as inherently lower quality.
- Adding shakes, smoothies, or liquid-only recipes in this expansion.
- Recalculating source nutrition panels or inventing missing quantities.
- Deployment, accounts, or saved filters.

## Impact

The checked collection, admission checks, filter model, recipe identity,
details panel, tests, and durable product documentation change. Astro remains
the only production dependency.

## Capabilities

- Modified: `curated-vegetarian-collection` expands the food inventory and
  formalizes accepted concentrated protein sources without raising the drink
  count.
- Modified: `recipe-nutrition-ledger` adds protein-source filtering and visible
  source-strategy labels.
