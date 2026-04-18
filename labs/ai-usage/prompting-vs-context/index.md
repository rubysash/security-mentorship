---
title: "Prompting vs. Context Prompting"
date: 2026-04-18
description: "Stop 'guessing' with your prompts. Learn how to give Gemini a Source of Truth using Gems, NotebookLM, and live system snapshots."
tags: ["ai", "gemini", "prompting", "context-prompting", "intermediate"]
showTableOfContents: true
---
# Prompting vs. Context Prompting

## Objective

By the end of this lab, you are going to stop treating AI like a magic 8-ball and start treating it like a technical partner. We are moving past basic "how to ask" and into the world of **Context Prompting**—where you give the AI a "Source of Truth" (SOT) using Gemini Gems and NotebookLM. You will learn to build a "mini-RAG" system that uses live data from your own machine to get vendor-accurate results.

## Legal & Ethical Disclaimer

**MANDATORY.** This lab is for educational purposes only. All AI-assisted activities, data processing, and automation must ONLY be performed on datasets, documents, and codebases for which you have explicit, written permission or ownership. Be mindful of data privacy when uploading information to cloud-based AI services. Never upload sensitive PII (Personally Identifiable Information), secrets, or proprietary data that you are not authorized to share with third-party providers.

![Prompting vs Context Diagram](featured.jpg)

## Prerequisites

- A Google Account with access to [https://gemini.google.com](https://gemini.google.com).
- Access to [https://notebooklm.google.com](https://notebooklm.google.com).
- A basic understanding that AI models "predict" the next word—and context is what keeps those predictions accurate.

## Why This Matters

Look, the "long prompt" era—where you write a three-page essay to get a one-page answer—is over. The real power now is **Context Prompting**. Instead of asking the AI to "remember" its training data, you are handing it the exact manual, the exact logs, or the exact code it needs to see. This kills hallucinations and gives you answers grounded in reality. In security and DevOps, a generic answer can get you fired; a context-driven answer solves the problem.

## Simple Prompting: The Base Recipe

We still use simple prompting for quick brainstorms or one-off fixes. Think of this as the "Base Recipe" for a good question. If you don't give the AI a role and a target, it's just guessing.

### The Anatomy of a High-Signal Prompt

- **The Role:** Who is the AI today? (e.g., "You are a Senior Security Architect.")
- **The Context:** Why are we here? (e.g., "I'm hardening a public-facing web server.")
- **The Task:** What is the move? (e.g., "Review these SSH settings for common weaknesses.")
- **The Format:** How do I want to see it? (e.g., "Give me a Markdown table with the setting, the risk, and the fix.")

### Simple Prompting Checklist ✅

- [ ] Did I define a specific persona?
- [ ] Did I set clear boundaries (e.g., "Only use standard Linux tools")?
- [ ] Did I use a "1-shot" example (showed it one example of what I want)?
- [ ] Did I specify the exact output format?

## Context Prompting: Giving the AI a Brain Transplant

Context prompting is where things get serious. You aren't just asking a question; you are building a temporary database for the AI to query. This is "mini-RAG" (Retrieval-Augmented Generation). You provide the "Source of Truth" (SOT), and the AI stays within those walls.

### Context Sources for Your "Source of Truth"

- **NotebookLM:** Think of this as a research assistant. You upload PDFs, video transcripts, or technical docs, and it grounds every answer in those files. [https://notebooklm.google.com](https://notebooklm.google.com).
- **Gemini Gems:** These are your custom-built experts. You give them persistent instructions and tell them exactly which files to trust.
- **Transcripts & Swipe Files:** Use video transcripts or "Swipe Files" (examples of perfect work) to teach the Gem your specific style and logic.
- **pdf2md Scripts:** Complex PDFs are noisy. Use a script to convert them to clean Markdown so the AI doesn't get distracted by page numbers and headers. Use this repo: [https://github.com/rubysash/pdf2md.git](https://github.com/rubysash/pdf2md.git).

## Active Context: The "Script-Bridge" and MCP

Sometimes the data you need isn't in a PDF—it's live on your machine or in an API. Professional-grade Gems use **Active Context**.

### What is MCP?

The Model Context Protocol (MCP) is like a universal plug for your data. 

- **The Old Way (APIs):** You write a Python script -> Fetch data -> Format it -> Upload it. It's manual labor.
- **The New Way (MCP):** You run an MCP Server (like a SQL or Google Drive connector) and the AI "plugs in" to query what it needs, when it needs it.

Since the browser interface for Gemini Gems can't see your local hard drive (for good security reasons!), we use a **Script-Bridge**. We use a local script to take a "snapshot" of your system data and then hand that snapshot to the Gem.

## Setting Up a Professional Gemini Gem

A Gem is a specialized agent. To make it work like a pro, you have to define the **Tiers of Truth** in its instructions. You are telling it which information to value most.

### Gem Custom Instructions Template

When you build your Gem, use this "mentor-style" structure in the Instructions field:

```text
# Role & Expertise
You are the <SPECIALIZED_ROLE> for the <PROJECT_NAME>.

# Source of Truth (SOT)
Your primary source of truth is the uploaded documentation.
- Tier 1: Technical Specifications (Highest Priority)
- Tier 2: My uploaded 'Active Context' snapshots (Live system data)
- Tier 3: Internal brainstorming and transcripts

# Processing Logic
1. When I ask a question, check Tier 1 and Tier 2 first.
2. If the data is missing, tell me exactly what Tier is silent.
3. Use the Google Search extension to verify local data against official vendor documentation (like learn.microsoft.com).
4. Provide the direct URLs to the vendor docs so I can verify your logic.

# Style
Be direct. No fluff. No 'As an AI language model.' Just the tech.
```

## Hands-On Lab: The System Optimizer Gem

Let's build something real. We're going to make a Gem that analyzes your local Windows services and cross-references them with official Microsoft documentation to suggest speed improvements.

### Generate Your Live Snapshot

First, we need to give the Gem "eyes" into your system. Run this PowerShell command to take a snapshot of your running services:

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"} | Select-Object Name, DisplayName, StartType | ConvertTo-Json | Out-File -FilePath "services.json"
```

### Create the Optimizer Gem

1.  Go to **Gems** > **New Gem** in the Gemini web interface.
2.  **Name:** System Optimizer.
3.  **Enable Extensions:** Make sure **Google Search** is turned ON.
4.  **Instructions:** Paste this logic into the box:

```text
# Role
You are a Windows Performance Analyst.

# Objective
Analyze my 'services.json' file. Identify 5 services safe to optimize for a gaming/home PC.

# Process
1. For every service you select, you MUST use Google Search with 'site:learn.microsoft.com' to find the official vendor description.
2. Compare my local 'StartType' with the official recommended state.
3. Provide the Service Name, a summary of what it does, and the DIRECT LINK to the Microsoft Learn page.

# Disclaimer
Include this: "Validate these recommendations using the provided Microsoft links or 'Get-Help' in PowerShell before acting."
```

### Run the Analysis

1.  Open your new **System Optimizer** Gem.
2.  Upload the `services.json` file you created.
3.  Ask: "Analyze my services for a high-performance gaming setup."
4.  **Verify:** Click the Microsoft Learn links it provides. Does the vendor data match what the AI told you?

## Comparing the Two Approaches

| Feature | Simple Prompting | Context Prompting (Gems) |
|---------|------------------|--------------------------|
| **Knowledge** | "Best guess" from training | Your specific system & files |
| **Accuracy** | Decent, but can hallucinate | High (Grounded in vendor docs) |
| **Verification**| Hard to double-check | Direct links to the Source of Truth |
| **Best For** | Brainstorming & quick fixes | Technical audits & system analysis |

## What You Learned

- **The difference between "guessing" and "grounding."**
- **How to use a Script-Bridge** to get live data into a web-based Gem.
- **The importance of Tiers of Truth** so the AI knows which data to trust first.
- **How to force the AI to show its work** by providing direct vendor URLs.

By moving from "asking" to "providing context," you just upgraded from using a chatbot to using a professional-grade engineering tool.
