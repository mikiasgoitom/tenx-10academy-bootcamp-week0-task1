# Understanding MCP and the Rules

## What is MCP (Model Context Protocol)?

The [Model Context Protocol (MCP)](https://modelcontextprotocol.io/introduction) is a standard that allows AI models (like GitHub Copilot or Claude) to interact with external tools, data, and environments in a standardized way.

In this workspace, the MCP configuration is defined in `[.vscode/mcp.json](../.vscode/mcp.json)`.

### How it Works in This Workspace

1.  **Configuration (`.vscode/mcp.json`)**:
    - This file defines a "server" named `tenxfeedbackanalytics`.
    - It points to an external proxy URL: `https://mcppulse.10academy.org/proxy`.
    - This server exposes specific "tools" to the AI agent.

2.  **The Tools**:
    The connected MCP server provides two critical tools that the AI _must_ use:
    - `log_passage_time_trigger`: Tracks the start of a user interaction.
    - `log_performance_outlier_trigger`: Tracks specific performance metrics (success/failure patterns).

3.  **The "Rules" Files**:
    - Standard location: `[.github/copilot-instructions.md](../.github/copilot-instructions.md)`
    - **Purpose**: This markdown file is essentially a "System Prompt" that is injected into the AI's context.
    - **Mechanism**: When you type a query, the AI reads this file first. The file instructs the AI _that it must_ call the MCP tools defined above before doing anything else. Without these instructions, the AI would not know the tools exist or that it is required to use them.

## Where are the Rules Set?

- **Location**: `[.github/copilot-instructions.md](../.github/copilot-instructions.md)`
- **Execution**: These are not "run" like a script. They are "read" by the AI. The AI then "executes" the logic by deciding to call the functions (tools) described in the text.

## Summary of Changes in Recommendation

The proposed changes in `[.github/copilot-instructions_proposed.md](../.github/copilot-instructions_proposed.md)` shift the focus from **Passive Compliance** to **Active Engineering**.

| Feature          | Original (`copilot-instructions.md`) | Proposed (`copilot-instructions_proposed.md`)               |
| :--------------- | :----------------------------------- | :---------------------------------------------------------- |
| **Primary Goal** | Ensure telemetry tools are called.   | Solve tasks efficiently (while still calling tools).        |
| **Workflow**     | Wait for triggers -> Process loop.   | **OODA Loop** (Observe, Orient, Decide, Act) + Triggers.    |
| **Agent Role**   | Passive responder.                   | **Senior Software Engineer (10x)**.                         |
| **File Safety**  | Not defined.                         | **Strict Gating**: No reading/writing without verification. |
| **UX**           | Standard text.                       | **Clickable Markdown Links** for all file paths.            |

The proposed version retains all the critical telemetry requirements but wraps them in a professional engineering framework to prevent common AI errors (like hallucinating files or writing incomplete code).
