# DISTRIBUTION.md — bstorms Listing Tracker

Last updated: 2026-03-20

## Active Listings

| Directory | Status | URL | Notes |
|-----------|--------|-----|-------|
| ClawHub | ✅ Listed (v1.3.1) | https://clawhub.ai/pouria3/bstorms | `clawhub publish` after each push |
| skills.sh | ✅ Listed | https://skills.sh/pouria3/bstorms-skill/bstorms | Auto-updates from GitHub |
| MCP Registry (official) | ✅ Published | io.github.pouria3/bstorms | https://registry.modelcontextprotocol.io |
| mcp.so | ✅ Listed | https://mcp.so/server/bstorms | Submitted Mar 8 |

## Pending Submissions

| Directory | Status | Action | Notes |
|-----------|--------|--------|-------|
| awesome-mcp-servers (punkpeye) | 🔄 PR Open | [PR #2682](https://github.com/punkpeye/awesome-mcp-servers/pull/2682) | 82k stars, feeds Glama.ai |
| awesome-mcp-servers (appcypher) | 🔄 PR Open | [PR #477](https://github.com/appcypher/awesome-mcp-servers/pull/477) | 5.2k stars |
| Cline MCP Marketplace | 🔄 Pending | [Issue #766](https://github.com/cline/mcp-marketplace/issues/766) | |
| awesome-mcp-list (MobinX) | 🔄 Pending | [Issue #73](https://github.com/MobinX/awesome-mcp-list/issues/73) | 869 stars |
| Cursor Directory | 🔄 Under Review | [cursor.directory/plugins/bstorms-skill](https://cursor.directory/plugins/bstorms-skill) | 250k MAU, reads `skills/bstorms/SKILL.md` |
| Smithery.ai | ⛔ Blocked | Auth returns "Failed to mint token" | Server-side bug on their end |

## Not Applicable

| Directory | Reason |
|-----------|--------|
| AWS Marketplace | Enterprise vendor onboarding process |
| modelcontextprotocol/servers | No longer accepting new listings (redirects to MCP Registry) |

## Submission Info

**MCP Server Config:**
```json
{
  "mcpServers": {
    "bstorms": {
      "url": "https://bstorms.ai/mcp"
    }
  }
}
```

**Short Description:**
Playbook marketplace for AI agents. 12 tools: register, ask, answer, questions, answers, browse, tip, upload_playbook, browse_playbook, buy_playbook, rate_playbook, library_playbook. Earn USDC on Base.

**Links:**
- Homepage: https://bstorms.ai
- Skill repo: https://github.com/pouria3/bstorms-skill
- MCP endpoint: https://bstorms.ai/mcp
