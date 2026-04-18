# Contributing to ByteVeda

Thanks for your interest in contributing! ByteVeda is a collection of
independent libraries — some written in Rust with bindings for other
languages, some pure-Python or pure-Java, some other stacks entirely. This
guide covers the shared expectations that apply across every repo in the
organization.

Individual repositories may add their own `CONTRIBUTING.md` with
project-specific setup, build, and test instructions — always read the repo's
`README.md` and local `CONTRIBUTING.md` first.

## Ways to contribute

- **Report a bug** — open an issue in the relevant repo with a minimal
  reproduction, the version you're on, and your platform.
- **Suggest a feature** — start a
  [discussion](https://github.com/ByteVeda/.github/discussions) before writing
  code. It saves everyone time if the idea isn't a fit.
- **Improve docs** — typos, clearer examples, missing sections. Docs PRs are
  reviewed quickly and are the easiest way to get familiar with a codebase.
- **Fix an issue** — look for issues labeled `good first issue` or
  `help wanted` across the org.
- **Write a benchmark** — we care about measured performance, not vibes. Solid
  benchmarks are always welcome.

## Development workflow

The shape is the same regardless of language:

1. **Clone the repo** and read its `README.md` — it lists the required
   toolchain (Rust, Python, JDK, Node, etc.), any native dependencies, and the
   one-command setup for that project.
2. **Install the toolchain** exactly as the README specifies. If anything in
   the setup is unclear or broken, that itself is a contribution — open an
   issue or a docs PR.
3. **Build and run the full test suite** before you write any code — confirm
   the baseline passes on your machine.
4. **Create a feature branch** off `main`:

   ```bash
   git checkout -b feat/short-description
   ```

5. **Make your change.** Keep commits focused. Add or update tests that
   exercise the new behavior.
6. **Run the repo's check suite** before pushing — each project documents its
   own lint, format, and test commands. Match the existing style; don't
   reformat unrelated code.
7. **Push and open a pull request** against `main`. Describe *what* changed
   and *why* — a link to the related issue or discussion is ideal.

## Pull request expectations

- **One logical change per PR.** If you're fixing two unrelated bugs, open two
  PRs. Smaller PRs merge faster.
- **Tests required** for new behavior and bug fixes. "I tested it manually" is
  fine for docs-only changes; it's not fine for code.
- **No breaking public API changes** without prior discussion — open an issue
  first so we can plan the migration.
- **Commit messages:** imperative mood, under ~72 chars for the headline, body
  for context. Example: `fix(taskito): handle zero-length queues on shutdown`.
- **Sign off your commits** if the repo requires DCO (check the repo's
  `CONTRIBUTING.md`).

We review PRs within a few days. If yours has been quiet for longer than a
week, feel free to comment to ping us.

## Code style

Every repo ships its own formatter and linter config. **Run what the repo
runs** — don't override or ignore it in your PR. You don't need to memorize
the rules; the tools are the source of truth.

## Licensing

Contributions are licensed under each repository's license — typically
**MIT OR Apache-2.0** dual-licensed. By opening a PR, you agree your
contribution may be distributed under those terms. If the repo requires DCO
sign-off, add `-s` to your commits (`git commit -s`).

## Code of conduct

Be kind. Assume good intent. Disagree on technical merits, not people. We
follow the [Contributor Covenant](https://www.contributor-covenant.org/) —
violations can be reported to the maintainers or to GitHub directly.

## Getting help

- **Questions about using a library:** open a GitHub Discussion in that repo,
  or a general one in
  [ByteVeda/.github discussions](https://github.com/ByteVeda/.github/discussions).
- **Questions about contributing:** open a discussion or comment on the issue
  you're working on.

Thanks again for showing up.
