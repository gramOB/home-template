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

The `reference/` folder includes generic Azure DevOps MCP setup notes.
The `CLAUDE.md` file contains the operating instructions and work item conventions.

Before using this template for a real workspace, replace the placeholder Azure DevOps org, project, team, area path, and iteration values with your own.
