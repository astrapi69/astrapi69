<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Git, pull requests and issues

Read on demand; the rules every session needs are in core/.

- Pass every commit through the repository's hooks; when a hook rewrote files, re-stage them, check `git diff --cached` and commit again. (AG-086)
- Before a local merge, confirm you are on the target branch: a checkout fails when another worktree holds that branch, and the merge then reports 'Already up to date'. (AG-087)
- In a PR for one sub-issue write `Closes #<sub-issue>` first and `Refs #<umbrella>` after it; close the umbrella once its last sub-issue is closed or the rest is deferred, saying so. (AG-088)
- When the repository has a PR template, mirror its section headings in the PR body. (AG-089)
- Self-merge only after GitGuardian reported success on the PR's current head; if its run stays queued, push one empty commit to trigger it and wait for that success. (AG-090)
- Under strict branch protection, merge develop into the PR branch first and wait for a fresh green round before you merge. (AG-091)
- Let the tooling wait for the checks: `gh pr merge <n> --auto --merge` in the libraries, the project's own merge target where it has one (mystic-crypt-ui: `make merge-pr PR=<n>`). (AG-092)
- Read a green PR as 'the PR checks are green', not 'develop is green': checks that run only nightly still have to pass. (AG-093)
- For a breaking dependency upgrade, bump the version first behind backward-compatible re-exports and migrate the call sites after, so every commit stays green. (AG-094)
- Give an item that waits for a named condition the label `blocked` and the condition in writing, not a P stage; blocked is not P0 even when critical. (AG-095)
- When an issue needs a label the repository lacks, copy it in name, colour and description from a family repository that has it, read it back, then apply it; never improvise or overwrite one. (AG-096)
- Classify a finding's environment (development or production setup) before you assign its urgency. (AG-097)
