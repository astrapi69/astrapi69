<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# Security

- Report a security vulnerability only in a private security advisory, never in a public issue, PR, commit or comment; a public issue follows the fixed release. A review by another AI that the maintainer forwards is kept in the private notes repository with its date, the question and the result; confidential material (an unpublished vulnerability, the content of the private notes, a secret) never goes to an outside service. (AG-032)
- Whoever works privately on a security finding under AG-032 claims the public issue at once: the label status:in-progress and the board entry, with nothing about the finding in them; a second session then neither fixes nor describes it publicly. (AG-115)
- Until its advisory is published, a security fix leaves no public trace of the advisory: no advisory id in a branch name, a test plan or the CHANGELOG; no hint of an advisory in a commit, pull request, issue or comment text, nor in a test case or a CHANGELOG line that describes the defect (the neutral announcement the repository's release workflow provides stays allowed); and the patches of a private fork reach the public repository, the head branch of a pull request included, only as one squash commit with a neutral message, since a pull request's commits stay readable through refs/pull/N/head, while RL-002's two commits stay in the private fork. (AG-117)
- Before a public text names a consumer's defect, read its SECURITY.md; hold a possible confidentiality or integrity hole in a release and tell the maintainer. (AG-033)
- Never commit or write down a secret (key, real keystore, password, token, API key) in code, config, notes or docs; git-ignore .env, make test keys at runtime. (AG-034)
- Never let a secret or plaintext reach a message, the chat, a log or build output. (AG-035)
- Pass a secret by standard input, a hidden prompt or an environment variable of the one process, never as a command-line argument. (AG-036)
- Before a repository is opened to cloud agents, and once a month for the private notes repository, scan its whole history for secrets (a tool such as gitleaks); report place and commit, never a value. (NW-014)
- Delete a secret from a store (a CI secret, a keyring entry) only when it is proven that nothing reads it any more: every workflow on every branch, every unit and every script checked, with the command and its result recorded. (NW-025)
