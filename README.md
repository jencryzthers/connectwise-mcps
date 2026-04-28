# ConnectWise MCPs — issue tracker & landing page

Public issue tracker and landing page for four MCP (Model Context Protocol)
servers. The source code is maintained in private
repositories; the npm tarballs are released under the MIT License.

If you're looking for bug reports, feature requests, or general questions
about any of the MCPs, **[open an issue here](../../issues/new/choose)**.
Security issues follow coordinated disclosure — see [SECURITY.md](./SECURITY.md).
**Do not** open a public issue for a security concern.

## Packages

| Product | npm Package |
|---|---|---|
| **ConnectWise PSA** (Manage) | [`connectwise-psa-mcp`](https://www.npmjs.com/package/@goxtechnologies/connectwise-psa-mcp) |
| **ConnectWise RMM** (Asio) + ScreenConnect | [`connectwise-rmm-mcp`](https://www.npmjs.com/package/@goxtechnologies/connectwise-rmm-mcp) |
| **ConnectWise CPQ** (Quosal Sell) | [`connectwise-cpq-mcp`](https://www.npmjs.com/package/@goxtechnologies/connectwise-cpq-mcp) | 
| **ConnectWise Home** (partner identity portal) | [`@connectwise-home-mcp`](https://www.npmjs.com/package/@goxtechnologies/connectwise-home-mcp) | 

Each MCP is a [Model Context Protocol](https://modelcontextprotocol.io)
server that lets AI assistants (Claude Desktop, Claude Code, any
MCP-aware client) interact with the corresponding ConnectWise product.

**All MCP** are flagged as experimental.

### Claude Desktop Extension (.dxt) bundles

Download the latest `.dxt` from [**Releases**](../../releases) and
double-click to install into Claude Desktop. Releases are tagged per
product so you can find the one you want:

- `psa-vX.Y.Z` → ConnectWise PSA
- `rmm-vX.Y.Z` → ConnectWise RMM + ScreenConnect
- `cpq-vX.Y.Z` → ConnectWise CPQ
- `home-vX.Y.Z` → ConnectWise Home

Every release here mirrors an npm publish of the matching package —
same version, same code, with the prebuilt `.dxt` attached as a release
asset.

## Who maintains this? Why is the source private?

The source code lives in private repositories under the maintainer's
personal account. The npm tarballs are distributed under the
[MIT License](https://opensource.org/licenses/MIT) — you are free to
use, modify, and redistribute them per the license terms (see `LICENSE`
inside each tarball).

Public issues, feature requests, and security advisories are handled
here. If you need access to the source for a specific reason (audit,
PR, contribution), open an issue and we'll discuss.

## Filing an issue

- **Bug in a specific MCP?** Pick the matching template (PSA / RMM /
  CPQ / Home). Include version, Node.js version, Claude client, and
  redacted logs.
- **Feature request?** Use the feature request template. If it's a new
  named operation, reference the ConnectWise API endpoint it would map
  to.
- **Security concern?** Use **Security → Report a vulnerability** on
  this repo, or see [SECURITY.md](./SECURITY.md) for routing to
  per-product policies. **Do not** open a public issue.

---

## Legal notices and responsibilities

These are the shared terms for all MCPs in this suite. They
supplement — and in case of conflict, are subordinate to — the MIT
License in each package's tarball.

### MIT License

Each of the three packages is released under the
[MIT License](https://opensource.org/licenses/MIT). The full license
text ships inside every npm tarball (`LICENSE` file). You may use,
modify, merge, publish, distribute, sublicense, and/or sell copies of
the software freely, subject to including the copyright notice and
permission notice.

### No warranty — "AS IS"

**THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.**

Neither the maintainer (jencryzthers) nor GOX Technologies Inc. (npm
scope owner) is liable for any data loss, service disruption,
unauthorized access, financial loss, or any other damage arising from
your use of these MCPs. **Use at your own risk.**

### Experimental software

These MCPs are an personnal active experiment in AI-assisted MSP operations. The
core tools (API calls, ticket/device/quote queries, named operations)
are well-tested and used daily by the maintainer. Many analytics
handlers and advanced features have seen limited real-world testing.
Features may be added, changed, or removed without notice between
versions.

**This software is NOT a substitute for professional judgment.** All
outputs, recommendations, and actions should be independently verified
by qualified IT professionals before being relied upon. When used with
an AI assistant, the model may propose or execute actions that are
incorrect, incomplete, or destructive — **human review of all
AI-proposed actions is strongly recommended.**

### Your responsibilities as a user

By using these MCPs, you accept full responsibility for:

- **Credentials.** You obtain, store, rotate, and secure your own
  ConnectWise API credentials. Never commit them. Use
  minimum-privilege keys scoped to only the endpoints you need.
- **Actions performed.** These MCPs can create, modify, and delete
  records in your ConnectWise PSA, RMM, CPQ, and Home instances —
  tickets, time entries, agreements, endpoints, quotes, customers,
  **user accounts** (invite, disable, delete), roles, and support
  cases. **You bear full responsibility for every action performed
  through this software**, including actions initiated by an AI
  assistant acting via the MCP.
- **Remote command execution** (RMM/ScreenConnect). The RMM MCP can
  execute arbitrary shell commands on live customer endpoints via
  ScreenConnect. Confirmation gates are in place, but ultimately
  **you** decide what gets run. A hook bypass or an approved
  destructive command is your responsibility.
- **Compliance with ConnectWise's terms.** Your use of the ConnectWise
  APIs is governed by your agreements with ConnectWise LLC. Neither
  the maintainer nor GOX Technologies is responsible for any
  ConnectWise Terms of Service violations resulting from your use of
  these MCPs.

### Data and privacy

- **No telemetry.** These MCPs do not phone home. Neither the
  maintainer nor GOX Technologies has any access to your API
  credentials, your ConnectWise data, or any actions you perform
  through the software.
- **Local state only.** Cached data (SQLite catalogues, saved queries,
  browser state for the PSA and Home web scrapers) is stored entirely
  under `~/.config/connectwise-<product>/` on the user's machine.
  Nothing leaves your environment unless you explicitly ship it. The
  Home MCP additionally persists a Playwright `storageState.json` with
  OIDC cookies at mode `0o600` — treat this file as sensitive.
- **Credentials file permissions.** Each MCP refuses to load a `.env`
  file whose permissions allow group/world read. This is a defensive
  default — it's on you to actually `chmod 600` the file and keep it
  out of version control.

### ConnectWise trademark notice

"ConnectWise", "ConnectWise PSA", "ConnectWise Manage", "ConnectWise
RMM", "ConnectWise Asio", "ConnectWise ScreenConnect", "ConnectWise
Control", "ConnectWise CPQ", "ConnectWise Home", "Quosal", and "Sell"
are trademarks or registered trademarks of **ConnectWise LLC**.

These packages are **NOT** official ConnectWise products. They are
**NOT** developed, endorsed, sponsored, certified, or approved by
ConnectWise LLC. Neither the maintainer nor GOX Technologies Inc. has
any affiliation with ConnectWise LLC. These marks are referenced
solely to identify the third-party APIs this software interoperates
with.

### ConnectWise API licensing (your own)

To use these MCPs you must hold your own valid ConnectWise PSA,
ConnectWise RMM, ConnectWise ScreenConnect, ConnectWise CPQ, and/or
ConnectWise Home partner-portal access and API credentials, as
applicable. These MCPs do not grant, transfer, or imply any license to
ConnectWise's software or APIs. The Home MCP in particular drives the
partner portal via browser automation; your use must comply with
ConnectWise's terms for authenticated portal access.

### AI-assisted operation disclaimer

When used with an AI assistant (Claude, GPT, or any other LLM), the
assistant may propose or execute actions based on its interpretation
of your request and the data returned by the MCP. **The assistant is
not guaranteed to be correct.** Examples of what can go wrong:

- Wrong ticket updated after ambiguous phrasing
- Wrong endpoint targeted by a remote command
- Time entry created against the wrong charge code
- Quote sent to the wrong customer
- Destructive operation (delete, uninstall) approved because the
  confirmation prompt wasn't read carefully

Every confirmation prompt exists because something real can be broken.
Read them before approving.

### Third-party dependencies

These MCPs bundle open-source packages governed by their own licenses:

- [better-sqlite3](https://github.com/WiseLibs/better-sqlite3) — MIT
- [@modelcontextprotocol/sdk](https://github.com/modelcontextprotocol/typescript-sdk) — MIT
- [zod](https://github.com/colinhacks/zod) — MIT
- [express](https://github.com/expressjs/express) — MIT (PSA + RMM MCPs)
- [js-yaml](https://github.com/nodeca/js-yaml) — MIT (RMM MCP)
- [playwright](https://github.com/microsoft/playwright) — Apache-2.0 (Home MCP; optional peer dependency)

Full `package-lock.json` files are available on request (open an issue
mentioning "dependency audit").

### Governing law

The MIT License is governed by its own terms. For any other dispute
arising from use of these MCPs, the parties agree to
**Québec, Canada** as the jurisdiction, without prejudice to your
rights under applicable consumer protection laws.

---

## License

This landing repo itself is MIT-licensed (see [LICENSE](./LICENSE)).
Each npm package ships its own `LICENSE` file — see the tarball
contents for the authoritative copy.

Copyright © 2024–2026 jencryzthers (maintainer). Published under the
`@goxtechnologies` npm scope. Packages are MIT-licensed; source code
is maintained privately by the maintainer.
