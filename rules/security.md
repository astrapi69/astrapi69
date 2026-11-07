<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Security

Read on demand; the rules every session needs are in core/.

- Fix an advisory's issue in its private fork with the full local gate (no CI there); the maintainer approves the text, the fixed release ships, then the advisory is published and may be named. (AG-037)
- Keep tokens in the system keyring and pass them as environment variables; make them fine-grained, limited to your own repositories and with an expiry date. (AG-038)
- Check a keyring entry with `secret-tool lookup ... >/dev/null`, never with `secret-tool search`, which prints the secret in clear text. (AG-039)
- Overwrite files that held key material (`shred -u`) instead of only deleting them. (AG-040)
- Use only official or self-reviewed MCP servers, run them read-only until a write tool has a reason, and use a new one once for real after setup and record the result. (AG-041)
- Never hand-roll a cryptographic primitive (cipher, hash, signature, KDF, randomness, padding, IV or salt handling, key encoding, constant-time compare); own code only orchestrates proven ones. (AG-042)
- Build a new cryptographic construction first in lethenon under its ADR 0001 (peer-reviewed publication, the authors' test vectors), and move it into a library only after the external review. (AG-043)
- Hold passwords in char[] where the API allows, and clear sensitive buffers when feasible. (AG-044)
- Validate user-supplied files (type, size, format) before storing or parsing them. (AG-045)
- Never show raw HTTP details or stack traces to the users of a production build. (AG-046)
- Never render user content as raw HTML; use a renderer that sanitizes it. (AG-047)
- Make a helper that bulk-deletes, wipes or drops data refuse to run on production-marked data unless an explicit override is set. (AG-048)
- State in UI texts and docs what data leaves the device; never promise that no personal data is sent. (AG-049)
- Close a Dependabot alert on a test- or build-only dependency as tolerable_risk with the measured chain and an issue, then fix it at low priority; any other dismissal needs the maintainer's yes. (AG-050)
- Triage Dependabot alerts one row per package and manifest: version, scope (runtime, test, build), direct or transitive with the pulling package, severity, first fixed version, fix route; critical first; kept private. (NW-022)
