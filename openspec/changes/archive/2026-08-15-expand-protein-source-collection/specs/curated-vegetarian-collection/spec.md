## MODIFIED Requirements

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

## ADDED Requirements

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
