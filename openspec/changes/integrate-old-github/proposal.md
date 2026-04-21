## Why
We need to integrate the old project codebase into the current repository to unify the work. Pulling the GitHub contents from `https://github.com/ziyuli526/AIOT_ProjectProposal.git` will bring all previous AIOT project proposals and implementations into our main tracking space.

## What Changes
- Pull/Merge `https://github.com/ziyuli526/AIOT_ProjectProposal.git` into the current local repository.
- Ensure all historical files from the old repo are represented and committed to the current active git branch (`main`).

## Capabilities

### New Capabilities
- `integrate-old-github`: The capability to ingest old AIOT project files into the current workspace.

### Modified Capabilities


## Impact
- The workspace will contain many new files. Potential merge conflicts if the old repo has a `README.md` that conflicts with the current local one. This logic will require `git merge --allow-unrelated-histories`.
