<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Working as an agent

Read on demand; the rules every session needs are in core/.

- Write files with the Write tool or a quoted heredoc (<<'EOF'), never with a heredoc that expands $VAR, and compile or run them before trusting them. (AG-025)
- In a prompt or brief, reference the existing patterns instead of inventing new ones, and name the file, the class or function and the expected behaviour. (AG-027)
- In an audit, read the authoritative sources (rules, roadmap, backlog) before flagging, cite the rule for each finding, rank on the P0-P5 urgency scale, and change no code unless asked. (AG-028)
- When you replace a broken mechanism, check the assumptions it was built on as well. (AG-029)
- For a bug reported against a running build, first establish which build the user ran; when the code looks right but the user insists, ask for evidence, never dismiss or guess-fix. (AG-030)
- Before a larger change, tabulate the current state and run a gap analysis, then implement; no blind coding. (AG-031)
