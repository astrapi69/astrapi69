<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Decisions and the maintainer

- Put every decision to the maintainer as numbered options with a recommendation, its reason and the best practice behind it with a source; never a bare 'A or B'. The source is a primary one: the official documentation, the release notes of the version in use, a specification, an RFC, a legal text or the source code; a blog post or another AI's answer is a lead, not a source. (AG-098)
- Hold no approval rounds over wording only the maintainer reads (release notes, PR prose), and run no LLM check loop over a text only he reads (reports, PR texts without outside effect, notes); ask about behaviour, API and releases, and keep reports short. (AG-099)
- Propose a new check, gate, label rule or required workflow only for a failure that already happened (name its issue); build it only on the maintainer's word. Add a new rule only after a documented failure and only when it replaces an existing rule or is merged with one. (AG-100)
- Decide reversible steps yourself; collect the maintainer's real decisions (direction, irreversible steps, contract changes) and put them to him once per round. (AG-101)
- Add a dependency, an MCP server included, only after asking and checking its maintenance and security; prefer existing ones, and scrutinize crypto ones extra. Before you use a package, a GitHub Action, an API or a method for the first time, check in its registry or its official documentation that it exists in the version you name, and cite where; before you rely on how it behaves, read the release notes of the version in use. (AG-103)
- Ask before changing an architectural decision such as a file format, the plugin mechanism or the persistence layer. (AG-104)
- Work in this order: open PRs (self-merged only with a grant), bugs (on 'weiter' or 'work through the bugs' work the open bug issues as the queue in P order, smallest scope first within a tier, without waiting in between), infrastructure (CI, security, gates), UI fixes, cleanup, features, release. (AG-105)
- Before posting anything to a repository the maintainer does not own, show him the final text and wait for an explicit yes for that very posting. (AG-106)
