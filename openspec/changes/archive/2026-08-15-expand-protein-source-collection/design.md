# Design

## Collection policy

1. Every new recipe remains egg-free vegetarian.
2. Every new recipe publishes at least 10 g protein per serving and derives at
   least 10 g protein per 100 kcal from the same serving calories.
3. Whey, vegan protein powder, soy/TVP, tofu, tempeh, seitan, dairy foods, and
   legumes are valid protein strategies.
4. A dish is rejected only for failing the admission or evidence rules—not for
   using a concentrated protein ingredient.
5. This expansion adds food only. The five existing drinks remain available,
   categorized, and last in default order.

## Data model

Each recipe gains one or more normalized `proteinSources` values. The first is
the primary strategy shown in the row; all values participate in filtering.
Accepted labels are `soy-tofu-tvp`, `tempeh`, `seitan-gluten`, `whey-powder`,
`vegan-powder`, `dairy-food`, and `legumes`.

## Interface

- Add a dataset-backed Protein source dropdown beside format, India fit, and
  diet.
- Show a concise primary source tag in each recipe identity.
- Add the complete strategy list to the details panel.
- Keep “Curated · food first” as the default sort.

## Verification

- Automated checks enforce at least 50 recipes, exactly five drinks, all new
  rows as food, both nutrition gates, egg-free ingredients, published serving
  provenance, and valid protein-source labels.
- Filter tests cover every normalized source family and combined filters.
- Astro builds and desktop/390 px browser smoke tests confirm the added control
  and tags remain usable without horizontal overflow.
