# Contributing to ReelVault

Thanks for wanting to help! This file covers the conventions shared across
every repository in the [ReelVault organization](https://github.com/ReelVault).
Each repository's own `README.md` (and `AGENTS.md`, for AI coding agents)
covers what is specific to that project, such as build steps and architecture
notes.

## Before you start

- For anything beyond a small fix, **open an issue first** to discuss the
  approach. It saves you from writing a pull request that gets rejected.
- Check existing issues and pull requests so you don't duplicate work.
- Report security vulnerabilities through [`SECURITY.md`](./SECURITY.md),
  never in a public issue.

## Workflow

1. Fork the repository and create a branch from `main`.
2. Make your change.
3. Run the checks for that repository (see [Local checks](#local-checks)).
4. Open a pull request against `main` and fill in the template.
5. A maintainer reviews it. Every pull request needs passing CI and a
   maintainer's approval before it merges. This applies to everyone,
   maintainers included.

## Local checks

All repositories use [Bun](https://bun.sh) and the same script names:

| Script | What it checks | Repositories |
| --- | --- | --- |
| `bun run lint` | Biome and oxlint, read-only | `reelvault`, `website`, `sdk`, `plugins` |
| `bun run check-types` | TypeScript types | `reelvault`, `website`, `sdk`, `plugins`, `plugin-template` |
| `bun run deadcode` | Unused files, exports and dependencies (Knip) | `reelvault`, `website`, `sdk`, `plugins` |
| `bun run test` | Test suite | `reelvault`, `website`, `sdk`, `plugins` |
| `bun run build` | Builds the plugin zip | `plugin-template` |

`plugin-template` has no linter, test suite or dead-code check: it is a small
starting point for your own plugin, and you add those tools if you need them.

For example, in `sdk`, from the repository root:

```bash
bun install
bun run lint
bun run check-types
bun run deadcode
bun run test
```

CI runs the same checks on every pull request, and a pull request won't merge
until they pass. If a script in the table no longer exists, check that
repository's `package.json`.

## Code style

- Don't fight the linter. If Biome or oxlint flags something, fix it rather
  than suppressing it. Avoid lint-suppression comments such as
  `// biome-ignore`. If a rule is wrong for the codebase, open an issue to
  discuss changing the config.
- TypeScript: prefer `unknown` over `any`, and use the strictest types the
  situation allows.
- Follow the style of the file you're editing rather than introducing a new
  pattern.

## Commit messages

Write a short, present-tense summary of what changed, and why if it isn't
obvious. No strict format is enforced. Small, focused commits are easier to
review than one large diff.

Example: `Add retry button to failed downloads`

## Plugin contributions

If you're contributing a plugin to the [catalog](https://github.com/ReelVault/plugins)
or building a new one from the [template](https://github.com/ReelVault/plugin-template),
read the [plugin authoring guide](https://reelvault.org/plugins/getting-started)
first. It covers the manifest, capability declarations and the submission
process in more detail than fits here.

## Documentation contributions

The documentation lives in the [`reelvault.org`](https://github.com/ReelVault/reelvault.org)
repository as Markdown files. Small fixes, such as typos, broken links or
unclear wording, don't need an issue first. Just open a pull request.

## Questions

Open a [discussion](https://github.com/orgs/ReelVault/discussions) if the
repository has discussions enabled. Otherwise, open an issue with the
`question` label.
