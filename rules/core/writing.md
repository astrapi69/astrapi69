<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Writing

- Write GitHub text, code, comments, commits, CHANGELOG, rules and docs in English, whatever the request's language; translations and verbatim quotes excepted. (DC-001)
- Use no em-dash (U+2014 or --) and no emoji in code, comments, docs, UI strings, commits, PRs or issues unless the maintainer asks; use a hyphen or comma. (DC-002)
- Write real characters (ä, ö, ü, ß, never ae, oe, ue, ss) in all text, the chat, comments and commits included; only identifiers, file, directory and branch names stay ASCII. (DC-003)
- Treat every number or claim you report, a config, a doc or a claim about another repo included, as unproven until you have measured it in the same session, and cite the command; memory, grep or a quoted number is a lead, and an unmeasured claim says so; mark inferences and plainly correct an earlier wrong statement. (DC-004)
- Never edit a CHANGELOG yourself: collect grouped bullets written for humans, not raw commit messages, privately for the release PR, which takes them over. In the squash pilot repository (NW-026) the bullet comes instead as a changelog.d/ fragment in the same pull request, and the release pull request assembles the fragments. One exception: once a security advisory is published, a docs pull request adds only its id to the CHANGELOG entry of the release that fixed it and changes nothing else; until then AG-117 keeps the id out. (DC-007)
- Write no journal entry per session: the board and the pull requests are the record; a journal entry only at a milestone, only in the maintainer's private notes repository, never in a public repository, not even as fallback (the entry fails with a message instead). (DZ-003)
