# Recipe nutrition integrity

## ADDED Requirements

### Requirement: Complete ingredient extraction

The system SHALL preserve every quantity-led ingredient line across multiple
ingredient subsections until an explicit non-ingredient section begins.

#### Scenario: Multi-layer recipe

- **Given** a description separates base, oats, and yogurt with dot lines
- **When** ingredients are extracted
- **Then** ingredients from all three subsections are retained

#### Scenario: Protein-named ingredient

- **Given** an ingredient line contains "high protein flour" or "protein powder"
- **When** ingredients are extracted
- **Then** it remains an ingredient and is not treated as a result claim

### Requirement: Same-evidence density

The system SHALL expose protein per 100 kcal only when the protein and calorie
values cover the same complete recipe.

#### Scenario: Partial USDA estimate

- **Given** creator-stated protein and one or more unmatched material ingredients
- **When** no creator calorie total exists
- **Then** protein density is unavailable

#### Scenario: Creator totals

- **Given** creator-stated protein and creator-stated calories for the complete recipe
- **When** both values are positive
- **Then** density is calculated from those two creator totals

#### Scenario: Complete ingredient estimate

- **Given** every material ingredient is matched with a quantity
- **When** creator calories are absent
- **Then** estimated protein and calories may be used together for density

### Requirement: Auditable provenance

The system SHALL retain the source text and source type for creator totals and
shall distinguish creator calories from ingredient-estimated calories in the UI.

#### Scenario: Evidence inspection

- **Given** a recipe has creator and estimated nutrition evidence
- **When** its evidence sheet is opened
- **Then** each displayed total identifies its source and retains the source text
