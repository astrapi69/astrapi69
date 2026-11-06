<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Tests, quality and dependencies

- Test first for every change of behaviour or logic: a failing test before any production code, then only the code that passes it, then refactor with tests green. (RL-001)
- Start every bug fix with a test that reproduces the bug and is red on the unfixed code; the fix turns it green, and the test stays as a regression guard. (RL-002)
- Never delete, comment out, weaken or disable an existing test to make the build green. (RL-003)
- Keep the project's everyday gate green after every change; no exception to test-first lifts this. (RL-004)
- Never run mutation testing locally, not as an agent, subagent or workflow stage; it runs in the repository's CI workflow, and its numbers come from that run. (RL-005)
- Pick what to depend on in this order in every project: the JDK and the language, then the family's libraries, then third-party libraries. (RL-098)
- Before writing a class, helper, constant or enum, grep the family's local checkouts (do not guess) and use what exists; writing it again needs a stated reason. (RL-099)
