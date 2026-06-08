# Azure DevOps MCP VS Code Setup

Use this guide to wire Azure DevOps MCP into VS Code with Copilot Chat.

## 1. Install runtime dependency

Make sure Node.js is installed and `npx` works.

## 2. Start from the sanitized template config

This repository includes [mcp.json](/home/gob/home-template/mcp.json) at the root.

Copy it to your VS Code profile MCP config path and keep this repository version sanitized.

Typical remote path:

```text
~/.vscode-server/data/User/profiles/<profile-id>/mcp.json
```

## 3. Update placeholders

In `mcp.json` replace:
- `YOUR_ORG` with your Azure DevOps org
- optional server name with your preferred naming

Leave credentials as prompt-based input or local-only secret source.

Do not hardcode PAT values in repository files.

## 4. Reload VS Code

Open command palette and run:

```text
Developer: Reload Window
```

## 5. Validate with a simple prompt

Try prompts like:
- Show my assigned work items
- List current sprint iterations
- Get details for work item 12345

If MCP is configured correctly, Copilot will call Azure DevOps tools directly.

## 6. Minimal smoke test sequence

Run these in order:

1. Read only test: list current sprint iterations
2. Read only test: show assigned work items
3. Single-item test: get work item details by ID

Only after those pass should you run write actions.

## 7. Troubleshooting

- Invalid config errors usually mean malformed JSON.
- Auth errors usually mean PAT issue or tenant mismatch.
- No tool calls usually means MCP server failed to start.

When debugging, temporarily reduce capabilities to `core` and `work-items`, then add others back.
