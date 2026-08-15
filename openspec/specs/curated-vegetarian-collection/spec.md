# curated-vegetarian-collection Specification

## Purpose
Provide a compact, source-linked collection of protein-dense egg-free
vegetarian recipes that favors useful dishes over drink-heavy content.
## Requirements
### Requirement: Nutrition admission gate

The product SHALL list only egg-free vegetarian recipes with source-published
serving macros of at least 10 g protein and at least 10 g protein per 100 kcal.

#### Scenario: Recipe clears both gates

- **WHEN** a recipe has published protein and calories for the same serving
- **AND** protein is at least 10 g and derived density is at least 10 g per 100 kcal
- **THEN** the recipe may appear in the collection

#### Scenario: Recipe fails either gate

- **WHEN** total protein or protein density is below its threshold
- **THEN** the recipe is excluded even if its title says high protein

### Requirement: Food-first composition

The expanded collection SHALL contain at least 50 recipes, SHALL retain exactly
five shakes or smoothies, SHALL add only non-drink recipes in this expansion,
and SHALL place all food formats ahead of drinks in the default curated order.

#### Scenario: Homepage first loads

- **WHEN** no user-selected sort is active
- **THEN** meals, components, breads, breakfasts, bars, and desserts appear
  before the five shakes and smoothies

#### Scenario: User chooses a metric sort

- **WHEN** the user selects protein, calories, or protein density
- **THEN** every matching recipe, including drinks, follows that metric sort

### Requirement: Source attribution and provenance

Every recipe SHALL identify its publisher, link directly to its original recipe
or video, and label protein and calories as source-published serving values.

#### Scenario: User inspects a recipe

- **WHEN** the recipe row or evidence panel renders
- **THEN** the publisher, serving basis, verification note, ingredients, and
  direct external source are available

### Requirement: Practical collection filters

The product SHALL preserve recipe and ingredient search plus removable
ingredient exclusions, and SHALL add filters for recipe format and India fit.

#### Scenario: User excludes an ingredient family

- **WHEN** one or more ingredient exclusions are selected
- **THEN** recipes matching any excluded family are removed

#### Scenario: User selects a format

- **WHEN** the user selects meals, components, breads, breakfasts, bars,
  desserts, or drinks
- **THEN** only recipes in that format remain

#### Scenario: User selects India fit

- **WHEN** the user selects easy, adaptable, or specialty
- **THEN** only recipes with that editorial availability label remain

### Requirement: Concentrated protein sources are allowed

The collection SHALL admit egg-free vegetarian dishes using soya/TVP, tofu,
tempeh, seitan, whey, vegan protein powder, dairy foods, or legumes whenever the
dish meets the nutrition and provenance requirements.

#### Scenario: Qualifying dish uses whey

- **WHEN** a non-drink egg-free vegetarian recipe uses whey protein and clears
  both nutrition gates with published serving macros
- **THEN** whey does not disqualify the recipe

#### Scenario: Qualifying dish uses soy or tempeh

- **WHEN** a non-drink egg-free vegetarian recipe uses soya, TVP, tofu, or
  tempeh and clears both nutrition gates with published serving macros
- **THEN** that concentrated protein source does not disqualify the recipe
