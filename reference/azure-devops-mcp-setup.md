# Azure DevOps MCP Setup

This is a full, sanitized setup flow for Azure DevOps MCP.

All values in this repository are placeholders by design.

## Prerequisites

- Node.js installed
- `npx` available in shell
- VS Code with Copilot Chat enabled
- Azure DevOps account access

## 1. Choose an authentication pattern

Use one of these options:

- PAT prompt at runtime: recommended for a shared template, no secret stored in repo
- Interactive auth: good when your environment supports sign-in flows

This template keeps both options available in [mcp.json](/home/gob/home-template/mcp.json).

## 2. Create a PAT (if using PAT mode)

1. In Azure DevOps, open user settings and then Personal Access Tokens.
2. Create a PAT with a clear name and short expiration.
3. Grant minimum scopes needed:
- Work Items, Read and Write
- Project and Team, Read
- Wiki, Read and Write
4. Copy the PAT once, then store it in your password manager.

## 3. Edit the sanitized MCP config

Open [mcp.json](/home/gob/home-template/mcp.json) and replace placeholders:

- `YOUR_ORG` with your Azure DevOps org URL segment
- Optional server name if you prefer a custom key
- Capability list after `-d` if you want fewer tools

Capabilities in this template:

- `core` for org, project, team, identity access
- `work` for team iterations and capacity
- `work-items` for PBIs, tasks, bugs, queries, comments, revisions
- `wiki` for wiki read and write

## 4. Copy mcp.json into VS Code profile config

Common remote/container path:

```text
~/.vscode-server/data/User/profiles/<profile-id>/mcp.json
```

If you do not use custom profiles, place it in the default user-level MCP config path for your VS Code environment.

## 5. Reload VS Code and validate

1. Run `Developer: Reload Window`.
2. Open Copilot Chat.
3. Test with read-only prompts first:
- list my assigned work items
- show current team iteration
- get work item 12345
4. Confirm MCP tool calls appear and return results.

## 6. Optional: multi-org setup

Add multiple entries under `servers` in [mcp.json](/home/gob/home-template/mcp.json):

- `azure-devops-primary`
- `azure-devops-secondary`

Each entry can target a different org and auth input.

## 7. Security checklist

- Never commit real PAT values
- Keep placeholders in repository files
- Use runtime prompt inputs or local-only secret injection
- Rotate PATs and remove stale credentials
- Remove unused capability groups

## 8. Troubleshooting checklist

- `npx` not found: install Node.js and restart shell
- MCP server fails to start: validate JSON format in [mcp.json](/home/gob/home-template/mcp.json)
- Auth errors: verify org name and PAT scope, then regenerate token
- No tools show in Copilot: reload VS Code and check MCP logs
- Partial tool availability: reduce to `core` + `work-items`, then add groups back
