# Home Template

## Writing style

- Keep prose concise and factual.
- Prefer flat structure over nested bullets.
- Use plain ASCII unless a file already depends on something else.

## Azure DevOps

- Org: `YOUR_ORG`
- Project: `YOUR_PROJECT`
- Team: `YOUR_TEAM`
- Area: `YOUR_AREA_PATH`
- Sprint format: `YOUR_PROJECT\YOUR_TEAM\YYYY\YYYY_MM`
- MCP prefix: `mcp__azure-devops__`

### Work Item Conventions

- Title format for security PBIs: `Security - <description> (added mm/dd/yy)`
- Done state: PBIs use the team's release-ready state, tasks use `Done`
- Merge new tags into existing tags, never overwrite blindly

### Creating Work Items

When creating work items, fill in the required fields for your workspace and check the current values before updating existing items.

### Workspace Files

- `inbox.md` for general triage
- `security-misc-inbox.md` for security misc items
- `soc-activity-inbox.md` for SOC activity items
- `logs/` for daily activity logs
- `reports/` for summaries and reviews
- `reference/` for stable setup docs
- `queries/` for KQL and WIQL

### Workflow Notes

- `process inbox` triages the main inbox file.
- `process security misc inbox` triages the security misc inbox.
- `process soc activity inbox` triages the SOC inbox.
- `run daily log` builds a daily activity report from work item history.
