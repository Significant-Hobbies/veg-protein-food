# standalone-product-boundary Specification

## Purpose
Keep the recipe dashboard independently runnable, understandable, and testable
without Fleet application code, navigation, services, or visual identity.
## Requirements
### Requirement: Independent local product
The product SHALL run from the standalone repository root and MUST NOT import,
embed, or route through Fleet application code, navigation, or runtime services.

#### Scenario: Local start
- **WHEN** a user runs the documented development command from the standalone repository
- **THEN** the recipe product is available at its documented localhost URL with no Fleet application running

#### Scenario: Product navigation is inspected
- **WHEN** the page header and primary controls render
- **THEN** they contain only recipe-product identity and actions, with no Fleet, domains, Google Search, or AI Awareness navigation

### Requirement: Self-contained checked-in snapshot
The product SHALL include the recipe and nutrition-reference data needed for its
core experience inside the repository and SHALL NOT require credentials or a
network request to load the ledger.

#### Scenario: Runtime is offline
- **WHEN** the local product starts without internet access
- **THEN** the complete checked-in recipe ledger remains searchable, filterable, sortable, and inspectable

#### Scenario: User opens an external source
- **WHEN** the user explicitly activates a YouTube watch link
- **THEN** the product may navigate to that external source while all other core interactions remain local

### Requirement: Dependency-minimal operation
The product SHALL use Astro as its only direct production package and SHALL use
repository-owned files for application logic, data, tests, and checks.

#### Scenario: Fresh checkout is inspected
- **WHEN** the repository manifest is read
- **THEN** it declares Astro as the only direct production dependency and no development package dependencies

### Requirement: Verifiable product boundary
The repository SHALL provide automated checks for snapshot integrity, nutrition
filtering behavior, source-link validity, and prohibited Fleet coupling.

#### Scenario: Checks pass
- **WHEN** the documented check command runs against an intact repository
- **THEN** it verifies the expected recipe counts and reports no Fleet runtime or navigation references in product files

#### Scenario: Snapshot is incomplete
- **WHEN** a required record, source URL, or expected inventory count is missing
- **THEN** the check command fails with a diagnostic message
