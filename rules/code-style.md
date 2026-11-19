<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Code style

Read on demand; the rules every session needs are in core/.

- Name the thing: no generic names (data, info, result, temp, item, obj, val, tmp, x) except loop indices and short lambdas, no I-prefix on interfaces, and name a reusable part after what it does, not after its first caller (MatchingTile, not LessonMatchingTile). (DC-030)
- Give each function one responsibility, about 40 lines (over 50 means refactor) and one abstraction level; step comments inside it mean each step becomes its own function; split a god class or file instead of whitelisting it, and whitelist only a single-concern file such as a model, a schema or static data. (DC-032)
- Crash early: validate input at the top with guard clauses instead of deep nesting. (DC-033)
- Pass data shared between functions in a small typed structure (record, class, dataclass), not in loose maps or dicts. (DC-034)
- Treat hard to test as a design verdict: a function that needs a pile of mocks is cut wrong and is split, and each extracted helper takes plain parameters and is testable alone. (DC-035)
- Extract logic or a constant instead of copying it to a second place; refactor three copies in the repository you work on, with their tests. (DC-036)
- Handle an error at the layer that can act on it and never swallow one: lower layers throw meaningful exceptions and pass up what they cannot handle (logged, rethrown with context or left to propagate), the UI shows the user an actionable message, and a broad catch stands only where no specific type exists, with the reason in the code. (DC-040)
- Make error messages carry the reason and the offending value, never a secret, precise enough for an issue without follow-up questions; never write a generic one such as "Export failed". (DC-041)
- Never print for feedback: the user gets it through the UI, and diagnostics go to the logger with context as structured fields, not objects formatted into the message; log developer detail at DEBUG, important actions at INFO, the unexpected but harmless at WARNING and what affects the user at ERROR (HTTP 4xx as WARNING, 5xx as ERROR with trace). (DC-042)
- Prefer self-explanatory names and put explanations into the doc comment (Javadoc, docstring, TSDoc); write an inline comment only as a short WHY for a genuinely non-obvious spot with no doc-comment home, never one that says what the code does, reads like a commit message or marks authorship (added by AI), and leave no commented-out code (git keeps the history); in code or a document, give a TODO or FIXME an issue reference (TODO(#NN)); a question parked in a document is written TODO(clarify): <question> only within the session, and before the merge each one is answered or turned into an issue (TODO(#NN)). (DC-046)
- Add no setting the code never reads: check that the code reads a new setting, and remove a feature's settings together with the feature. (DC-047)
- Put no user-visible string literal into UI code: every label, tooltip, title and error message goes through the i18n lookup, with a literal default where the lookup takes one. (DC-048)
- Treat CLI exit codes as a contract: document them and keep error exits distinguishable from domain results. (DC-050)
- Before deleting a conversion, a cast or a null check, find out what it currently prevents, and turn a rule that holds only by accident into a guard clause that states it. (DC-051)
- Keep importing or loading a module free of side effects. (DC-052)
- Let an application's diagnostic and convenience checks fail open (warn and proceed, never kill the app), make a fail-open fallback warn and be testable so a miss cannot pass silently, and where a version derivation can fail at runtime fall back to a sentinel such as 0.0.0+unknown with a warning log, never silently to a hardcoded number. (DC-054)
- Keep production data out of the project tree: resolve every data path through a helper at use time, never relative to the working directory or frozen at import. (DC-055)
- In a lifecycle operation (add, remove, delete, re-add), list every place it leaves residue (database, files, caches, browser storage) and clean each or document why it stays. (DC-056)
- Change a dependency's code only in its own repository and release cycle, never from inside the consumer. (DC-057)
- Write pragmatic, maintainable code for what is needed now (no over-engineering, no premature optimization, no code for later); make code you write yourself library-grade (no app imports, own types, a doc comment with a usage example, own tests, no incidental coupling, one concern) in the smallest scope that works, and say in the commit message and the PR why nothing existing fits. (DC-059)
