<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Working as an agent

- At session start fetch and compare with origin, read the recent history and the rules for the task, and get a green baseline before you change anything. (AG-001)
- Before building on claimed work, your own included, verify the artifact (git status, git log -1, the gate's exit code); after each commit check that HEAD moved. (AG-005)
- Inspect a proposed mass edit (global sed, regex sweep) instead of running it: read each match, apply the changes one by one and diff the result. (AG-007)
- Never guess: answer an unclear point from evidence, else park it under the most cautious assumption and go on; stop and ask only if it blocks or risks damage. (AG-008)
- Name in every final report the issues opened and closed in the session (the goal: at least as many closed as opened), and end it with the parked questions (where, which assumption), the answers found in evidence (source) and how each blocking question was resolved. (AG-009)
- End every report to the maintainer, after the questions AG-009 closes with, with the instructions he gave since the last report: verbatim, dated, each with its state (done, in progress, not started), 'none' when there are none; never quote a secret. (NW-024)
- Answer the question asked before starting a fix; be direct and factual, say when something breaks the architecture rather than work around it, mark suggestions. (AG-010)
- Report results, not launches: after each finished item give its measured result, and let an interim note name only what is already measured. (AG-011)
- Check a brief or dispatch prompt against the repo's rules; surface a conflict before acting, and deviate only when the user overrides the rule in this session. (AG-013)
- When a hook or a permission refuses a command, report it to whoever dispatched you; never work around it and never hand it to the maintainer to run. (AG-014)
- Call a change done only when merged or its PR open, the build green, tests written, touched docs updated and, if user-facing, its CHANGELOG bullet collected. (AG-016)
- Make work survive a crash: commit WIP once green, write each finding to a file at once, start long runs detached, and say at a stop what is uncommitted where. (AG-019)
- Run GUI automation and UI tests only on an Xvfb started for them, with DISPLAY set on each call and its socket checked; take the pid from $!, never pgrep -f. (AG-022)
- Never stop or kill a Gradle daemon, not even an idle one of another session; to keep builds apart, an agent or worktree may use its own GRADLE_USER_HOME. (AG-024)
- As a subagent, report a finding with its reproducing test to the session that dispatched you; that session fixes it, or files the issue under NW-016. (DZ-001)
- Run shell commands as bash -c '...' with the commands written out, chain dependent steps with && (never ;) and never pipe a check through | tail or anything else that hides its exit code; use a script file only when it is committed. A go before each round is adaptive-learner's own rule. (DZ-002)

## The Agenten-Board

- Put every task on the Agenten-Board when you start it: status In Arbeit and the field Agent set (for example "cc silly-collection", "ccw lethenon"); a task without an issue gets a draft item. Before starting on an issue, check its labels and the board for that claim first. (NW-001)
- Set Wartet auf Owner while you wait for the maintainer (the owner), and leave Erledigt to the board's automation, which sets it when the issue is closed or the pull request merged. (NW-002)
- An agent that executes tasks and does not reach the board (a cloud session, whose proxy allows repos/* only, or any session without the board token) uses no board token and reports in the two places cc's local sync reads every 5 minutes: the label status:in-arbeit, status:wartet-auf-owner or status:wartet-auf-rechner on an open issue or PR of a repository on the sync's relevance list, created first with exactly that name where the repository lacks it; and for a task without an issue a row `| repo | description | status |` in the section `## ccw` of the sync's status file, the one file whose rows the sync reads, for every repository. The relevance list and the status file are in the private notes repository, on the branch and paths cc's sync reads; only the prompt for such an agent names them, and it lies beside cc's sync in the private notes. An agent without write access to GitHub ends its answer with one line per task, `Board: repo | issue, PR or description | status`, for the maintainer or cc to carry over. It says what it set, never that an item is on the board it cannot see. Until #32 is done, a transitional rule: the sync sets Agent ccw on everything it carries, so the agent names itself in the description or in the comment that goes with the label; this sentence goes with #32. (NW-023)

## Access

| Who | Can read | Cannot |
|---|---|---|
| cc, a local session | the local checkouts, the public and the private repositories, the private notes, the Agenten-Board | secret values |
| ccw, a cloud session | the public rules and the repositories the Claude GitHub App is installed on | the local machine, the Agenten-Board (NW-023), secret values |
| Claude in the chat | public URLs only | everything else |
| the maintainer | everything, and only he sets secrets | |

- Missing an access: do not guess and do not go on with assumptions; name exactly what is missing, where it lies and what it is needed for, stop at that point and go on with everything else; when the same access gap stops work again, solve the access instead of bridging it once more, and propose to the maintainer how. (NW-004)
- Hand extracts to another agent as an issue comment or a file in that agent's repository when they are not sensitive; sensitive extracts go only through the maintainer, never public. (NW-005)
- Never set a secret's value: only the maintainer does. (NW-006)

## When the maintainer is travelling

- When the maintainer is travelling only ccw works: there is no cc as a bridge and no local terminal.
- A task that needs the local machine (setting secrets, local files, a local build with the gate on the pinned JDK, a repository ccw cannot reach) ccw sets to Wartet auf Rechner with a short description (the label status:wartet-auf-rechner, or that status in its row of the section ccw), and works on; back at the machine, cc takes the items in Wartet auf Rechner first. (NW-010)

## Where rules live

- Write a working rule only into these rule files (public) or the private part, commit and push it; never into an agent's memory, which holds only a project's state of work. (NW-012)

## Findings

- Finding means fixing (the Boy Scout rule): a bug or a small improvement you find in the repository you work on, inside the task or not, fix in the same session, test first, in its own PR, merged when green; propose a change first only when it is in another repository (NW-017) or changes a documented contract (NW-016). (NW-015)
- File an issue or put a decision to the maintainer instead of fixing only when the fix changes a documented contract (a Javadoc or API promise, a persisted format, an architectural decision), depends on something external or is too big for the session; give the reason and the next step. (NW-016)
- Hand a finding in another repository to the session that owns that repository; that session fixes it. (NW-017)
