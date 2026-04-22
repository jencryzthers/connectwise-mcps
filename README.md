# ConnectWise MCPs — issue tracker & landing page

This repository is a **public issue tracker and landing page** for the
three ConnectWise MCPs published on npm under the
[`@goxtechnologies`](https://www.npmjs.com/~goxtechnologies) scope. The
source code for each MCP and its Claude Code plugin companion is
maintained in private repositories; the npm tarballs are released under
the MIT License.

If you're looking for bug reports, feature requests, or general questions
about any of the MCPs, **[open an issue here](../../issues/new/choose)**.
Security issues follow the coordinated-disclosure process documented in
each project — please **do not** open a public issue for a security
concern.

## Packages

| Product | MCP (npm) | DXT installer | Plugin name |
|---|---|---|---|
| **ConnectWise PSA** (Manage) | [`@goxtechnologies/connectwise-psa-mcp`](https://www.npmjs.com/package/@goxtechnologies/connectwise-psa-mcp) | `.dxt` attached to GitHub Releases | `connectwise-psa` |
| **ConnectWise RMM** (Asio) + ScreenConnect | [`@goxtechnologies/connectwise-rmm-mcp`](https://www.npmjs.com/package/@goxtechnologies/connectwise-rmm-mcp) | `.dxt` on Releases | `connectwise-rmm` |
| **ConnectWise CPQ** (Quosal Sell) | [`@goxtechnologies/connectwise-cpq-mcp`](https://www.npmjs.com/package/@goxtechnologies/connectwise-cpq-mcp) | `.dxt` on Releases | `connectwise-cpq` |

## What these are

Each MCP is a [Model Context Protocol](https://modelcontextprotocol.io)
server that lets AI assistants (Claude Code, Claude Desktop, any MCP-aware
client) interact with the corresponding ConnectWise product. The plugins
wrap the MCPs with agents, slash commands, skills, and safety hooks
tailored for MSP technicians.

Published under MIT License. Independent community project, **not
affiliated with, endorsed by, or sponsored by ConnectWise LLC**.
"ConnectWise", "ConnectWise PSA", "Manage", "ConnectWise RMM", "Asio",
"ScreenConnect", "Control", "ConnectWise CPQ", "Quosal", and "Sell" are
trademarks of ConnectWise LLC.

## Install

Each MCP can be launched directly via `npx` (no install needed):

```bash
npx -y @goxtechnologies/connectwise-psa-mcp
npx -y @goxtechnologies/connectwise-rmm-mcp
npx -y @goxtechnologies/connectwise-cpq-mcp
```

For Claude Code plugin install (requires access to the companion private
repos — contact the maintainer if you want access):

```
/plugin marketplace add jencryzthers/gox-marketplace
/plugin install connectwise-psa@connectwise
/plugin install connectwise-rmm@connectwise
/plugin install connectwise-cpq@connectwise
```

## Why is the source private?

The source code is maintained in private repositories by the publishing
organisation. The npm tarballs are released under the MIT License — you
are free to use, modify, and redistribute them per the license terms (see
`LICENSE` inside each tarball).

Public issues, feature requests, and security advisories are handled
here. If you need access to the source for a specific reason (audit, PR,
contribution), open an issue and we'll discuss.

## Filing an issue

- **Bug in a specific MCP?** Pick the matching template (PSA / RMM / CPQ
  bug report). Include version, Node.js version, Claude client, and
  redacted logs. See the template for redaction guidance.
- **Feature request?** Use the feature request template. If it's a new
  named operation, reference the ConnectWise API endpoint it would map
  to.
- **Security concern?** Use **Security → Report a vulnerability** on the
  corresponding product repo, or email the maintainer. **Do not** open a
  public issue.

## Support the maintainer

These MCPs are maintained by a single person on personal time. If they save
you time or headaches, a small contribution is genuinely appreciated:

- ☕ [**GitHub Sponsors**](https://github.com/sponsors/jencryzthers) — recurring or one-time, 0% platform fees
- 💰 [**PayPal**](https://www.paypal.com/paypalme/jcproulx) — one-time, choose your amount

Goes to the maintainer personally, not to GOX Technologies. Totally
optional. Zero impact on support or issue triage — the MIT "AS IS"
clause still applies. Think of it as buying the maintainer a coffee.

## License

This landing repo itself is MIT-licensed. Each npm package ships its own
`LICENSE` file — see the tarball contents.
