# How my projects are made

I wrote most of these projects myself over many years, long before there were AI tools. Since
2026 I use AI agents as a tool to modernize, maintain and secure them, and to develop new parts,
such as Lethenon and the wallet in mystic-crypt-ui.

With their help, these were added: unit tests, parameterized tests and mutation tests;
parity tests against other implementations, such as KeePassXC and gpg; GitHub Actions for build,
checks and publishing; the upkeep of the dependencies; signed releases; decision records; and a
number of security findings in old code, published as advisories and fixed.

I set the goals, the rules and the architecture, and I make every decision beyond them. I look at
every pull request, but I do not read every line of code. I approve every release in person and
sign it with my key.

The AI agents are tools, not authors. I decide what is published. Use is governed by the license of
each project; the software is provided without warranty.

## Where to see it

- The rules every agent session follows, with the source of each: [rules/](rules/index.md)
- Security advisories, each with the version that fixes it:
  [mystic-crypt-ui](https://github.com/astrapi69/mystic-crypt-ui/security/advisories),
  [mystic-crypt](https://github.com/astrapi69/mystic-crypt/security/advisories),
  [randomizer](https://github.com/astrapi69/randomizer/security/advisories)
- How the projects are tested, and what that found:
  [mystic-crypt TESTING.md](https://github.com/astrapi69/mystic-crypt/blob/develop/docs/TESTING.md),
  [mystic-crypt-ui testing.md](https://github.com/astrapi69/mystic-crypt-ui/blob/develop/docs/testing.md)
- Parity tests: the KDBX suite of mystic-crypt-ui against KeePassXC
  ([src/e2eKdbx](https://github.com/astrapi69/mystic-crypt-ui/tree/develop/src/e2eKdbx)), the GnuPG
  tests of mystic-crypt against a real gpg home
  ([gnupg tests](https://github.com/astrapi69/mystic-crypt/tree/develop/src/test/java/io/github/astrapi69/mystic/crypt/gnupg))
- Decision records:
  [mystic-crypt-ui](https://github.com/astrapi69/mystic-crypt-ui/tree/develop/docs/decisions),
  [Lethenon](https://github.com/astrapi69/lethenon/tree/develop/docs/adr)
- Signed releases, and how to verify them: the section "Verifying the release signatures" in the
  READMEs of [mystic-crypt](https://github.com/astrapi69/mystic-crypt#verifying-the-release-signatures)
  and [Lethenon](https://github.com/astrapi69/lethenon#verifying-the-release-signatures)

Since November 2026, commits and pull requests carry no AI attribution line; this page says it once, for all of
them. Older commits and pull requests may still carry one.

Asterios Raptis
