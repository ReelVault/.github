# .github

Organization-wide defaults for [ReelVault](https://github.com/ReelVault)
repositories.

GitHub automatically falls back to the files in this repo for any
repository in the organization that doesn't have its own copy:

- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`
- `SECURITY.md`
- `CODEOWNERS`
- `.github/ISSUE_TEMPLATE/*`
- `.github/pull_request_template.md`

`profile/README.md` is the organization's public profile page, shown at
[github.com/ReelVault](https://github.com/ReelVault).

If a repository needs different conventions than the org default (e.g. a
different CODEOWNERS reviewer, or an extra issue template type), add that
file directly in that repository — a repo-local file always takes
precedence over this one.
