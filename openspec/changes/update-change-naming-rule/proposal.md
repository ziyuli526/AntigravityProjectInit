## Why

Currently, changes do not have a numbering convention, making it difficult to order or track them chronologically. Introducing a numeric `01-` prefix provides a chronological and consistent naming schema, solving this issue of project organization.

## What Changes

- All newly created changes will require a 2-digit numeric prefix followed by a hyphenated string (e.g., `01-change-name`).
- Numbering will dynamically increment. If none exist, it starts at `01-`.
- Validations, documentation, and examples will all be updated to mandate this format.
- **BREAKING**: Change creation commands will reject names lacking the correct numeric prefix or generate the prefix automatically if only a name is provided.

## Capabilities

### New Capabilities
- `change-naming-rule`: The specification that dictates change naming formats, sequence generation, and validation.

### Modified Capabilities


## Impact

- `openspec new change` command logic will need modification to auto-generate the prefix.
- All docs mentioning change naming will need updates.
- Internal validation rules where OpenSpec validates names will require regex updates (e.g., `^\d{2}-[a-z0-9-]+$`).
