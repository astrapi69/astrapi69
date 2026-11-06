<!-- Generated from the consolidated rule inventory of 2026-11-06; the rule ids are explained in provenance.md. Change a rule here by pull request. -->

# The Java family

Read on demand; the rules every session needs are in core/.

- Apply the workflow rules of mystic-crypt's workflow.md in all three crypt-family repositories (mystic-crypt, crypt-data, crypt-api), whichever the work starts in. (AG-112)
- Deprecate a replaced method instead of removing it, and remove it only in the next major. (AG-113)
- Use a family library that almost fits and report the gap in its repository instead of working around it quietly; a workaround names the issue in a comment, and an open vulnerability goes only to a private advisory. (RL-101)
- Before using a family API inside a library, check that its package is exported to JPMS modules and that it behaves correctly; fix a defect at its source or work around it consciously with a comment saying why. (RL-102)
- Keep as a project's own only what it defines itself and what must not move with a library: identifiers in a persisted or signed format, its domain rules and its user-facing text. (RL-103)
- Declare a dependency where it is used, declare a used dependency directly instead of inheriting it through another, and import nothing just in case. (RL-104)
- Inside a family library, walk the hierarchy top-down and stop at the first level that fits: never an own cryptographic primitive, the JDK first (checked before assuming Bouncy Castle), own code last. (RL-105)
- Add a new dependency to a library only after asking and only when the JDK, Bouncy Castle and the family do not fit: maintained, no known CVEs, a sane transitive footprint, JPMS-capable. (RL-106)
- Write own code in the smallest scope that works and library-grade (own tests, javadoc, no incidental coupling), and state why no existing level fits. (RL-107)
- Compile, test and release every family library on JDK 25; one on an older version moves to 25 at its next release as a new major, with one CHANGELOG sentence naming the new minimum. (RL-108)
- Build only through the Gradle wrapper (./gradlew), with dependency versions in the version catalog gradle/libs.versions.toml. (RL-109)
- Give every new public package of a JPMS module its exports entry in module-info.java, and check that the consumer really resolves it. (RL-110)
- Format every file and its license header through Spotless: run spotlessApply before committing, and never hand-format against the formatter. (RL-111)
- Keep a family library's everyday local gate at ./gradlew build, with the tests, the JaCoCo floor inside check, and Spotless. (RL-112)
- Make javadoc warnings break the build (failOnError, -Werror, check depending on javadoc) at the next release of each repository an agent touches anyway, proven in the PR by a deliberately missing doc that fails it. (RL-113)
- Until a repository has -Werror, check javadoc for warnings with LC_ALL=C and a forced rerun, grepping the full log for warning|warnung and the summary line; never conclude from a default-locale or -q run. (RL-114)
- Fix the javadoc locale to en_US (options.locale plus the user.language and user.country jFlags) together with -Werror, proven by a build under a German locale that gives lang=en, English texts and equal artifacts. (RL-115)
- Build every family library reproducibly: Build-Jdk-Spec as the only JDK entry in the manifest, javac --release, reproducible archives, mavenLocal() only with -PuseMavenLocal, the JDK pinned in .sdkmanrc and workflows. (RL-116)
- Build a release with the JDK the repository pins, and take a newer JDK patch release deliberately in a small PR of its own that passes the gate, never automatically. (RL-117)
- Raise a family repository to the current Gradle when it is touched anyway, in its own commit: wrapper generated twice, its jar checked against the published sha256, .gitattributes, no --warning-mode all deprecation left. (RL-118)
- Raise silly-io and file-worker to 4.0 and 20.0 in the same change as the Gradle update of a repository that declares them. (RL-119)
- Run versionCatalogUpdate (stable selector) in a library before the release PR, with test counts before and after; fix a test that no longer compiles, never disable it, and build no gate or tool for this. (RL-120)
- Judge a transitive bump by the end-to-end suite, not by compilation: Gradle resolves a version conflict to the higher version whatever the consumer pins. (RL-121)
- Use release tags of the shape RELEASE-<projectVersion>, never vX.Y, made with the tagging target (./gradlew tagRelease, make tag-release) and never retyped from prose. (RL-122)
- Force only the test tasks in the release gate, each by name with its own --rerun, never --rerun-tasks; CI builds without --rerun. (RL-123)
- Copy build/test-results away before rerunning a failed suite, and give release gate runs TMPDIR and -Djava.io.tmpdir on a disk with room. (RL-124)
- Merge a PR in a repository where PIT runs only on GitHub only when the pitest check of its head is green, also while that check is not required. (RL-125)
- Write Java tests with JUnit Jupiter, with AssertJ-style fluent assertions where the neighbouring tests already use them. (RL-126)
- Give every class, test classes included, and every public member Javadoc in the style of its neighbours, and keep an existing {@inheritDoc} as it is. (DC-026)
- End a Javadoc sentence without a dot unless another sentence follows it. (DC-027)
- Name Java classes in PascalCase, methods and fields in camelCase and constants in UPPER_SNAKE_CASE. (DC-028)
- Declare a dependency you use directly in your own build, instead of inheriting it quietly through another one. (NW-013)

## Where to look

Before writing a class, a helper, a constant or an enum, look for it in the family first (RL-099). Where the
capabilities are:

| What | Where |
|---|---|
| algorithm names, key formats, key sizes, hash and cipher enums | crypt-api: `KeyPairGeneratorAlgorithm` (Ed25519, ML-DSA, SLH-DSA), `HashAlgorithm`, `KeyFormat`, `KeyFileFormat` |
| key readers and writers, PEM/DER, hex, certificates | crypt-data: `PrivateKeyReader`, `PublicKeyExtensions`, `HexExtensions` |
| signing, verifying, encryption, KEM, Shamir sharing, password hashing | mystic-crypt: `Ed25519Signer`, `Ed25519Verifier`, `SecretSharing`, the picocli command line |
| checksums | checksum-up |
| trees | gen-tree, tree-api |
| Swing components bound to a model | swing-model-components, swing-base-components, swing-renderer, swing-table-components, swing-tree-component, menu-action |
| random test data, test doubles | randomizer, test-object |
| files and IO | file-worker, silly-io, silly-collection |

The family's catalog of capabilities, entry points and tools is kept in the maintainer's private notes.
