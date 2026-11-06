<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Decisions and the maintainer

- Put every decision to the maintainer as numbered options with a recommendation, its reason and the best practice behind it with a source; never a bare 'A or B'. (AG-098)
- Hold no approval rounds over wording only the maintainer reads (release notes, PR prose); ask about behaviour, API and releases, and keep reports short. (AG-099)
- Propose a new check, gate, label rule or required workflow only for a failure that already happened (name its issue); build it only on the maintainer's word. (AG-100)
- Decide reversible steps yourself; collect the maintainer's real decisions (direction, irreversible steps, contract changes) and put them to him once per round. (AG-101)
- Put a fix that would change a documented contract to the maintainer as a decision; other findings need no OK. (AG-102)
- Add a dependency, an MCP server included, only after asking and checking its maintenance and security; prefer existing ones, and scrutinize crypto ones extra. (AG-103)
- Ask before changing an architectural decision such as a file format, the plugin mechanism or the persistence layer. (AG-104)
- Work in this order: open PRs (self-merged only with a grant), bugs, infrastructure (CI, security, gates), UI fixes, cleanup, features, release. (AG-105)
- Before posting anything to a repository the maintainer does not own, show him the final text and wait for an explicit yes for that very posting. (AG-106)
