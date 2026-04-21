## Context
We have an initialized Git repository with an existing `README.md` and some OpenSpec tools. The goal is to merge `https://github.com/ziyuli526/AIOT_ProjectProposal.git` into this directory.

## Goals / Non-Goals
**Goals:**
- Completely fetch and merge the old repository into `main` without destroying current work.

**Non-Goals:**
- Do not refactor the code inside the newly integrated files; just get them into the repo safely.

## Decisions
- Add the old GitHub repo as a secondary remote (e.g., `git remote add old-repo URL`), fetch it, and merge its primary branch using `--allow-unrelated-histories`, because this local repository was just initialized from scratch independently.

## Risks / Trade-offs
- Merge conflicts (especially on `README.md`) are possible. Mitigation: Resolve conflicts carefully by combining both readme files if needed, then commit the resolution.
