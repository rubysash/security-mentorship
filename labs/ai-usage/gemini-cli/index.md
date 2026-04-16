---
title: "Beginner Gemini CLI: AI-Powered Engineering"
date: 2026-04-04
description: "Install, configure, and use the Gemini CLI to plan projects, manage environments, and automate tasks like website screenshotting."
tags: ["ai-usage", "gemini-cli", "automation", "python", "cli"]
showTableOfContents: true
---

# Mastering the Gemini CLI: AI-Powered Engineering

## Objective
By the end of this lab, you will have installed the Gemini CLI, used it to architect a project plan, and developed a functional Python script to capture website screenshots—all directed from your terminal.

## Legal & Ethical Disclaimer
**FOR EDUCATIONAL USE ONLY.** The Gemini CLI is a powerful tool capable of modifying your filesystem and executing commands. Always review AI-generated code and shell commands before execution. Only use the screenshot script on websites you own or for which you have explicit permission to capture data.

## Prerequisites

Node is required for Gemini, but we are going to do other work with it, so install python too.

- **Node.js installed** (Required for npm): Download at [https://nodejs.org/](https://nodejs.org/).
- **A Google Account:** To authenticate your AI session.
- **Python 3 installed** (For the project portion): Download at [https://www.python.org/downloads/](https://www.python.org/downloads/).

### Authentication and Tier Options
The Gemini CLI offers two ways to connect. Your choice determines how your data is handled and what limits apply.

*   **Option 1: Gemini Advanced Subscription (No API Key Required)**
    If you have a paid Gemini Advanced subscription ($20/mo), the CLI can authenticate directly through your browser. 
    *   **Cost:** Flat $20/mo.  includes 2TB storage, and other parts of Google Ecosystem
    *   **Privacy:** Generally follows the consumer terms of service. Great for personal use and standard project work.

*   **Option 2: Google AI Studio (API Key)**
    The professional developer portal allows for fine-grained control over data and costs. Obtain your key at [https://aistudio.google.com](https://aistudio.google.com).

| Feature | Free Tier | Paid Tier (Pay-As-You-Go) |
| :--- | :--- | :--- |
| **Model Training** | **Yes.** Google uses your data to improve models. | **No.** Your data is never used for training. |
| **Human Review** | **Possible.** Data may be read by human annotators. | **No.** Enterprise-grade privacy protections. |
| **Cost** | $0 (Generous free limits). | Charged per 1M tokens (very inexpensive). |
| **Rate Limits** | Lower (e.g., 15 RPM for Pro). | Significantly higher for production use. |

**Important Security Verification:**
You can verify these policies and check current pricing at these official links:
- **Pricing & Tier Comparison:** [https://ai.google.dev/pricing](https://ai.google.dev/pricing)
- **Data Privacy & Usage Terms:** [https://ai.google.dev/gemini-api/terms#data-use](https://ai.google.dev/gemini-api/terms#data-use)

> **Pro Tip:** For any work involving proprietary code, sensitive security findings, or PII (Personally Identifiable Information), you MUST use the **Paid Tier** to ensure your data remains private and is not used for model training and then... you must trust that Google will keep it private (lol)

---

## Installation and Initial Setup

Install the Gemini CLI globally using npm:

```bash
npm install -g @google/gemini-cli@latest
```

### First Time Tests (The Sandbox)
Before working on your real files, enter the sandbox mode to explore capabilities without risk:

```bash
gemini --sandbox
```

---

## Project Workflow: The Website Screenshot Tool
We will use Gemini to help us plan and build a tool that takes a full-page screenshot of any URL.

### Create the Workspace (The Environment)
In this workflow, the project folder **is** the virtual environment. This keeps your tools and project files in a single, isolated unit.

```bash
# Create the environment folder
python3 -m venv site-screenshot

# Enter the workspace
cd site-screenshot
```

### Activate and Plan
Now, activate your environment and ask Gemini to design the architecture.

```bash
# Activate (Linux/Pi/WSL)
source bin/activate  

# Activate (Windows PowerShell)
# .\Scripts\Activate.ps1
```

### Run Gemini

In this folder, type:  `gemini` to start the gemini cli.

After it loads, issue a command and start working with it:

**Command:**
```bash
I want to build a tool that takes a screenshot of a website. Create a comprehensive project plan including the best language, required libraries, and file structure. Output this plan in Markdown format and save it to project-plan.md.   This project will be in Python3 on my Raspberry Pi 4 which is running noobs.
```

### Establish Project Memory (GEMINI.md)
Create a local `GEMINI.md` file to set specific engineering standards for the AI agent to follow within this workspace.

**Command:**
```bash
Based on project-plan.md, create a GEMINI.md file for this repository. Include rules for using Playwright, a mandate for clean variable naming, and a requirement to include error handling in every script.
```

### Direct the Coding
Tell Gemini to write the actual code based on the established plan and memory.

**Command:**
```bash
Write a Python script named screenshot.py based on our project-plan.md. Use Playwright to take a full-page screenshot of a URL passed as a command-line argument. Ensure it follows the rules in our local GEMINI.md.
```

### Project Structure
Your workspace should now look like this. Note that the standard virtual environment files (`bin`, `lib`, `pyvenv.cfg`) live alongside your project files:

```text
site-screenshot/
├── bin/                    # Venv binaries (Scripts/ on Windows)
├── lib/                    # Venv library packages
├── pyvenv.cfg              # Venv configuration
├── GEMINI.md               # Project-specific rules and context
├── project-plan.md         # The AI-generated technical blueprint
└── screenshot.py           # The functional Python script
```

### Execution
Install the dependencies and run your tool:

```bash
python3 -m pip install playwright
playwright install
python3 screenshot.py [https://google.com](https://google.com)
```

---

## CLI Memory
The Gemini CLI uses `GEMINI.md` files to remember your rules and preferences. You can edit these at different levels:

*   **Global Memory:** `~/.gemini/GEMINI.md` (Rules for every project).
*   **Project Root:** `./GEMINI.md` (Rules for the current repository).
*   **Subdirectory:** `./src/GEMINI.md` (Rules specific to a folder).

### Useful Memory Commands
*   `/memory show` - View current memory.
*   `/memory reload` - Refresh rules after editing a file.

### Session Management vs. Version Control
It is critical to understand the difference between the CLI's internal history and professional version control (Git).

*   **Internal Checkpointing (`/rewind` & `/restore`):** Before the AI modifies a file, it creates a "checkpoint" in a hidden shadow repository. Using `/rewind` allows you to revert the conversation state **and** any file changes made by the AI.
    *   **Limitation:** It **cannot** revert manual edits you made yourself or changes made via the `!` shell tool.
*   **Version Control (Git):** You still need Git for professional work. Git tracks *every* change (manual or AI) and is required for collaboration and backups.

> **Pro Tip:** Think of `/rewind` as an "AI Undo" button and **Git** as your permanent project "History Book." Always link your project to a GitHub repository once you have a working script. Review the **Git Foundations: Version Control** lab to set this up.

---

## Advanced CLI Reference
Use these slash commands during an interactive session (`gemini`) to manage the agent:

| Command | Description |
|---------|-------------|
| `/tools` | List available tools the agent can use. |
| `/settings` | View or change AI configuration. |
| `/help` | Show help for all commands. |
| `/quit` | Exit the session. |
| `!ls -la` | Run any bash command by prefixing with `!`. |

### Session Management
Resume exactly where you left off:
*   `gemini -r "latest"` - Resume the most recent session.
*   `gemini --list-sessions` - See your history.
*   `/rewind` - Step back if the AI makes a mistake.

### Model Selection
Switch models for different tasks:
*   `gemini -m gemini-3.1-pro-preview` - Use the latest reasoning model.
*   `gemini extensions` - List active model extensions.

---

## Learning Resources
*   **Official CLI Reference:** [https://geminicli.com/docs/cli/cli-reference/](https://geminicli.com/docs/cli/cli-reference/)
*   **Skills Getting Started:** [https://geminicli.com/docs/cli/tutorials/skills-getting-started/](https://geminicli.com/docs/cli/tutorials/skills-getting-started/)
*   **Google AI Studio:** [https://aistudio.google.com](https://aistudio.google.com)

---

## What You Learned
*   **CLI Integration:** Running AI agents natively in your terminal.
*   **Architectural Planning:** Using AI to design project structures before coding.
*   **Environment Management:** Setting up a workspace where the project folder **is** the virtual environment.
*   **Contextual Memory:** Using `GEMINI.md` to persist engineering standards.
