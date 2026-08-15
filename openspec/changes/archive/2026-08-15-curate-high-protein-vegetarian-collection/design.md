# Design

## Data model

Each checked recipe record stores its publisher, source URL, format, India-fit
assessment, dietary tags, source ingredient names, published serving macros,
serving basis, and verification note. Protein density is derived only from the
published protein and calorie values on that same serving basis.

## Catalogue policy

1. Every listed recipe is egg-free vegetarian.
2. Every listed recipe has at least 10 g published protein per serving.
3. Every listed recipe has at least 10 g protein per 100 kcal after deriving
   the ratio from the same published serving macros.
4. The collection contains no more than five drinks in its initial 34 items.
5. Default curated order ranks meals and useful food components before breads,
   breakfasts, bars, desserts, and drinks. User-selected sorts remain purely
   metric or alphabetical.
6. India fit is a practical editorial label: `easy`, `adaptable`, or
   `specialty`. It does not imply universal availability.

## Interface changes

- Replace the single creator banner with a collection standard banner that
  states the two nutrition gates and the 29-food/5-drink composition.
- Add format and India-fit dropdowns to the filter rail.
- Show format, publisher, and India fit in each recipe identity.
- Rename the source action from “Watch” to “Recipe” because sources include
  both blogs and YouTube.
- Replace ingredient-estimate audit language with published-macro provenance,
  serving basis, and a direct source credit.

## Verification

- Unit tests enforce every collection gate, drink count, default food-first
  order, source-link presence, and filter behavior.
- The snapshot checker validates counts and derived densities.
- Astro builds successfully and the page is smoke-tested at desktop and phone
  widths.
