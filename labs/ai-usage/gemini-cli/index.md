---
title: "Beginner Gemini CLI: AI-Powered Engineering"
date: 2026-04-04
description: "Install, configure, and use the Gemini CLI to plan projects, manage environments, and automate tasks like website screenshotting."
tags: ["ai-usage", "gemini-cli", "automation", "python", "cli"]
showTableOfContents: true
---

# Gemini CLI: Basic Python Use Example

## Objective
By the end of this lab, you will have installed the Gemini CLI, used it to architect a project plan, and developed a functional Python script to capture website screenshots—all directed from your terminal.

**Note** you need a Google Account To authenticate your AI session.


## Checklist

Here is the TLDR version of what we are going to do.

- Install Prequisites
- Setup python Environment
- Install gemini-cli
- Authenticate
- /init
- Create a Project Plan Using Gemini
- Work with Gemini to Execute the Plan


## Install Prerequisites

Node is required for Gemini, but we are going to do other work with it, so we'll install python too.

- **Node.js installed** (Required for npm): Download at [https://nodejs.org/](https://nodejs.org/).
- **Python 3 installed** (For the project portion): Download at [https://www.python.org/downloads/](https://www.python.org/downloads/).  I suggest 3.13 because 3.14 does not have full support yet.

---

## Python Environment

In this lab we are going to use python to capture a screenshoot of a site.   To do that, we need a working environment for our python files, and then we'll use gemini to work with those files.

We'll use the `venv` module to create the virtual environment called `site-screenshot` that stores our scripts and modules for this program.

```bash
# Create the environment folder
python3 -m venv site-screenshot

# Enter the workspace
cd site-screenshot
```

### Activate and Plan
Now, activate your environment so the modules you are instructed to install will be contained.

```bash
# Activate if (Linux/Pi/WSL)
source bin/activate  

# Activate if (Windows PowerShell)
Scripts\Activate
```

Your CLI will change to `(site-screenshot)`.    This is the **python** venv, and it's ready to run `gemini` cli on it.
---

## Install gemini-cli

If you have node installed, you can can install gemini-cli like this:

```bash
npm install -g @google/gemini-cli@latest
```


---



## Run Gemini

In this folder, type:  `gemini` to start the gemini cli.   It will ask for authorization before you can continue.

## Authenticate

This is pretty straight forward.  Your free google account will allow basic work.   You can purchase a subscription from [https://one.google.com/about/plans](https://one.google.com/about/plans) for about $21 a month for additional usage beyond the free tier.

## /init

typing `/init` in the cli will create a filed called "GEMINI.md" that contains the basic instructions for your project.  You can edit this and fine tune how the AI responds, thinks, and prioritizes and more.

You can also create a `.geminiignore` file to tell gemini what to ignore.    Just list the files and directories like you would to ignore, using the same format as you might a `.gitignore`.

The initial `/init` will create blank or generic files and you will need to edit them to your specific project needs.      `GEMINI.md` files are folder and sub folder specific, but also you can have a main `GEMINI.md` file for everything you do.   Each folder and subfolder can have specific gemini files as needed.

## Create a Project Plan

If you try to ask gemini to boil the ocean, it will try.   However, if you spell it out exactly what you want it to do, it will perform much better for you.     I call these "Project Plans".   List out what you want the create, how it will work, limitations, how it looks, etc.    The more details you put into your project plan by thinking ahead - the better results you will get when you ask gemini to help you execute the plan.

At a bare minimum, I would list the following:

- Objectives
- Limits
- Examples
- Input
- Exact Output
- Reference Material
- GUI Design

You get the idea - create a well thought out plan.     You can (and should) use gemini to help create your project plan.   

**Example Prompt:**
```bash
I want to build a tool that takes a screenshot of a website. Create a comprehensive project plan for python 3.13 on debian, required libraries, and suggested file structure. Output this plan in a single block of markdown code and save it to project-plan.md.   Input will be a URL, and the output will be a screenshot of that URL saved to the /screenshots/ directory.   The gui will use pyqt that prompts for the URL and has a "capture" button.   We want modular design so that maintenance is easy.  For example, gui.py, main.py, url-grabber.py, logger.py and config.py
```

This is an example and how I start most of my projects.   THen I'll review the the `project-plan.md` and modify as needed before I even begin writing "code".  

### Update  GEMINI.md
Now that you have a project plan, you can update your `GEMINI.md` file to set specific engineering standards for the AI agent to follow within this workspace if it's not to your liking.  Again, you can use gemini to update it's own files.  For example, if you were doing best practice python, you might require PEP8. 

**Command:**
```bash
Based on project-plan.md, update the GEMINI.md file for this project. Require PEP8 and add a requirement to include error handling in every script.
```

### Direct the Coding
We have an updated GEMINI.md, project-plan.md and are ready to tell Gemini to write the actual code based on the established plan and memory.

**Command:**
```bash
Write a Python script for our  based on our project-plan.md. Use Playwright to take a full-page screenshot of a URL passed as a command-line argument. Ensure it follows the rules in our local GEMINI.md.
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


## References

- **Pricing & Tier Comparison:** [https://ai.google.dev/pricing](https://ai.google.dev/pricing)
- **Data Privacy & Usage Terms:** [https://ai.google.dev/gemini-api/terms#data-use](https://ai.google.dev/gemini-api/terms#data-use)

