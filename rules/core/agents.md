<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Working as an agent

- At session start fetch and compare with origin, read the recent history and the rules for the task, and get a green baseline before you change anything. (AG-001)
- Before building on claimed work, your own included, verify the artifact (git status, git log -1, the gate's exit code); after each commit check that HEAD moved. (AG-005)
- Treat a config, a doc, a given number or a claim about another repo as unproven until measured; mark inferences and plainly correct an earlier wrong statement. (AG-006)
- Inspect a proposed mass edit (global sed, regex sweep) instead of running it: read each match, apply the changes one by one and diff the result. (AG-007)
- Never guess: answer an unclear point from evidence, else park it under the most cautious assumption and go on; stop and ask only if it blocks or risks damage. (AG-008)
- End the final report with the parked questions (where, which assumption), the answers found in evidence (source) and how each blocking question was resolved. (AG-009)
- Answer the question asked before starting a fix; be direct and factual, say when something breaks the architecture rather than work around it, mark suggestions. (AG-010)
- Report results, not launches: after each finished item give its measured result, and let an interim note name only what is already measured. (AG-011)
- Check a brief or dispatch prompt against the repo's rules; surface a conflict before acting, and deviate only when the user overrides the rule in this session. (AG-013)
- When a hook or a permission refuses a command, report it to whoever dispatched you; never work around it and never hand it to the maintainer to run. (AG-014)
- On 'weiter' or 'work through the bugs', work the open bug issues as the queue in P order, smallest scope first within a tier, without waiting in between. (AG-015)
- Call a change done only when merged or its PR open, the build green, tests written, touched docs updated and, if user-facing, its CHANGELOG bullet collected. (AG-016)
- Make work survive a crash: commit WIP once green, write each finding to a file at once, start long runs detached, and say at a stop what is uncommitted where. (AG-019)
- In German prose, the chat included, write real umlauts (ä, ö, ü), never ae, oe or ue. (AG-020)
- Run GUI automation and UI tests only on an Xvfb started for them, with DISPLAY set on each call and its socket checked; take the pid from $!, never pgrep -f. (AG-022)
- Never stop or kill a Gradle daemon, not even an idle one of another session; to keep builds apart, an agent or worktree may use its own GRADLE_USER_HOME. (AG-024)
- Chain dependent shell steps with && and never with ;, and never pipe a check through | tail or anything else that hides its exit code. (DC-060)
- Park a question in a document as TODO(clarify): <question> only within the session; before the merge answer each one or turn it into an issue (TODO(#NN)). (OC-003)
- As a subagent, report a finding with its reproducing test to the session that dispatched you; that session files the issue without asking. (DZ-001)
- Run shell commands as bash -c '...' with the commands written out; use a script file only when it is committed. A go before each round is adaptive-learner's own rule. (DZ-002)

## The Agenten-Board

- Put every task on the Agenten-Board when you start it: status In Arbeit and the field Agent set (for example "cc silly-collection", "ccw lethenon"); a task without an issue gets a draft item. (NW-001)
- Set Wartet auf Aster while you wait for the maintainer, and leave Erledigt to the board's automation, which sets it when the issue is closed or the pull request merged. (NW-002)
- Keep in STATUS.md only the state and context the board cannot hold; for the state of the work STATUS.md points to the board. (NW-003)

## Access

| Who | Can read | Cannot |
|---|---|---|
| cc, a local session | the local checkouts, the public and the private repositories, the private notes, the Agenten-Board | secret values |
| ccw, a cloud session | the public rules and the repositories the Claude GitHub App is installed on | the local machine, secret values |
| Claude in the chat | public URLs only | everything else |
| the maintainer | everything, and only he sets secrets | |

- Missing an access: do not guess and do not go on with assumptions; name exactly what is missing, where it lies and what it is needed for, stop at that point and go on with everything else. (NW-004)
- Hand extracts to another agent as an issue comment or a file in that agent's repository when they are not sensitive; sensitive extracts go only through the maintainer, never public. (NW-005)
- Never set a secret's value: only the maintainer does. (NW-006)
- When the same access gap stops work again, solve the access instead of bridging it once more, and propose to the maintainer how. (NW-007)

## When the maintainer is travelling

- When the maintainer is travelling only ccw works: there is no cc as a bridge and no local terminal. (NW-008)
- ccw reads directly the public rules, the maintainer's private notes repository (STATUS.md, the collection files) and the Agenten-Board. (NW-009)
- A task that needs the local machine (setting secrets, local files, a local build with the gate on the pinned JDK, a repository ccw cannot reach) ccw sets to Wartet auf Rechner with a short description, and works on. (NW-010)
- Back at the machine, cc takes the items in Wartet auf Rechner first. (NW-011)

## Where rules live

- Write a working rule only into these rule files (public) or the private part, commit and push it; never into an agent's memory, which holds only a project's state of work. (NW-012)
