# Security Policy

## Scope

This repository is the **public issue tracker and landing page** for the four ConnectWise MCPs.

Security concerns should be directed to the corresponding product's private security policy:

## How to report

1. **Use GitHub Security Advisories** on this repo (*Security → Report a vulnerability*). We'll triage and route to the appropriate private repo internally.
2. Include:
   - Which package
   - Version
   - Description + reproduction steps
   - Impact assessment
3. Acknowledgement within **72 hours**.
4. Target fix timelines: critical = 14 days, medium = 30 days, low = next regular release.

## Do NOT

- Open a public issue for security concerns — the issue tracker on this repo is **public**.
- Post reproduction details in a public PR description or commit message.

## In scope

- Credential leaks through any MCP tool output or error path
- Authentication bypasses
- Prompt injection surfaces that escalate capability
- Dependency-chain CVEs
- Hook confirmation-gate bypasses (especially on RMM's `cw_rmm_sc_send_command`)
- Home MCP: OIDC bearer-token leaks through any tool response, `storageState.json` permissions regressions, XHR-capture redaction bypasses, off-origin navigation that escapes the origin allow-list

## Out of scope

- ConnectWise API bugs (report to ConnectWise LLC)
- Claude Code / Claude Desktop bugs (report to Anthropic)
- Social-engineering attacks against maintainers

## Coordinated disclosure

Up to 90 days from initial report. Public advisory + CVE is filed after a patched release is on npm.
