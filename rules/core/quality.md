<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Tests, quality and dependencies

- Test first for every change of behaviour or logic: a failing test before any production code, then only the code that passes it, then refactor with tests green. (RL-001)
- Fix in two commits: first a test that pins today's behaviour and is green, then the fix that turns its assertions; every commit stays green, bisect works, the change shows in the fix's diff. (RL-002)
- Never delete, comment out, weaken or disable an existing test to make the build green. (RL-003)
- Keep the project's everyday gate green after every change; no exception to test-first lifts this. (RL-004)
- Never run mutation testing locally, not as an agent, subagent or workflow stage; it runs in the repository's CI workflow, and its numbers come from that run. (RL-005)
- Take cryptographic primitives only from the JDK or Bouncy Castle; otherwise depend first on the JDK, the language and the project's framework, then the family, then third-party libraries. (RL-098)
- Before writing a class, helper, constant or enum, grep the family's local checkouts and use what exists; a rewrite states why in the commit message and the PR. (RL-099)
