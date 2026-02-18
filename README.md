# git-commit-helper

A Claude Code skill that generates well-formatted conventional commit messages following the official Conventional Commits specification — enabling automated changelogs and semantic versioning.

![Claude Code skill](https://img.shields.io/badge/Claude_Code-skill-blue)

## What it does

Analyzes your diff or change description and produces a properly formatted commit message with the right type, scope, subject, body, and footer.

## Install

```bash
npx skills add git-commit-helper
```

Or clone manually:

```bash
git clone https://github.com/ccwriter369-beep/claude-skill-git-commit-helper \
  ~/.claude/skills/git-commit-helper
```

## Usage

```
/git-commit-helper
write a commit message
help with my commit
what should my commit say
format this commit
```

## Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

## Commit types

| Type | Purpose | SemVer impact |
|------|---------|---------------|
| `feat` | New feature | MINOR |
| `fix` | Bug fix | PATCH |
| `docs` | Documentation only | None |
| `refactor` | No behavior change | None |
| `perf` | Performance improvement | PATCH |
| `test` | Tests only | None |
| `chore` | Build/deps/tooling | None |
| `ci` | CI configuration | None |

**Breaking changes** → MAJOR version — use `!` after type or `BREAKING CHANGE:` footer.

## The 7 rules

1. Separate subject from body with blank line
2. Limit subject to 50 characters (72 hard max)
3. Capitalize the subject line
4. No period at end of subject
5. Use imperative mood ("Add" not "Added")
6. Wrap body at 72 characters
7. Body explains what and why, not how

**Imperative test:** "If applied, this commit will _[subject]_"

## Examples

```
feat(auth): add password reset flow
```

```
fix(api): handle null response from payment provider

Payment provider returns null for declined cards instead of
an error object. Add null check before processing response.

Fixes #234
```

```
feat(api)!: change user endpoint response format

BREAKING CHANGE: User endpoint now returns nested address object.
Clients must update to use user.address.street instead of user.street.
```

## License

MIT
