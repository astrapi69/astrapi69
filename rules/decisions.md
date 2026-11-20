<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Decisions

Read on demand; the rules every session needs are in core/.

- Before a larger architectural change, check the work planned in the area; on a conflict between an instruction and the documented planning stop and ask, and never build a parallel system slated for removal. (AG-107)
- Take a decision that an issue reserves for the maintainer in that issue, in writing, before the code that depends on it; if a commit already took it, make it again visibly in the issue. Before a pull request that implements a decision recorded in an issue is merged, its reviewer checks it against the decision's wording point by point and names every deviation in the merge report; a deviation the author only mentions in the pull request text goes to the maintainer before the merge. Before code, a rule, a security text or any other public text is merged, an agent or a model other than its author reviews it adversarially: it gets the question and the raw data, not the author's conclusion (AG-005), and looks on purpose for counterexamples, unproven assumptions and contradictions; what it finds is a lead and counts only once a test, a measurement or a primary source bears it out. A text only the maintainer reads is exempt (AG-099). (AG-108)
- Leave an issue in the milestone the maintainer put it in. (AG-109)
