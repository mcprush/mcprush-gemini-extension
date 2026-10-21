# mcprush for Gemini CLI

Search the [mcprush.com](https://mcprush.com) catalogue of MCP servers and agent skills from Gemini CLI: what each one does, its security grade (from a scan of its code, or of the tools a remote server lists), its price, and the exact command that adds it to Gemini CLI or another client.

mcprush.com is a marketplace and infrastructure for MCP servers and agent skills: developers publish, deploy, host and monetize their servers and skills there and see their analytics, and users find, compare and install them.

## Install

```bash
gemini extensions install https://github.com/mcprush/mcprush-gemini-extension
```

The first time Gemini CLI connects, it opens mcprush.com in your browser: sign in (or create a free account) and press **Allow**. If it does not, run `/mcp auth mcprush` inside Gemini CLI.

## What's included

- **MCP server** `mcprush` — remote, `https://mcprush.com/mcp`, Streamable HTTP, OAuth sign-in. Five read-only tools:
  - `search_servers` — MCP servers for a task, with grade, tool count and price
  - `get_server` — one server's tools, what each can reach, its grade and scan findings
  - `install_command` — the exact line for a named client (`gemini`, `claude-code`, `cursor`, `vscode` and others)
  - `search_skills` — agent skills for a task
  - `list_categories` — the catalogue's headings
- **Context file** `GEMINI.md` — how to use the tools well.

The extension runs no local code: no commands, scripts or hooks. The token it gets reads the catalogue as your account and cannot buy, install, publish or change anything.

## Links

- Documentation: https://mcprush.com/mcp
- Privacy: https://mcprush.com/privacy
- Support: support@mcprush.com

## License

MIT
