# Correct nutrition-density data

## Why

The dashboard currently combines creator-stated protein for a complete recipe
with calories estimated from only the ingredient lines recognized by the USDA
matcher. Multi-part ingredient blocks and ingredients containing the word
"protein" can be dropped, which inflates the leading protein-per-100-kcal
values and makes the comparison misleading.

## What changes

- Re-extract ingredient lines from the public descriptions for all 278 videos.
- Preserve multi-part ingredient blocks and ingredients whose names contain
  nutrition words.
- Capture creator-stated calories when present.
- Calculate density only when protein and calories refer to the same complete
  recipe evidence; otherwise withhold the ratio.
- Add regression coverage for the recipes that exposed the failure.

## Out of scope

- Inferring servings or dividing whole recipes into portions.
- Inventing quantities absent from creator evidence.
- Automatic scheduled channel refresh or deployment.

## Impact

The checked snapshot, nutrition evidence, coverage counts, sorting results, and
explanatory copy may change. No runtime dependency or production deployment is
introduced.
