# TenX Agentic Dev Challenge: AI Workflow Optimization

Welcome to the **TenX Agentic Development** submission repository. This project demonstrates the configuration of a high-performance **Autonomous Coding Agent** using the Model Context Protocol (MCP) and advanced system prompt engineering.

This environment is configured to transform a standard AI assistant into a proactive **"10x Engineer"** that follows strict operational security (OpSec) and cognitive workflows (OODA Loop).

## 📂 Repository Structure

| File/Directory | Description |
| :--- | :--- |
| `[.github/copilot-instructions.md](.github/copilot-instructions.md)` | **Active Agent Rules**. The "System Prompt" that governs the AI's behavior, workflow, and tool usage. |
| `[.vscode/mcp.json](.vscode/mcp.json)` | **MCP Configuration**. Defines the connection to the `tenxfeedbackanalytics` server for telemetry. |
| `[docs/implementation-report.md](docs/implementation-report.md)` | **Task Report**. Detailed breakdown of the changes made, challenges faced, and insights gained (Task 3). |
| `[docs/architecture-mcp.md](docs/architecture-mcp.md)` | **Technical Guide**. Explains how the Model Context Protocol integrates with the agent. |

## 🚀 Setup & Configuration

### Prerequisites
*   **VS Code** or **Cursor** IDE.
*   **GitHub Copilot** or compatible AI Assistant.
*   **Node.js** (for MCP server operations, if running locally).

### 1. Environment Configuration
The project relies on the **Model Context Protocol (MCP)** to track "AI Fluency".
*   Ensure the `.vscode/mcp.json` file is present in your root directory.
*   This file connects the agent to the remote proxy: `https://mcppulse.10academy.org/proxy`.

### 2. Agent Rules (The "10x Engineer" Profile)
The core logic resides in `[.github/copilot-instructions.md](.github/copilot-instructions.md)`. This file enforces:
1.  **Mandatory Telemetry**: Calling `log_passage_time_trigger` before any analysis.
2.  **Epistemic Humility**: "Verify before you act" (prevents file hallucinations).
3.  **The OODA Loop**: A strict cognitive cycle:
    *   **Observe**: List directories/files.
    *   **Orient**: Read context.
    *   **Decide**: Plan the change.
    *   **Act**: Execute code edits.

## 🛠️ Usage

When interacting with the AI in this workspace, the agent will automatically:
1.  **Acknowledge Constraints**: It will likely start responses by confirming trigger logs.
2.  **Plan First**: It will provide a "Plan" or "Strategy" section before writing code.
3.  **Use Links**: All file references will be clickable Markdown links.

## 📄 Documentation

For a deeper understanding of the work performed during this challenge:
*   **[Implementation Report](docs/implementation-report.md)**: Configuring the "10x Engineer" workflow.
*   **[MCP Architecture](docs/architecture-mcp.md)**: How the telemetry pipeline works.

## 🤝 Context
**Program**: Agentic Development Bootcamp (Week 0)
**Collaboration**: 10 Academy & Tenacious Intelligence (TenX)
