<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Writing

- Write GitHub text, code, comments, commits, CHANGELOG, rules and docs in English, whatever the request's language; translations and verbatim quotes excepted. (DC-001)
- Use no em-dash (U+2014 or --) and no emoji in code, comments, docs, UI strings, commits, PRs or issues unless the maintainer asks; use a hyphen or comma. (DC-002)
- Write real characters (ä, ö, ü, ß, never ae, oe, ue, ss) in all text, comments and commits too; only identifiers, file, directory and branch names stay ASCII. (DC-003)
- Measure each number or claim you report in the same session and cite its command; memory, grep or a quoted number is a lead, and an unmeasured claim says so. (DC-004)
- Write no chat journal into a public repository, not even as fallback: it lives only in the maintainer's private repository, or the entry fails with a message. (DC-005)
- Never edit a CHANGELOG yourself: collect grouped bullets written for humans, not raw commit messages, privately for the release PR, which takes them over. In the squash pilot repository (NW-026) the bullet comes instead as a changelog.d/ fragment in the same pull request, and the release pull request assembles the fragments. (DC-007)
- Leave the code you touch cleaner than you found it: fix bugs, sharpen weak tests, correct wrong docs, remove dead code, each with a test, in the same or its own PR. (DC-037)
- Write no journal entry per session: the board and the pull requests are the record; a journal entry only at a milestone, privately in the maintainer's notes repository. (DZ-003)
