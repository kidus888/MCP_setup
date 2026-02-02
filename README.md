1. What I Did

Created a .github/copilot-instructions.md file to define custom rules and guidance for the AI agent.

Configured the MCP server in .vscode/mcp.json to connect VS Code with Tenx MCP.

Added required headers to ensure device and coding tool identification.

Authenticated the MCP server using GitHub OAuth.

Verified tool availability through Copilot Chat in agent mode.

2. What Worked

Updating VS Code to the latest version resolved compatibility issues.

Installing both GitHub Copilot extensions was essential for MCP support.

Properly setting headers (X-Device, X-Coding-Tool) enabled successful server communication.

Using copilot-instructions.md effectively guided the AI agent’s responses and behavior.

Authentication flow via GitHub worked smoothly once permissions were granted.

3. What Didn’t Work

MCP server did not appear initially due to missing mcp.json.

Authentication failed when headers were missing or incorrectly formatted.

Tools were not visible until Copilot Chat was switched to Agent mode.

Restarting VS Code was required after configuration changes for them to take effect.

Troubleshooting steps taken:

Verified folder structure (.github and .vscode)

Rechecked JSON syntax

Restarted VS Code

Re-authenticated GitHub access

4. Insights Gained

Rules defined in copilot-instructions.md significantly influence how the AI agent behaves.

Clear instructions help align the AI’s responses with:

Developer intent

Expected reasoning style

Project-specific standards

MCP acts as a bridge that enables richer, tool-aware interactions beyond standard chat.

Well-defined rules reduce ambiguity, improve consistency, and make the AI feel more like a focused collaborator rather than a generic assistant.
