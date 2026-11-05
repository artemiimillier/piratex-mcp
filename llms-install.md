# Installing the Piratex MCP server (for AI agents)

Piratex is a hosted remote MCP server. Nothing to install or build.

- URL: `https://piratex.ai/api/mcp`
- Transport: Streamable HTTP
- Auth: OAuth 2.1 (dynamic client registration). The user signs in on piratex.ai and presses "Allow". No API key needed.
- Fallback auth: API key from the user's piratex.ai account, sent as `Authorization: Bearer px_...`.

Client configs:

- Claude Code: `claude mcp add --transport http piratex https://piratex.ai/api/mcp`, then `/mcp` to sign in.
- Cursor (`~/.cursor/mcp.json`): `{"mcpServers": {"piratex": {"url": "https://piratex.ai/api/mcp"}}}`
- VS Code (`.vscode/mcp.json`): `{"servers": {"piratex": {"type": "http", "url": "https://piratex.ai/api/mcp"}}}`
- Claude (claude.ai / Desktop): Settings → Connectors → Add custom connector → the URL above.
- ChatGPT: developer mode → add custom MCP server → the URL above, OAuth.

After connecting, call `account` (free) to check the plan and credits, then `trending_now` for a niche.
Full docs: https://piratex.ai/en/mcp-server
