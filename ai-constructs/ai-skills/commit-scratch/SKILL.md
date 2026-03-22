---
name: commit-scratch
description: >
  Commits and pushes any uncommitted changes in ~/workspace/scratch to the current
  git branch. Use this skill whenever the user says anything like "commit my changes",
  "push my work", "save to git", "sync my scratch folder", "scratch-commit", or "run git
  in scratch". Also trigger when the user says "check for changes and push" or asks
  whether anything needs committing. If the user is asking about git operations on
  ~/workspace/scratch at all, this skill is almost certainly what they need — use it.
  This skill works from any directory — it always targets ~/workspace/scratch regardless
  of the current working directory.
---

# Scratch Commit

Commit and push any uncommitted changes in `~/workspace/scratch` to its current remote branch. This skill always targets `~/workspace/scratch` regardless of your current working directory — all git commands use the `-C ~/workspace/scratch` flag.

## Steps

1. **Check for changes** — run `git -C ~/workspace/scratch status --porcelain`. If the output is empty, tell the user there is nothing to commit and stop.

2. **Understand the diff** — run `git -C ~/workspace/scratch diff HEAD` (and also `git -C ~/workspace/scratch diff --cached` if any files are already staged). Read this output carefully — you need it to write a good commit message.

3. **Write a commit message** — compose a concise, imperative-mood summary (≤72 characters) that describes *what changed and why*, e.g. `"update config: add staging environment variables"` or `"fix typo in README and remove stale TODO comments"`. If the diff touches many unrelated files, pick the most significant change for the summary line and mention the others in a short body paragraph.

4. **Stage everything** — run `git -C ~/workspace/scratch add -A`.

5. **Commit** — run `git -C ~/workspace/scratch commit -m "<your message>"`.

6. **Push** — run `git -C ~/workspace/scratch push`. If the push fails because the upstream is not set, run `git -C ~/workspace/scratch push --set-upstream origin <current-branch>` (get the branch name first with `git -C ~/workspace/scratch branch --show-current`).

7. **Notify** — after a successful commit and push, report to the user:
   - Number of files changed
   - Commit hash (short form via `git -C ~/workspace/scratch rev-parse --short HEAD`)
   - The commit message used
   - The branch that was pushed to
   - The remote URL (via `git -C ~/workspace/scratch remote get-url origin`) so the user can verify

Do **not** ask for confirmation before committing or pushing. Just do it and report the result.

## Error handling

- If `~/workspace/scratch` does not exist or is not a git repository, tell the user and suggest they initialize one with `git init` and add a remote.
- If the push is rejected (non-fast-forward), do **not** force-push. Tell the user the push was rejected and ask whether they want you to pull and merge first.
- If there are merge conflicts or a dirty state that prevents committing cleanly, describe the problem clearly and ask the user what they would like to do.
- If the remote is unreachable (network error, auth failure), report the error clearly. The commit will still be local — let the user know they can push manually later.
