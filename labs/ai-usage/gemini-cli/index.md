---
title: "Beginner Gemini CLI: AI-Powered Engineering"
date: 2026-04-28
description: "Install, configure, and use the Gemini CLI to plan projects, manage environments, and automate tasks like website screenshotting."
tags: ["ai-usage", "gemini-cli", "automation", "python", "cli"]
showTableOfContents: true
---

# Gemini CLI: Basic Python Use Example

## Objective
By the end of this lab, you will have installed the Gemini CLI, used it to architect a project plan, and developed a functional Python script to capture website screenshots.  You will do all of this from your terminal, working with gemini-cli.

**Note** you need a Google Account To authenticate your AI session.

## What is Gemini-CLI?

It can look at a folder, analyze all of the files and function like a custom AI (based on GEMINI.md instructions) for those files.    It can be used to write scripts or books, analyze log files, court cases, and do just about anything you can imagine an AI would do.   It does not create images, however, you can hook and call to external sources that gather data or create images for you.   It can call APIs, read websites, download files, and do anything you can imagine really.   
  
You can "train" it with one or more detailed skills that are specific actions it can follow.   It can use agents and mcps combined with real time decision making.    Typically this version of gemini cli requires constant steering.  It is not a completely autonomous AI.

We are going to use it to write a simple script in this lab.

## Checklist

Here is the TLDR version of what we are going to cover.

- Install Prequisites
- Setup python Environment
- Install gemini-cli
- Authenticate
- /init and GEMINI.md
- Select Models
- Create a Project Plan Using Gemini
- Execute the Plan
- Revision Control
- Other Useful Commands


## Install Prerequisites

Node is required for Gemini, but we are going to do other work with it, so we'll install python and git too.

- **Node.js installed** (Required for npm): Download at [https://nodejs.org/](https://nodejs.org/).
- **Python 3 installed** (For the project portion): Download at [https://www.python.org/downloads/](https://www.python.org/downloads/).  I suggest 3.13 because 3.14 does not have full support yet.
- **GIT installed** (For revisions): Download at [https://git-scm.com](https://git-scm.com)  

Git can be used for local revision and does not require a github account, but that is also worth learning if you work between multiple computers, or with multiple people on the same project.   We are going to use it for local snapshots in this lab.

---

## Python Environment

In this lab we are going to use python to capture a screenshoot of a site and gemini to create the scripts.   To do that, we need a working environment for our python files, and then we'll use gemini to work with those files.

We'll use the `venv` module to create the virtual environment called `site-screenshot` that stores our scripts and modules for this program.

```bash
# Create the environment folder
python3 -m venv site-screenshot

# Enter the workspace
cd site-screenshot
```

### Activate
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

## Authenticate

In this folder, type:  `gemini` to start the gemini cli.   It will ask for authorization before you can continue.

This is pretty straight forward.  Your free google account will allow basic work.   You can purchase a subscription from [https://one.google.com/about/plans](https://one.google.com/about/plans) for about $21 a month for additional usage beyond the free tier.

## /init and GEMINI.md

typing `/init` in the cli will create a filed called "GEMINI.md" that contains the basic instructions for your project.  You can edit this and fine tune how the AI responds, thinks, prioritizes and more.

You can also create a `.geminiignore` file to tell gemini what to ignore.    Just list the files and directories like you would to ignore, using the same format as you might a `.gitignore`.

The initial `/init` will create blank or generic files and you will need to edit them to your specific project needs.      `GEMINI.md` files are folder and sub folder specific, but also you can have a main `GEMINI.md` file for everything you do.   Each folder and subfolder can have specific gemini files as needed.  

The Gemini CLI uses `GEMINI.md` files to remember your rules and preferences. You can edit these at different levels:

*   **Global Memory:** `~/.gemini/GEMINI.md` (Rules for every project).
*   **Project Root:** `./GEMINI.md` (Rules for the current repository).
*   **Subdirectory:** `./src/GEMINI.md` (Rules specific to a folder).

## Select Models

By default gemini will try to use the model it thinks is best suited for the task.   The "pro" model will consume your credits faster, but is best for writing code.    You can think and plan with Gemini 3 "auto".

```bash
/model list
/model set auto
/model set gemini-3.1-pro
/model manage
```

I typically use `/model set auto` unless I have a few wrong answers in a row, then I force the model into it's higest tier and ask the question again.   For now, use `/model set auto`

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

This is an example and how I start most of my projects.   THen I'll review the the `project-plan.md` and modify as needed before I even begin writing "code".  The project-plan.md is not a requirement, it's just something I do as I build any project.  Typically I'll build the plan, then revist the GEMINI.md file and update them base don the plan.

### Update  GEMINI.md
Now that you have a project plan, you can update your `GEMINI.md` file to set specific engineering standards for the AI agent to follow within this workspace if it's not to your liking.  Again, you can use gemini to update it's own files.  For example, if you were doing best practices in python, you might require PEP8, certain formatting, . 

**Example Prompt:**
```bash
Based on project-plan.md, update the GEMINI.md file for this project. Require PEP8 and add a requirement to include error handling in every script.    Create a staged MVP plan so we can get the MVP working.
```

By stating we want an MVP it will focus on the core features instead of getting overwhelmed.

## Execute the Plan
We have an updated GEMINI.md, project-plan.md and a staged MVP plan, and are ready to tell Gemini to write the actual code based on the established plan and memory.   Read through all of the GEMINI.md and project-plan.md files to make sure it is building what you expect.

**Command:**
```bash
Write a Python script for our  based on our project-plan.md. Use Playwright to take a full-page screenshot of a URL passed as a command-line argument. Ensure it follows the rules in our local GEMINI.md.   Start with just skeleton and comments.
```

I alway start with skeleton code and comments because it forces the AI to "show it's work".   I've found this always makes cleaner, more logical code that has fewer errors.

```bash
Based on the project-plan and existing skeleton code let's work towards the MVP and stage 1 of the MVP.  What are the next steps?
```

Repeat a process similar to this to get your MVP working.   There will be mistakes and crazy suggestions.  This is where your overall knowledge and skill helps shape how the AI functions.   For example, I know about PEP8, but a novice programmer may not.   Because I know about it, my scripts will be PEP8 (because I told AI to adhere to that standard), and a novice programmer's code may or may not.   

### Project Structure
Your workspace should now look like this. Note that the standard virtual environment files (`bin`, `lib`, `pyvenv.cfg`) live alongside your project files:

```text
site-screenshot/
├── bin/                    # Venv binaries (Scripts/ on Windows)
├── lib/                    # Venv library packages
├── pyvenv.cfg              # Venv configuration
├── GEMINI.md               # Project-specific rules and context
├── .geminiignore           # List things gemini should ignore
├── .gitignore              # List things that should never be public or on git
├── project-plan.md         # The AI-generated technical blueprint
└── main.py                 # The functional Python script
```

There may be other files such as config.py, .env, gui.py etc depending on what you are building.  It's a good idea

## Run the Code

In another terminal, I open the venv we previously installed and run the code, feeding any errors into the gemini-cli prompt and rerunning the code.   I also use vscode, open the folder and manually review code.    Using this process I keep working with the gemini-cli until I have working code.    

---

## Revision Control

Sometimes, the AI will make a suggestion that modifies multiple files, and essentially breaks your code.  It's nice to have a revision point.     In my work flow I install git (part of the prerequisits).   Then before any major changes, I commit.  If I ever need to restore, I can do so.    That work flow looks like this:

### Initialize Git

Do this from your project directory.

```bash
git init
```
### Take Snapshots

```bash
git add .
git commit -m "Changed xyz, some useful comment"
```

### View Your Revisions

To find the specific snapshot you want to restore, you need to view your Git log. The most readable way to do this in the terminal is by using the one-line flag.

```bash
    git log --oneline
```

This outputs a chronological list of your commits, looking something like this:

```bash
    d9f4a12 Changed xyz, some useful comment
    b3c2d11 Initial commit
```

The 7-character alphanumeric string at the beginning of each line (e.g., d9f4a12) is your **commit hash**. You will use this unique identifier to tell Git exactly which snapshot to target.

### Restore a Previous Revision

You have two primary methods to undo the damage, depending on your environment.

#### Option 1: Hard Reset

If you are working solo on your local machine and want to completely nuke the broken AI code to start fresh, use a hard reset. This moves your project exactly back to your chosen snapshot. 

*Warning: This is a destructive command. It will permanently delete any uncommitted changes and erase the history of commits that occurred after your target hash.*

```bash
    git reset --hard <commit-hash>
```

#### Option 2: Revert

If you are working in a production environment, sharing code, or simply want to maintain a strict defensive audit trail, you should never erase history. Instead, use a revert. This command analyzes the target commit and creates a brand *new* commit that applies the exact opposite changes, safely undoing the damage while preserving the chronological timeline of what happened.

```bash
    git revert <commit-hash>
```

## Useful Commands

Your entire token context is in memory for every quesiton you ask.  That means, by clearing that window and starting fresh, it's sometimes easier for the AI (and uses less tokens).   This allows you to work longer on the better models (because your credits won't be wasted with conversation that isn't relevant).

* `/clear` - Starts a new converation and rerereads your GEMINI.md files
* `/compress` - Keeps the important parts of the conversation, dumps the rest.
* `/memory show` - View current memory.
* `/memory reload` - Refresh rules after editing a file.

Keeping your GEMINI.md file updated, using `/clear` and `/compress` often, allows me to use the highest tier all day because I'm optimizing my use of the context window.

Other commands you might find useful as you work more with gemini-cli

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


## What You Learned
*   **CLI Integration:** Running AI agents natively in your terminal.
*   **Architectural Planning:** Using AI to design project structures before coding.
*   **Environment Management:** Setting up a workspace where the project folder **is** the virtual environment.
*   **Contextual Memory:** Using `GEMINI.md` to persist engineering standards.
*   **Gemini CLI Powered Workflow**: Using gemini-cli to plan and create.

---
## References

* **Pricing & Tier Comparison:** [https://ai.google.dev/pricing](https://ai.google.dev/pricing)
* **Data Privacy & Usage Terms:** [https://ai.google.dev/gemini-api/terms#data-use](https://ai.google.dev/gemini-api/terms#data-use)

*   **Official CLI Reference:** [https://geminicli.com/docs/cli/cli-reference/](https://geminicli.com/docs/cli/cli-reference/)
*   **Skills Getting Started:** [https://geminicli.com/docs/cli/tutorials/skills-getting-started/](https://geminicli.com/docs/cli/tutorials/skills-getting-started/)
*   **Google AI Studio:** [https://aistudio.google.com](https://aistudio.google.com)


