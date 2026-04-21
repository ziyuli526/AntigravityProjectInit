## Context

OpenSpec currently names changes without a consistent numeric sequence, making chronological ordering difficult. The proposal is to enforce a `01-` numbered prefix on all new changes.

## Goals / Non-Goals

**Goals:**
- Enforce the new numbering logic (`01-`, `02-`) within the change creation command (`openspec new change`).
- Discover existing numeric prefixes within the `changes` directory and increment based on the highest existing number.
- Update validation schemas.

**Non-Goals:**
- Do not retroactively rebuild or rename existing changes that violate this rule.

## Decisions

- **Regex Validation:** Change the strict naming regex to `^\d{2}-[a-z0-9-]+$`.
- **Auto Increment Logic:** If a user specifies just `update-naming`, the system will list directory contents, locate the max two-digit prefix (e.g., `01`, `02`), and increment by +1 (e.g., `03-update-naming`).

## Risks / Trade-offs

- **Tooling Breakage:** Any CI/CD tools creating changes dynamically without prefix awareness will fail. Mitigation: Auto-prefixing if the format `[a-z0-9-]+` is provided but lacks `\d{2}-`.
