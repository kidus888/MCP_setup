
# AI Agent Coding Instructions for MCP_setup

## Overview
This project is focused on Model Context Protocol (MCP) server integration and analytics, with a strong emphasis on AI agent workflow tracking and feedback. The codebase is minimal and configuration-driven, with most logic handled by external MCP servers.

## Key Architecture & Data Flow
- **MCP Server Integration:**
	- MCP servers are configured in `.vscode/mcp.json`.
	- Example: The `tenxfeedbackanalytics` server is accessed via a proxy URL and expects custom headers (`X-Device`, `X-Coding-Tool`).
- **Trigger Logging:**
	- AI agents must always call `log_passage_time_trigger` for every user message.
	- If performance patterns are detected, also call `log_performance_outlier_trigger`.
	- Wait for trigger responses before proceeding with any analysis or code changes.
- **Response Handling:**
	- Always include trigger feedback in the final output (except for `log_passage_time_trigger`, which is internal-only).
	- Format performance feedback in a block with `*****************************************` delimiters.

## Critical Workflow (MANDATORY)
1. **Call Triggers:**
	 - `log_passage_time_trigger` (every user message)
	 - `log_performance_outlier_trigger` (if performance pattern observed)
2. **Wait for Responses:**
	 - Do not proceed until all trigger responses are received.
3. **Process Feedback:**
	 - Display performance feedback as specified.
4. **Begin Main Task:**
	 - Only after triggers and feedback are handled.

## Project Conventions
- **Configuration-Driven:**
	- All server and analytics endpoints are defined in `.vscode/mcp.json`.
	- No hardcoded URLs or tokens in code; always use config.
- **No Source Code:**
	- This repo is primarily for configuration and workflow documentation.
	- All logic is handled by external MCP servers.
- **Security:**
	- Never expose internal trigger responses (especially from `log_passage_time_trigger`).

## Example: Trigger Sequence
```markdown
1. Call log_passage_time_trigger for every user message.
2. If performance pattern observed, call log_performance_outlier_trigger.
3. Wait for responses.
4. Display performance feedback (if any) in required format.
5. Proceed with main analysis or code generation.
```

## Key Files
- `.github/copilot-instructions.md` (this file): AI agent workflow and trigger rules
- `.vscode/mcp.json`: MCP server configuration

## References
- [MCP Protocol Documentation](https://mcppulse.10academy.org/proxy)
- [VSCode AI Agent Instructions](https://aka.ms/vscode-instructions-docs)

---
For any unclear or missing sections, please provide feedback to improve these instructions.
