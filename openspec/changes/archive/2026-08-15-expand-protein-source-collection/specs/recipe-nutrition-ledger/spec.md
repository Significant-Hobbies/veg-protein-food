## ADDED Requirements

### Requirement: Protein-source visibility and filtering

The ledger SHALL identify each recipe's normalized protein-source strategies,
show the primary strategy in the recipe identity, and provide a dataset-backed
filter that matches any strategy assigned to the recipe.

#### Scenario: User filters by whey or protein powder

- **WHEN** the user selects the whey/powder protein-source option
- **THEN** the ledger contains only recipes whose protein strategy includes
  whey or dairy protein powder

#### Scenario: User filters by soy or tempeh

- **WHEN** the user selects soy/TVP/tofu or tempeh
- **THEN** the ledger contains only recipes carrying the selected normalized
  strategy

#### Scenario: User combines protein source with other filters

- **WHEN** the user selects a protein source together with format, India fit,
  diet, search, or ingredient exclusions
- **THEN** all selected constraints apply to the remaining recipes
