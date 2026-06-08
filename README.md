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

## How Work Gets Processed

This workspace is designed around three inbox files so different kinds of work do not get mixed together.

### 1) General intake: `inbox.md`

Use this file for new backlog candidates, larger efforts, or items that still need scoping.

When you run `process inbox`, the agent typically:
- reads all unprocessed lines in `inbox.md`
- decides whether each item should become a new backlog work item or a sprint-level item
- creates or updates work items in Azure DevOps
- links items to the correct parent/iteration based on your conventions
- marks lines as processed in `inbox.md`

### 2) Sprint misc stream: `security-misc-inbox.md`

Use this file for smaller, unplanned security tasks that belong in a sprint misc bucket.

When you run `process security misc inbox`, the agent usually:
- creates tasks under the sprint misc work item
- keeps each entry small and execution-oriented
- marks entries processed after task creation

This keeps ad hoc work visible without polluting long-term backlog planning.

### 3) SOC stream: `soc-activity-inbox.md`

Use this file for SOC investigations, alert triage, and security operations follow-ups.

When you run `process soc activity inbox`, the agent:
- converts SOC notes into actionable tasks or tracked work
- preserves operational context in titles/descriptions
- marks entries processed once captured in Azure DevOps

### 4) Daily execution history: `logs/`

After work items are updated through the day, run `run daily log`.

The log workflow normally:
- queries item changes for the date
- reads comments and revisions for meaningful progress context
- writes a date-stamped file in `logs/`

This gives you an auditable daily narrative instead of only a raw board view.

### 5) Planning and reporting outputs

- `backlog/roadmap.md` keeps medium and long-range planning
- `sprints/2026_XX/misc-security.md` tracks sprint-level misc execution notes
- `reports/` stores biweekly, monthly, and sprint review summaries

Together, the workflow is: capture in the right inbox, process into tracked work, log daily progress, then roll up into reports.

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
