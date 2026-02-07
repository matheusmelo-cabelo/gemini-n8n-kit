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
Connect your n8n instance so Gemini can "see" and "control" your workflows. This kit is now optimized for the **official n8n MCP protocol**.

**Option A: Using Standard SSE (Recommended)**
This is the official transport protocol for the n8n MCP Client.

```bash
gemini mcp add n8n-mcp "http://localhost:3000/mcp" --header "Authorization: Bearer <YOUR_TOKEN>" --trust
```

**Option B: Using npx (Quick Local Setup)**
If you haven't deployed the server yet:

```bash
gemini mcp add n8n-mcp "npx -y n8n-mcp" --env "MCP_MODE=stdio" --env "N8N_API_URL=http://localhost:5678" --env "N8N_API_KEY=<YOUR_N8N_KEY>" --trust
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
