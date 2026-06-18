---
name: conventional-commits
description: Use when writing git commit messages — formats them per the Conventional Commits spec (type(scope): summary) with an optional body and footer.
---

# Conventional Commits

Write commit messages in the Conventional Commits format so history stays readable and tooling (changelogs, semver) can parse it.

## Format

```
<type>(<scope>): <summary>

<body>

<footer>
```

- **type** (required): `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`.
- **scope** (optional): the area changed, e.g. `feat(auth): …`.
- **summary** (required): imperative mood, lower-case, ≤ 72 chars, no trailing period.
- **body** (optional): what changed and why, wrapped at ~72 columns.
- **footer** (optional): `BREAKING CHANGE: …`, or issue refs like `Closes #123`.

## Rules

- One logical change per commit.
- Use `feat` for new features and `fix` for bug fixes.
- Mark a breaking change with a `BREAKING CHANGE:` footer or a `!` after the type/scope.
- Use the imperative ("add", not "added") and don't end the summary with a period.

## Examples

- `feat(cli): add --json output flag`
- `fix(parser): handle empty input without throwing`
- `refactor(core): extract token bucket into its own module`
- `feat(api)!: drop deprecated v1 endpoints` — with footer `BREAKING CHANGE: v1 routes removed`
