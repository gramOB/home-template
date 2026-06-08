# Home Template

This repository is a sanitized example of a personal security work workspace.

It is meant to show:
- the folder structure used for inbox triage, logs, queries, reports, and reference material
- the daily commands used to work the repo
- how Azure DevOps MCP integration is wired into the workflow

## Folder Layout

```
inbox.md                     general triage queue
security-misc-inbox.md       security misc items
soc-activity-inbox.md        SOC activity items

logs/                        daily activity logs
sprints/2026_XX/             sprint notes and task tracking
backlog/                     roadmap and archive notes
queries/                     KQL queries grouped by domain
reports/                     summaries, reviews, and status drafts
reference/                   setup guides and stable reference docs
azdo/                        exported query data and work item notes
```

## Common Commands

- `process inbox`
- `process security misc inbox`
- `process soc activity inbox`
- `run daily log`
- `run daily log for today MM/DD`
- `generate sprint review report`

## MCP Workflow

For implementation, go directly to:

- [reference/azure-devops-mcp-setup.md](/home/gob/home-template/reference/azure-devops-mcp-setup.md)

That guide tells you what to edit, where to place the config, and how to validate MCP is working.

Supporting files:

- [mcp.json](/home/gob/home-template/mcp.json) (sanitized config template)
- [reference/azure-devops-mcp-vscode-setup.md](/home/gob/home-template/reference/azure-devops-mcp-vscode-setup.md) (VS Code-specific notes)

Before using this template for a real workspace, replace the placeholder Azure DevOps org, project, team, area path, and iteration values with your own.

## MCP Setup Files Included

- `mcp.json` - sanitized MCP server configuration example
- `reference/azure-devops-mcp-setup.md` - full setup guide (PAT, server setup, verify, troubleshooting)
- `reference/azure-devops-mcp-vscode-setup.md` - VS Code-focused setup and profile config steps
