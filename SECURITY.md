# Security Policy

ReelVault is a self-hosted media server. It runs a network-facing HTTP API,
manages user accounts, and executes third-party plugins inside the server
process. Because plugins run with full server access, plugin-related
vulnerabilities are treated with the same seriousness as core server ones.

## Reporting a Vulnerability

**Please do not open a public issue for security vulnerabilities.**

Report privately through GitHub Security Advisories on the affected
repository:

1. Go to the repository's **Security** tab.
2. Click **Report a vulnerability**.
3. Fill in as much detail as you can — affected version, reproduction
   steps, and potential impact.

If you're unsure which repository is affected, use
[ReelVault/reelvault](https://github.com/ReelVault/reelvault/security/advisories/new) —
the core server.

This opens a private discussion with maintainers only, visible to no one
else until a fix is ready and you both agree to disclose.

## What to Expect

- **Acknowledgment**: within a few days of the report.
- **Assessment**: we'll confirm whether it's a valid vulnerability and its
  severity.
- **Fix & disclosure**: once a fix is ready, we'll coordinate a release and
  public advisory. Credit is given to reporters unless you ask to stay
  anonymous.

There's no bug bounty program at this time — this is a small, independently
maintained open-source project.

## Supported Versions

ReelVault does not yet have a formal long-term-support policy. Until a
`SECURITY.md` update says otherwise, only the **latest released version**
of each component is supported with security fixes.

## Scope

This policy covers all repositories under the
[ReelVault organization](https://github.com/ReelVault), including:

- [`reelvault`](https://github.com/ReelVault/reelvault) — server & plugin host
- [`website`](https://github.com/ReelVault/website) — web/desktop client
- [`sdk`](https://github.com/ReelVault/sdk) — plugin & client SDK
- [`plugins`](https://github.com/ReelVault/plugins) — plugin catalog
- [`plugin-template`](https://github.com/ReelVault/plugin-template)
- [`reelvault.org`](https://github.com/ReelVault/reelvault.org) — docs site

Third-party plugins not published in the official `plugins` catalog are
outside this policy's scope — report issues with those directly to their
authors.

## Known Risk Areas

For context when reporting: plugins execute in-process with the
capabilities they declare in `plugin.json`. A plugin requesting more
capabilities than it needs, or a capability check that can be bypassed, is
considered a valid security concern even without a working exploit.
