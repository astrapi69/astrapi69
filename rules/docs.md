<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Documentation

Read on demand; the rules every session needs are in core/.

- Record in each chat journal entry, per relevant step, the maintainer's prompt verbatim, the optimized prompt, goal, result and commit, plus decisions with reasons and problems with solutions; no small talk. (DC-006)
- In Markdown use one # title, ## sections and ### subsections without skipping a level, - for bullets, backticks for paths, commands and identifiers, #NNN for issues, bold only for a key term. (DC-008)
- Keep CLAUDE.md under 8000 characters and current: purpose, stack keywords, short architecture, build targets and rule pointers, updated when one changes; no file trees, version tables or history. (DC-009)
- Keep each volatile number (test, coverage, mutation, plugin or language counts) in one canonical place; other documents carry a pointer to it, or change in the same commit. (DC-010)
- Word a claim in a public text so that it holds in every CI state: name the enforced floor, never a measured value such as 100%. (DC-011)
- Take every value and name a document states (number, default, threshold, flag, path, target, class, option) from the code or config defining it and check it exists; flag what you cannot find. (DC-012)
- Describe current behaviour in end-user help in the present tense, leave what shipped when to the changelog, and when touching such a line check its claim and drop stale counts. (DC-013)
- Treat docs as specification: describe in the help only features the code has (audit after a large docs addition), and mark one not built yet as planned for a future version. (DC-014)
- Give a new help page its navigation entry in the same or a paired commit, and decide where a help change shows up by reading the code that loads it. (DC-015)
- Date a changed privacy policy with the day of the change; a changed body under an unchanged date is a false statement. (DC-016)
- Give no hard time bound in user-facing text for an operation whose cost grows with input size; leave the estimate out or frame it as a dependency (larger archives take longer). (DC-017)
- Keep documents describing a state, not an intention: update one in the change that alters its state (reference, roadmap, concept, decision record), and search the records for an issue before closing it. (DC-018)
- Keep only open items in planning files, each defined once and pointed to elsewhere; archive a task done with its tests and docs in its closing commit, never delete it, never reuse or edit its ID. (DC-019)
- Add a lesson to the lessons-learned file when a bug came from a wrong pattern, a workaround for a library limit was found, a workflow gap surfaced or a release brought something noteworthy. (DC-020)
- Treat the rule corpus as a cost, since every rule file is injected into every prompt: a new or grown section trades space (condense or delete first) or the commit message says what it bought. (DC-021)
- Hold a PR framed as cleanup, reflow or condensation to the standard of a content change: nothing deleted silently, no rule weakened, every normative change declared in the PR body or commit message. (DC-022)
- Give a document written before the English rule a Language: line saying so instead of translating it for its own sake. (DC-023)
- Give each repository agents have worked on since 2026 a README section "How this project is made" that links to the one project-wide AI_USAGE.md in the profile repository. (DC-024)
- Leave the GitHub About sections (description, website, topics) of the family's repositories as they are until the maintainer asks to unify them in one go. (DC-025)
