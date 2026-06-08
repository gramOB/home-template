# Azure DevOps MCP Setup

This document explains the generic pattern for wiring Azure DevOps MCP into a workspace.

## What to configure

- Azure DevOps org
- project and team
- area path and sprint path
- the MCP prefix used by the agent tools

## What the workflow does

- queries work items by date or iteration
- reads revisions and comments for context
- writes daily logs and sprint notes from the results

## Example

Replace the placeholder values below with your own.

```text
Org: YOUR_ORG
Project: YOUR_PROJECT
Team: YOUR_TEAM
Area: YOUR_AREA_PATH
```
