# Contributing to ByteVeda

Thanks for your interest in contributing! ByteVeda builds libraries with Rust
cores and ergonomic bindings for Python, Java, and beyond. We welcome
contributions from everyone — first-time open source contributors included.

This guide applies org-wide. Individual repositories may add their own
`CONTRIBUTING.md` at the repo root that overrides or extends this one — always
check there first.

## Ways to contribute

- **Report a bug** — open an issue in the relevant repo with a minimal
  reproduction, the version you're on, and your platform.
- **Suggest a feature** — start a [discussion](https://github.com/ByteVeda/.github/discussions)
  before writing code. It saves everyone time if the idea isn't a fit.
- **Improve docs** — typos, clearer examples, missing sections. Docs PRs are
  reviewed quickly and are the easiest way to get familiar with a codebase.
- **Fix an issue** — look for issues labeled `good first issue` or
  `help wanted` across the org.
- **Write a benchmark** — we care about measured performance, not vibes. Solid
  benchmarks are always welcome.

## Development workflow

Every ByteVeda library follows the same basic shape:

1. **Clone the repo** and read its `README.md` — setup varies slightly by
   project (Python vs. Java bindings, additional native deps, etc.).
2. **Install the toolchain.** You need a recent stable Rust
   (`rustup install stable`) plus the language runtime the bindings target
   (Python 3.10+ / JDK 21 / etc.).
3. **Build and test locally** before you write any code — confirm the existing
   test suite passes on your machine:

   ```bash
   cargo test
   # plus binding-specific tests, e.g.:
   # maturin develop && pytest   (Python)
   # ./gradlew test              (Java)
   ```

4. **Create a feature branch** off `main`:

   ```bash
   git checkout -b feat/short-description
   ```

5. **Make your change.** Keep commits focused. Add or update tests that
   exercise the new behavior.
6. **Run the full check suite** before pushing:

   ```bash
   cargo fmt --check
   cargo clippy -- -D warnings
   cargo test
   ```

7. **Push and open a pull request** against `main`. Describe *what* changed and
   *why* — a link to the related issue or discussion is ideal.

## Pull request expectations

- **One logical change per PR.** If you're fixing two unrelated bugs, open two
  PRs. Smaller PRs merge faster.
- **Tests required** for new behavior and bug fixes. "I tested it manually" is
  fine for docs-only changes; it's not fine for code.
- **No breaking public API changes** without prior discussion — open an issue
  first so we can plan the migration.
- **Commit messages:** imperative mood, <72 chars headline, body for context.
  Example: `fix(taskito): handle zero-length queues on shutdown`.
- **Sign off your commits** if the repo requires DCO (check the repo's
  `CONTRIBUTING.md`).

We review PRs within a few days. If yours has been quiet for longer than a
week, feel free to comment `@<maintainer>` to ping us.

## Code style

- **Rust:** rustfmt and clippy with the settings in each repo's
  `rustfmt.toml` / `clippy.toml`. Don't override them in your PR.
- **Python bindings:** ruff for linting and formatting; pyright for types.
- **Java bindings:** `./gradlew spotlessApply`.
- **Docs:** wrap at 80 columns. American English spelling.

## Licensing

Contributions are licensed under each repository's license — typically **MIT
OR Apache-2.0** dual-licensed. By opening a PR, you agree your contribution
may be distributed under those terms. If the repo requires DCO sign-off, add
`-s` to your commits.

## Code of conduct

Be kind. Assume good intent. Disagree on technical merits, not people. We
follow the [Contributor Covenant](https://www.contributor-covenant.org/) —
violations can be reported to the maintainers via email or to GitHub directly.

## Getting help

- **Questions about using a library:** open a GitHub Discussion in that repo,
  or a general one in [ByteVeda/.github discussions](https://github.com/ByteVeda/.github/discussions).
- **Questions about contributing:** open a discussion or ping a maintainer on
  the issue you're working on.

Thanks again for showing up.
