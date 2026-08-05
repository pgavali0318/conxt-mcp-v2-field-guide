# Conxt Field Guide — Upgrading MCP Python SDK to v2

A free, practical migration and interoperability guide for teams running **production MCP servers** who are moving to the **MCP Python SDK v2** (the 2026-07-28 specification).

📄 **[Read the guide (PDF)](./conxt-mcp-v2-field-guide.pdf)** · 🌐 **[Read it in your browser](./conxt-mcp-v2-field-guide.html)**

---

## What this covers

- **What actually changed in SDK v2** — the construction, transport, context, and lifecycle APIs that move, in a table you can act on.
- **A representative FastAPI-mounted port** — before/after, including the edges the general guidance misses.
- **A safe, staged migration protocol** — freeze, test, branch, stage, canary, cut over.
- **An interoperability test card** — discovery, schema, auth, authorization, execution, observability, recovery.
- **A release gate checklist** — the boxes to tick before promoting v2.

## Who it's for

- Teams operating Python MCP servers built with `FastMCP` / `mcp[cli]` 1.x.
- Agent builders connecting Claude, Codex, Cursor, or VS Code to real systems.
- Platform teams validating governed execution alongside a context, policy, or memory server.

## Scope

Written for teams running **Python** MCP servers on **Streamable HTTP**, especially mounted behind FastAPI. The **migration protocol** and **interoperability test card** are language-agnostic and apply to any MCP server (Python, TypeScript, Go, C#); the **code specifics** (imports, `MCPServer`, `streamable_http_app()`, the FastAPI mount) are Python + FastAPI. `stdio` / local servers don't use Streamable HTTP, so the transport and routing sections don't apply to them.

## How it was checked

The technical specifics in this guide were **verified against a live `mcp==2.0.0` install** at the time of writing — not paraphrased from a changelog. The items marked ✓ in the "what changed" table were run against the package directly.

That said: **this is a community-oriented implementation aid, not an official MCP project publication.** SDK behavior can change. Always confirm against the official sources before changing production systems:

- Python SDK — https://github.com/modelcontextprotocol/python-sdk
- v2 migration guide — https://py.sdk.modelcontextprotocol.io/migration/
- Specification (2026-07-28) — https://modelcontextprotocol.io/specification/2026-07-28

## License

This guide is released under **[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)** — free to share and adapt with attribution. Use it, fork it, translate it, hand it to your team.

## Feedback

Found something that's changed, or an edge this missed? Open an issue — corrections make the next version better.

---

*Maintained by the Conxt team. Conxt is an independent context & memory layer for AI agents.*
