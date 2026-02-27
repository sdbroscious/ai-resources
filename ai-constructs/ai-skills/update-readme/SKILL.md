---
name: update-readme
description: Keep the `README.md` file synchronized with the current repository structure and contents.
---

# README Update Skill

Keep `README.md` synchronized with the current repository structure and contents.

## Instructions

When this skill is invoked, follow this workflow:

1. Ask clarifying questions if scope is unclear (for example: full README refresh vs section-only update).
2. Inspect the repository structure and identify additions, deletions, renames, and major content changes since the last README update.
3. Update `README.md` so links, section names, and descriptions accurately match the repository's current files and directories.
4. Preserve existing style and organization unless the user asks for restructuring.
5. Verify every referenced path in `README.md` exists and descriptions are accurate and concise.
6. Call out notable gaps or ambiguities you cannot resolve from repository state alone.
7. When it makes sense, create or update architecture diagrams for the repo contents. Store these in docs/architecture.

## Output Requirements

After applying this skill:

1. `README.md` reflects the current repository state.
2. Broken or stale links and descriptions are removed or corrected.
3. New relevant files/directories are represented in the appropriate README sections.
