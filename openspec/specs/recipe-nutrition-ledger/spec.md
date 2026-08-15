# recipe-nutrition-ledger Specification

## Purpose
Provide an accessible, responsive ledger for comparing source-linked recipes,
ingredients, published serving macros, and practical cooking notes.
## Requirements
### Requirement: Accessible responsive operation
The ledger SHALL remain usable by keyboard and SHALL reflow without horizontal
page scrolling at phone, tablet, and desktop widths.

#### Scenario: Keyboard navigation
- **WHEN** a keyboard-only user moves through search, filters, sorting, details toggles, and source links
- **THEN** every control is reachable, visibly focused, and operable

#### Scenario: Narrow viewport
- **WHEN** the product is viewed at 390 CSS pixels wide
- **THEN** controls and recipe metrics reflow into a readable single-column presentation without clipped content

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
