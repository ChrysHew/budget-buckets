# Commit Message Standards

This project follows [Conventional Commits
1.0.0](https://www.conventionalcommits.org/en/v1.0.0/), with one
project-specific rule: **commit bodies must use dash (`-`) bullet
points.**

## Format

``` text
<type>[optional scope]: <description>

- <change or detail>
- <change or detail>
```

The body is optional. If a body is included, every body line must be a
bullet beginning with `-`.

## Commit Types

Use these common types:

-   `feat` --- add a new feature
-   `fix` --- fix a bug
-   `docs` --- documentation changes
-   `refactor` --- restructure code without changing behavior
-   `test` --- add or update tests
-   `ci` --- CI/CD changes
-   `build` --- build system or dependency changes
-   `chore` --- maintenance that does not fit another type

## Scope

An optional scope can identify the affected part of the project.

``` text
feat(api): add transaction endpoint
```

``` text
fix(frontend): correct bucket balance display
```

## Breaking Changes

Use `!` before the colon when a change is breaking.

``` text
feat(api)!: change transaction response format
```

A `BREAKING CHANGE:` footer may also be used when additional explanation
is needed.

## Examples

``` text
docs: add initial project documentation

- Add product and technical requirements
- Add basic user flow
- Add UX flow
```

``` text
feat(api): add bucket creation

- Add bucket creation endpoint
- Validate bucket allocation amount
- Persist buckets to the database
```

``` text
fix(frontend): correct remaining balance

- Recalculate remaining balance after deleting a transaction
- Update bucket totals immediately
```

For very small changes, a body is not required:

``` text
docs: fix README typo
```
