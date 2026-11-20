<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Tooling

Read on demand; the rules every session needs are in core/.

- Keep a long-running command from moving a checkout someone works in: take the checkout out of the command instead of relying on nobody working meanwhile. (DC-061)
- Add a new dependency only after asking, when the language, the family and the existing dependencies do not fit, and only if it is maintained, free of known CVEs, small and in Java JPMS-capable. (DC-062)
- Use only stable dependency versions in production code (no alpha, beta, RC or milestone), take latest stable as at least two weeks old, and prefer Active LTS over Current. (DC-063)
- When an upstream pin blocks a dependency bump, defer that bump and name the blocker in the commit that updates what it can; for a bulk bump try one instance first, prefer an allowlisted update over a bare one and check the lock diff for packages held back as risky before committing; validate a build-tool major bump with a full build, never with the tests alone. (DC-064)
- Make a gate fail closed and report what it measured (what ran, the size of the scanned set; one that cannot check fails or skips with a reason), exit non-zero on the failure it guards (also a check the maintainer decided to build), prefer a precise diff of the guarded artifact over a coarse presence check, keep its --check mode idempotent (the same answer twice in a row, never a write, no dependence on state outside the repository), and give every gate five tests: it catches the violation, passes on a clean tree, fails closed without its basis, reports what it measured, and its number means the same everywhere (named tolerance for unavoidable variance). (DC-067)
- Turn a check, hook or workflow off or narrow its run only visibly, with a reason in the diff or a named opt-in (a check that only warns enforces nothing); a CI gate that enforces a rule names the rule section, and retiring the gate or the rule removes both in the same PR. (DC-068)
- Wired is not working: run a new workflow, scheduled job, hook or check end to end once in the session that wires it and record the result; a check no step runs is a silent gate. (DC-069)
- Never let a gate on a drifting oracle move its baseline by itself: bank each fall of a counter that should be zero, move a budget with legitimate growth only by a deliberate act, and read or raise a ratchet baseline on a branch only after merging the base branch in, measured on the merged tree. (DC-071)
- Give a generated path exactly one writer, since two are a defect even with identical bytes; before tightening a comparison on it, find every writer by running each generator alone. (DC-075)
- Update the committed example of a gitignored config in the commit that adds or removes a load-bearing entry, and diff the real file against it first when a failure happens only in CI. (DC-077)
- Debug a CI failure by reading the failing job's log first, before building any hypothesis, and before planning a local fix for a CI warning confirm by searching the code that it has a local source; GitHub-managed services are not the repository's to fix. (DC-078)
- Keep every CI action at its newest release: check them at the start of every cycle with the dependency currency check (RL-120) and after any deprecation warning a run prints, read the runtime from action.yml and the notes of every major step against the inputs the workflows pass, and pin the newest release by its commit with the version as a comment. (DC-080)
- Claude Code injects every rule file into the prompt whatever its frontmatter; this is behaviour seen on a date, so recheck it on a major version or a visible change and update the date.
- Derive a repository's root from the working directory (git rev-parse --show-toplevel), never from the script's own location. (DC-082)
