<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Tooling

Read on demand; the rules every session needs are in core/.

- Keep a long-running command from moving a checkout someone works in: take the checkout out of the command instead of relying on nobody working meanwhile. (DC-061)
- Add a new dependency only after asking, when the language, the family and the existing dependencies do not fit, and only if it is maintained, free of known CVEs, small and in Java JPMS-capable. (DC-062)
- Use only stable dependency versions in production code (no alpha, beta, RC or milestone), take latest stable as at least two weeks old, and prefer Active LTS over Current. (DC-063)
- When an upstream pin blocks a dependency bump, defer that bump and name the blocker in the commit that updates what it can. (DC-064)
- For a bulk dependency bump, try one instance first, prefer an allowlisted update over a bare one, and check the lock diff for packages held back as risky before committing. (DC-065)
- Validate a build-tool major bump with a full build, never with the tests alone. (DC-066)
- Make a gate fail closed and report what it measured: one that cannot check fails or skips with a reason, and its output names what ran and the size of the scanned set. (DC-067)
- Turn a check, hook or workflow off or narrow its run only visibly, with a reason in the diff or a named opt-in; a check that only warns enforces nothing. (DC-068)
- Wired is not working: run a new workflow, scheduled job, hook or check end to end once in the session that wires it and record the result; a check no step runs is a silent gate. (DC-069)
- Name in each rule-enforcing CI gate the rule section it enforces, and when retiring the gate or the rule remove both halves in the same PR. (DC-070)
- Never let a gate on a drifting oracle move its baseline by itself: bank each fall of a counter that should be zero, and move a budget with legitimate growth only by a deliberate act. (DC-071)
- Before reading or raising a ratchet baseline on a branch, merge the base branch in first and measure on the merged tree. (DC-072)
- Run on pull requests only the correctness gates whose failure must block a merge; informational, warn-only or externally driven checks run on a schedule. (DC-073)
- Treat dead-code findings and "0 consumers" as claims: verify each before deleting, with a search covering every consumer, third-party code that renders yours included. (DC-074)
- Give a generated path exactly one writer, since two are a defect even with identical bytes; before tightening a comparison on it, find every writer by running each generator alone. (DC-075)
- Keep the --check mode of a sync or verify script idempotent: the same answer twice in a row, never a write, no dependence on state outside the repository. (DC-076)
- Update the committed example of a gitignored config in the commit that adds or removes a load-bearing entry, and diff the real file against it first when a failure happens only in CI. (DC-077)
- Debug a CI failure by reading the failing job's log first, before building any hypothesis. (DC-078)
- Before planning a local fix for a CI warning, confirm by searching the code that it has a local source; GitHub-managed services are not the repository's to fix. (DC-079)
- Check pinned CI actions each quarter or after a platform deprecation: read the runtime from action.yml, pin the lowest new major that meets the target, one commit per action class. (DC-080)
- Treat Claude Code's rule loading (every rule file injected whatever its frontmatter) as behaviour seen on a date: recheck it on a major version or a visible change and update the date. (DC-081)
- Derive a repository's root from the working directory (git rev-parse --show-toplevel), never from the script's own location. (DC-082)
- Make a check the maintainer decided to build exit non-zero on the failure it guards, and prefer a precise diff of the guarded artifact over a coarse presence check. (OC-008)
