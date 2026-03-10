# Copilot Agents & Git Integration Guide

This document explains how to define **Copilot agents** in VS Code using `copilot-agents.json` and how to **trigger them automatically on Git commits** using hooks and scripts.

---

## 1️⃣ Defining Agents in `copilot-agents.json`

Agents are defined in JSON and describe their **purpose, tools, system prompts, and predefined prompts**.

Example: **Java Full Dev Workflow Agent**

```json
{
  "agents": [
    {
      "name": "Java Full Dev Workflow",
      "description": "End-to-end Java Dev workflow: debugging, architecture, DB, logging, testing, security",
      "systemPrompt": "Analyze provided Java files and give actionable recommendations.",
      "tools": ["codebase", "terminal", "problems", "clipboard", "files"],
      "predefinedPrompts": [
        "Perform a full development workflow on this Java module: analyze bugs, optimize code, suggest tests and security improvements."
      ]
    }
  ]
}