## REMOVED Requirements

### Requirement: Creator-page attribution

**Reason**: The homepage is now a multi-publisher collection rather than a
single creator page.

**Migration**: Publisher credit and direct source links move to every recipe
row and details panel under the curated collection provenance requirement.

### Requirement: Ingredient-bearing long-form inventory

**Reason**: Exhaustively displaying a channel's long-form inventory conflicts
with the new quality-gated collection.

**Migration**: Only recipes that satisfy the curated collection admission gate
appear on the homepage.

### Requirement: Honest nutrition hierarchy

**Reason**: The collection no longer mixes creator claims with ingredient-based
USDA estimates.

**Migration**: Use source-published protein and calories for the same serving,
with the serving basis and publisher caveat displayed in details.

### Requirement: Coverage-gated nutrition density

**Reason**: Parser line coverage and fiber estimation do not apply to the
source-published macro collection.

**Migration**: Derive protein density only from the publisher's same-serving
protein and calorie values.

### Requirement: Search, filters, and sorting

**Reason**: Evidence coverage and protein-source filters have been replaced by
format and India-fit controls.

**Migration**: Search, multi-exclusions, dietary filtering, and sortable
nutrition remain; use the curated collection's practical filter requirements
for the new controls.

### Requirement: Recipe evidence and source access

**Reason**: Sources now include recipe blogs as well as YouTube, and evidence
is publisher-serving provenance rather than parser coverage.

**Migration**: Use each row's direct original source link and expandable key
ingredients, serving macros, caveat, and India-fit note.

## MODIFIED Requirements

### Requirement: Accessible responsive operation
The ledger SHALL remain usable by keyboard and SHALL reflow without horizontal
page scrolling at phone, tablet, and desktop widths.

#### Scenario: Keyboard navigation
- **WHEN** a keyboard-only user moves through search, filters, sorting, details toggles, and source links
- **THEN** every control is reachable, visibly focused, and operable

#### Scenario: Narrow viewport
- **WHEN** the product is viewed at 390 CSS pixels wide
- **THEN** controls and recipe metrics reflow into a readable single-column presentation without clipped content
