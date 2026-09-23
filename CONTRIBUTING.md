# Contributing to ReelVault

Thanks for wanting to help. This file covers the conventions shared across
every repository in the [ReelVault organization](https://github.com/ReelVault).
Repository-specific details (build steps, architecture notes) live in each
repo's own `README.md` and `AGENTS.md`.

## Before you start

- For anything beyond a small fix, **open an issue first** to discuss the
  approach — it saves you from writing a PR that gets rejected.
- Check existing issues and PRs so you're not duplicating work.
- Security vulnerabilities go through [`SECURITY.md`](./SECURITY.md), never
  a public issue.

## Workflow

1. Fork the repository and create a branch off `main`.
2. Make your change.
3. Run the repo's checks locally before opening a PR (see below).
4. Open a pull request against `main`. Fill in the PR template.
5. A maintainer will review it. All PRs require passing CI and a
   maintainer's approval before merging — this applies to everyone,
   including maintainers themselves.

## Local checks

All ReelVault repositories use [Bun](https://bun.sh) and share the same
toolchain: [Biome](https://biomejs.dev) + [oxlint](https://oxc.rs) for
linting, `tsc --noEmit` for types, and [Knip](https://knip.dev) for dead
code. Before opening a PR, run (from the repo root):

```
bun install
bun run lint
bun run check-types
bun run deadcode
bun test
```

Exact script names can vary slightly per repo — check that repo's
`package.json` `scripts` section or `README.md` if a command above doesn't
exist.

CI runs the same checks on every PR; a PR won't be merged until they pass.

## Code style

- Don't fight the linter — if Biome/oxlint flags something, fix it rather
  than suppressing it. Lint-suppression comments (e.g. `// eslint-disable`,
  `// biome-ignore`) are avoided; if a rule is genuinely wrong for the
  codebase, open an issue to discuss changing the config instead.
- TypeScript: prefer `unknown` over `any`; use the strictest types the
  situation allows.
- Match the existing style of the file you're editing over introducing a
  new pattern.

## Commit messages

Write a clear, present-tense summary of *what* changed and, if not
obvious, *why*. No strict format is enforced, but small, focused commits
are easier to review than one giant diff.

## Plugin contributions

If you're contributing a plugin to the [catalog](https://github.com/ReelVault/plugins)
or building a new plugin from the
[template](https://github.com/ReelVault/plugin-template), see the
[plugin authoring guide](https://reelvault.org/plugins/getting-started)
first — it covers manifest requirements, capability declarations, and the
submission process in more detail than fits here.

## Documentation contributions

Docs live in [`reelvault.org`](https://github.com/ReelVault/reelvault.org)
as plain Markdown (no MDX). Small fixes (typos, broken links, unclear
wording) don't need an issue first — just open a PR.

## Questions

Open a [discussion](https://github.com/orgs/ReelVault/discussions) if the
repo has one enabled, or an issue tagged `question`.
