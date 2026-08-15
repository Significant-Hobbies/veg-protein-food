# Design

## Data flow

```mermaid
flowchart LR
  Y[Public video descriptions] --> P[Ingredient and result parser]
  P --> M[USDA ingredient matcher]
  P --> C[Creator calories and protein]
  M --> G[Coverage gate]
  C --> G
  G --> S[Checked recipe snapshot]
  S --> D[Astro dashboard]
```

## Decisions

1. Store the fetched public descriptions as a reproducible source cache beside
   the snapshot; do not require network access during tests or builds.
2. Treat separators as boundaries between recipe subsections, not the end of
   the entire ingredient list. Continue collecting quantity-led lines until a
   results, instructions, or unrelated prose section begins.
3. Do not classify an ingredient line as a nutrition result merely because it
   contains the word "protein". Results require an explicit total/content
   pattern.
4. Prefer a creator-stated calorie total when available. Otherwise use the USDA
   estimate only when every material ingredient line has a resolved quantity.
5. A density ratio may use creator protein with creator calories, or estimated
   protein with estimated calories. Creator protein may use complete estimated
   calories only when all material lines are covered. Never use creator protein
   with partial calories.

## Verification

- Parser and ratio-gating unit tests.
- Fixed-value regression checks for the five audited recipes.
- Snapshot reconciliation and Astro production build.
