## Purpose

Provide an honest, searchable ledger for comparing the ingredients, nutrition
estimates, evidence coverage, and final results of long-form recipe videos.

## ADDED Requirements

### Requirement: Creator-page attribution
The product SHALL use a reusable product identity while each creator page MUST
credit its creator by name and handle with a direct source-channel link near the
top of the page.

#### Scenario: Creator page loads
- **WHEN** the Epic Mint Leaves recipe page renders
- **THEN** the page title and top credit identify Epic Mint Leaves and provide a direct link to the creator's Videos tab

### Requirement: Ingredient-bearing long-form inventory
The product SHALL display every long-form source video that has an extracted
ingredient list and SHALL exclude Shorts and videos without usable ingredients.

#### Scenario: Inventory loads
- **WHEN** the checked-in source snapshot is loaded
- **THEN** the product displays the 264 ingredient-bearing long-form recipes and reconciles them against the 278-video source inventory

#### Scenario: Recipe lacks ingredients
- **WHEN** a source record has no extracted ingredients
- **THEN** the record is excluded from the comparison ledger without changing the source-inventory count

### Requirement: Honest nutrition hierarchy
The product SHALL prefer creator-stated protein when present, SHALL otherwise
show a conservative ingredient-based protein estimate, and MUST label the
source of every displayed protein value.

#### Scenario: Creator protein is available
- **WHEN** a recipe includes a creator-stated protein result
- **THEN** that protein value is displayed and labelled as creator-stated

#### Scenario: Protein is estimated from ingredients
- **WHEN** creator-stated protein is absent and sufficient ingredients are matched
- **THEN** the ingredient-based protein value is displayed and labelled as estimated

#### Scenario: Protein cannot be supported
- **WHEN** neither a creator value nor a supportable estimate is available
- **THEN** protein is displayed as unavailable rather than fabricated

### Requirement: Coverage-gated nutrition density
The product SHALL display creator-stated or ingredient-estimated calories and
SHALL display protein per 100 kcal only when protein and calories cover the same
complete recipe. Fiber density SHALL require complete ingredient coverage.

#### Scenario: Coverage is sufficient
- **WHEN** a recipe has complete same-recipe protein and calorie evidence
- **THEN** the product displays calories, protein per 100 kcal, and fiber per 100 kcal with source labelling

#### Scenario: Coverage is insufficient
- **WHEN** a recipe has incomplete material ingredient coverage and lacks creator totals
- **THEN** density ratios are suppressed and the coverage shortfall remains visible

### Requirement: Search, filters, and sorting
The product SHALL provide recipe/ingredient search and a dataset-backed dropdown
for excluding one or more ingredient families. It SHALL also filter by dietary
tag, evidence coverage, and protein source, and sort through both the sort
select and sortable ledger headings.

#### Scenario: User searches recipes or ingredients
- **WHEN** the user enters a search term
- **THEN** the ledger contains only recipes whose title or ingredient evidence matches the term

#### Scenario: User selects ingredient exclusions
- **WHEN** the user selects one or more ingredient options from the exclusion dropdown
- **THEN** each selection remains visible and the ledger removes every recipe whose ingredient evidence matches any selected option

#### Scenario: User removes an ingredient exclusion
- **WHEN** the user removes one selected ingredient option
- **THEN** that exclusion no longer affects the ledger while the remaining exclusions stay active

#### Scenario: User sorts from a ledger heading
- **WHEN** the user activates a sortable ledger heading
- **THEN** the ledger uses that metric, toggles direction on repeated activation, and exposes the active direction visually

#### Scenario: User combines controls
- **WHEN** the user applies multiple filters and a sort order
- **THEN** all active filters are combined and the remaining recipes use the selected sort order

#### Scenario: No recipes match
- **WHEN** the active search and filters produce no matches
- **THEN** the product shows an explicit empty state and offers a control reset

### Requirement: Recipe evidence and source access
Each recipe SHALL provide one direct YouTube watch link and expandable evidence
that shows exact extracted ingredients, matched and unmatched coverage,
creator-stated results when present, and nutrition-estimate provenance.

#### Scenario: User opens recipe evidence
- **WHEN** the user expands a recipe
- **THEN** the product shows the recipe ingredients, evidence coverage, source notes, and available creator results

#### Scenario: User follows the source
- **WHEN** the user activates a recipe's watch link
- **THEN** the original YouTube video opens in a new browsing context

### Requirement: Accessible responsive operation
The ledger SHALL remain usable by keyboard and SHALL reflow without horizontal
page scrolling at phone, tablet, and desktop widths.

#### Scenario: Keyboard navigation
- **WHEN** a keyboard-only user moves through search, filters, sorting, evidence toggles, and watch links
- **THEN** every control is reachable, visibly focused, and operable

#### Scenario: Narrow viewport
- **WHEN** the product is viewed at 390 CSS pixels wide
- **THEN** controls and recipe metrics reflow into a readable single-column presentation without clipped content
