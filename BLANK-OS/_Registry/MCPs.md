# MCPs

Model Context Protocol servers configured for this workspace.
Config lives in `.claude/settings.json` under `mcpServers`.

---

## Configured MCPs

### GitHub
- **Purpose:** Read/write repos, issues, PRs, code search
- **Package:** `@github/github-mcp-server`
- **Setup:**
  1. Go to https://github.com/settings/tokens → Generate new token (classic)
  2. Scopes: `repo`, `read:org`, `read:user`
  3. Add to `.claude/settings.json`:
     ```json
     "github": {
       "command": "npx",
       "args": ["-y", "@github/github-mcp-server"],
       "env": { "GITHUB_PERSONAL_ACCESS_TOKEN": "YOUR_TOKEN_HERE" }
     }
     ```

### Notion
- **Purpose:** Read/write Notion pages and databases
- **Transport:** HTTP (hosted by Notion)
- **Setup:** Run `claude mcp add --transport http notion https://mcp.notion.com/mcp` → authenticates via browser

### Linear
- **Purpose:** Read/write issues, projects, and cycles
- **Transport:** HTTP (OAuth via Linear)
- **Setup:** Run `claude mcp add --transport http linear https://mcp.linear.app/sse` → authenticates via browser

### Slack
- **Purpose:** Read channels, send messages, search Slack
- **Package:** `@modelcontextprotocol/server-slack`
- **Setup:**
  1. Go to https://api.slack.com/apps → Create New App
  2. Add OAuth scopes: `channels:read`, `channels:history`, `chat:write`, `users:read`
  3. Install to workspace → copy Bot User OAuth Token
  4. Add to `.claude/settings.json`:
     ```json
     "slack": {
       "command": "npx",
       "args": ["-y", "@modelcontextprotocol/server-slack"],
       "env": {
         "SLACK_BOT_TOKEN": "xoxb-...",
         "SLACK_TEAM_ID": "TXXXXXXX"
       }
     }
     ```

---

## Verifying MCPs Work

After adding tokens, restart Claude Code. Run `/mcp` to see connected servers.

---

## Common Issues

- **"Cannot find module"** — Run `npm install -g <package>` globally first
- **"Unauthorized"** — Token is wrong or expired, regenerate it
- **Notion pages not found** — Make sure you've shared the page with your integration
