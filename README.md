# browser-mcp

Shared browser automation library for CPC MCP servers — chromiumoxide + CDP wrappers used by the `hands` server.

## What it does

Provides a pure-Rust browser automation layer over Chrome DevTools Protocol (CDP) via [chromiumoxide](https://github.com/mattsse/chromiumoxide). Used as a shared internal crate by the `hands` MCP server in the CPC stack.

## Key features

- **Pure Rust CDP** — no Python, no Node.js, no Playwright
- **chromiumoxide** backend — async, tokio-runtime
- **MCP-ready** — designed for stdio JSON-RPC 2.0 MCP servers
- **Vision support** — screenshot burst, clickable extraction, page metrics
- **Form automation** — field discovery, fill, submit
- **Cookie management** — get/set/clear

## Exposed capabilities

| Module | Purpose |
|--------|---------|
| `browser` | Launch/close browser, navigate, click, type, screenshot, wait |
| `tools` | MCP tool dispatch layer |
| `types` | Shared request/response types |
| `planner` | High-level action planner |

## Part of the CPC ecosystem

This crate is a component of **CPC (Cognitive Performance Computing)** — a multi-agent AI orchestration platform built on ~460 MCP tools across 13 servers.

| Repo | Purpose |
|------|---------|
| [hands](https://github.com/josephwander-arch/hands) | Browser + UI automation MCP server (consumes this crate) |
| [cpc-paths](https://github.com/josephwander-arch/cpc-paths) | Portable path discovery for CPC servers |

## Usage

This is an internal shared library crate. It is not published to crates.io. Consume it as a git dependency in your `Cargo.toml`:

```toml
[dependencies]
browser-mcp = { git = "https://github.com/josephwander-arch/browser-mcp", tag = "v0.1.0" }
```

## Versioning

- v0.1.x — initial release, Windows verified

## License

Apache-2.0
