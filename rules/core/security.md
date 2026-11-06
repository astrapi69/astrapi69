<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Security

- Report a security vulnerability only in a private security advisory, never in a public issue, PR, commit or comment; a public issue follows the fixed release. (AG-032)
- Before a public text names a consumer's defect, read its SECURITY.md; hold a possible confidentiality or integrity hole in a release and tell the maintainer. (AG-033)
- Never commit or write down a secret (key, real keystore, password, token, API key) in code, config, notes or docs; git-ignore .env, make test keys at runtime. (AG-034)
- Never let a secret or plaintext reach a message, the chat, a log or build output. (AG-035)
- Pass a secret by standard input, a hidden prompt or an environment variable of the one process, never as a command-line argument. (AG-036)
