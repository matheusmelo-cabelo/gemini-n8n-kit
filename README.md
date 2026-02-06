# Gemini n8n Kit

> 🚀 **The ultimate toolkit for orchestrating n8n workflows with Gemini CLI (Antigravity).**

This repository provides specialized **Skills** and **MCP Configurations** to turn your Gemini CLI into an expert n8n developer. It is inspired by the excellent work done for Claude by `czlonkowski`, but purely re-engineered for the Gemini ecosystem.

## 📦 What's Inside?

### 1. n8n Expert Skill (`/skills/n8n-expert`)
A native Gemini Skill that teaches the agent:
*   **Syntax Mastery:** No more broken `{{ $json... }}` expressions.
*   **Code Node Pro:** Generates perfect JavaScript/Python for data transformation.
*   **Workflow Patterns:** Knows how to build resilient webhooks, API integrations, and AI Agents.
*   **Validation:** Auto-detects common mistakes before you even run the workflow.

### 2. MCP Configuration (`/mcp-config`)
Plug-and-play configurations to connect Gemini CLI to your local or remote n8n instance via the Model Context Protocol (MCP).

## 🚀 Installation

### Prerequisites
*   **Gemini CLI** (Antigravity) installed.
*   **n8n** instance running (local or cloud).
*   **Supergateway** (optional, but recommended for easy HTTP tunneling).

### Step 1: Install the Skill
You can install the skill directly from this repository locally:

```bash
gemini skills install ./skills/n8n-expert --scope user
```

### Step 2: Connect n8n (MCP)
Connect your n8n instance so Gemini can "see" and "control" your workflows.

**Option A: Using Supergateway (Recommended)**
If you use `supergateway` to expose n8n:

```bash
gemini mcp add n8n-mcp "npx -y supergateway --streamableHttp https://localhost/mcp-server/http --header 'authorization:Bearer <YOUR_TOKEN>'" --trust
```

> **⚠️ Security Note:** The `--trust` flag allows the MCP server to execute tools on your behalf. Only use this flag if you fully trust the server and the network connection (e.g., localhost).

**Option B: Direct Connection**
If your n8n instance is running locally and exposes MCP directly (future support):

```bash
gemini mcp add n8n-local "node path/to/mcp-server.js"
```

## 🧠 How to Use

Once installed and reloaded (`/skills reload`), just talk to Gemini:

*   *"Create a workflow that listens to a Webhook and sends a message to Slack."*
*   *"Fix the expression error in this node."*
*   *"Analyze my active workflows and suggest optimizations."*

## 🤝 Contribution
Fork this repo, improve the skills, and open a PR! Let's build the best n8n AI tooling together.

---
*Adapted for Gemini CLI by matheus-cabelo. Original concept by czlonkowski.*
