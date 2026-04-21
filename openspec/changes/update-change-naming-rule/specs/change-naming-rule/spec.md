## ADDED Requirements

### Requirement: Naming format validation
The system SHALL require all new changes to start with a numeric prefix (`01-`, `02-`, etc.).

#### Scenario: Valid change name
- **WHEN** user provides `01-add-auth`
- **THEN** system successfully creates the change

#### Scenario: Invalid change name
- **WHEN** user provides `add-auth` missing numeric prefix
- **THEN** system throws an error or automatically prepends the next available prefix

### Requirement: Auto increment format
The system SHALL auto-generate the numeric prefix if the user supplies a valid name missing the prefix.

#### Scenario: First change creation
- **WHEN** no prior changes exist and user provides `init-project`
- **THEN** system creates change `01-init-project`

#### Scenario: Subsequent change creation
- **WHEN** change `02-auth` exists, and user provides `tests`
- **THEN** system creates change `03-tests`
