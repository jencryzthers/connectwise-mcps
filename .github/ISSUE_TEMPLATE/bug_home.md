---
name: "Bug: Home MCP (experimental)"
about: A bug in @goxtechnologies/connectwise-home-mcp (partner identity portal / SF support cases)
title: "[Home] "
labels: bug, home, experimental
---

<!--
SECURITY ISSUES: do NOT file them here. Use Security → Report a vulnerability.

The Home MCP is experimental — it targets home.connectwise.com which has no
public API. It uses Playwright to drive an authenticated browser and may be
more sensitive than the PSA/RMM/CPQ MCPs to portal UI changes on CW's side.
-->

## What happened?

## Expected

## Reproduction steps

1.
2.
3.

## Environment

- `@goxtechnologies/connectwise-home-mcp` version:
- Node.js version:
- OS:
- Playwright version (`node -e "console.log(require('playwright/package.json').version)"`):
- Claude client (Claude Desktop / Claude Code / MCP Inspector):
- Headless or headful (`CW_HOME_HEADLESS` value):

## What tool / named operation were you calling?

- Tool: `cw_home_...`
- (If `cw_home_operation`) Operation name:
- (If bridging to SF) Case number:

## Redacted logs

<details>
<summary>stderr output</summary>

```
<paste — scrub bearer tokens, cookies, case numbers, email addresses>
```

</details>

## Browser state

- [ ] Have you run `cw_home_login` recently?
- [ ] Does `cw_home_session_status` show valid cookies?
- [ ] If the issue is on a SF route (partnersupport), have you tried clearing `~/.config/connectwise-home/data/browser-state.json` and logging in fresh?
