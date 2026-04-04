# Security Mentorship Project: Gemini Context

This repository, **Security Learning Labs**, is a comprehensive collection of hands-on tutorials and guides designed to mentor individuals in cybersecurity, DevOps, and modern technical skills.

## Project Goals
- Provide structured, practical labs for foundational and advanced security topics.
- Bridge the gap between theory and practice through real-world scenarios (e.g., setting up a secure resume site, network monitoring).
- Cover a wide range of technologies: Linux, Cloud (AWS/Azure/GCP), Python, Docker, and AI-assisted development.
- Maintain a repository of knowledge that aligns with industry certifications (CompTIA, AWS, etc.).

## Project Structure
The canonical project structure, including the directory layout for labs, reference material, and flashcards, is maintained in the **README.md** file. Refer to that diagram for all organizational standards.

## Student Environment
All labs are designed to be performed on the following standard environments:
- **Raspberry Pi:** Running Raspberry Pi OS (Debian-based). This is the preferred hardware for native networking labs.
- **WSL (Windows Subsystem for Linux):** Running Ubuntu or Kali Linux. Ideal for students on Windows who want a Linux-native CLI experience.

## Lab Template Standards
All new labs MUST follow this structure to ensure consistency, educational value, and legal safety. Refer to `labs/devops/static-hosting-netlify/index.md` as the gold standard for layout.

### Frontmatter (YAML)
Standard metadata including title, date, description, and tags.

### Objective
A clear statement of what the learner will be able to do by the end of the lab.

### Legal & Ethical Disclaimer
**MANDATORY.** A prominent warning immediately following the Objective. It must explicitly state that the lab activities are for educational purposes only and must ONLY be performed on networks, systems, and devices owned by the student or for which they have explicit, written permission. It should warn of the potential legal and ISP consequences of unauthorized activity.

### Prerequisites
List of tools, hardware (Pi/WSL), accounts, or prior knowledge required.

### Why This Matters
The "So What?" section. Explain the security context, DevOps relevance, or career impact of this specific skill.

### Lab Instructions
*   Use clear, descriptive headings (avoid forced numbering).
*   Include code blocks with language identifiers.
*   Use `> **Tip:**` or `> **Note:**` for extra context.
*   Include professional "Pentester Tips" or "Analyst Notes" where appropriate.

### What You Learned
A summary of the specific skills and concepts mastered during the lab.

## Learning Paths (2026+ Strategy)

The project is designed to support various career trajectories by combining foundational knowledge with modern automation and AI skills.

### Defensive / Security Analyst Path
- **Focus:** `labs/foundational`, `labs/network-security`, `reference/networking`, `flashcards/comptia (CySA+)`.
- **Goal:** Master visibility, log analysis, and incident response.

### Offensive / Pen Tester Path
- **Focus:** `labs/network-security`, `labs/python`, `reference/os-internals`, `flashcards/comptia (PenTest+)`.
- **Goal:** Understand exploitation, scripting custom tools, and vulnerability assessment.

### Cloud Security / DevOps Path
- **Focus:** `labs/cloud`, `labs/devops`, `labs/ai-usage`, `flashcards/aws` or `flashcards/azure`.
- **Goal:** Secure infrastructure-as-code, automate deployments, and leverage AI for secure coding.

### The "Full-Stack" Security Professional
- **Focus:** Cross-disciplinary labs including `labs/job-hunting` and `labs/ai-usage`.
- **Goal:** Become a highly versatile engineer capable of building, securing, and automating systems while effectively marketing those skills.

---

## Core Mandates & Engineering Standards

### Security & Integrity
- **No Secrets:** Never include API keys, passwords, or PII in lab files or code examples. Use placeholders like `<YOUR_API_KEY>`.
- **Safe Tools:** When recommending tools, prioritize industry-standard, secure options (e.g., Cloudflare over less secure registrars).

### Context Efficiency
- **Surgical Edits:** When updating labs, modify only the relevant sections.
- **Parallel Research:** Use `grep_search` and `glob` to find related labs when creating cross-references.

### Documentation Style
- **Tone:** Professional, encouraging, and mentor-like.
- **Clarity:** Use simple language for foundational labs; increase technical depth for advanced labs.
- **Formatting:** 
  - **NO NUMBERED HEADERS:** Do not use "1.", "1.1", or any sequential numbering in headers or subheaders (`#`, `##`, `###`). Use clear, descriptive text instead.
  - **Lists:** Use bullet points for lists. Only use numbered lists within a section if a strict technical sequence is required (e.g., sequential terminal commands).
  - **Hyperlinks:** Every hyperlink MUST include the entire full URL as the link text. Example: `[https://google.com](https://google.com)`. Never use descriptive text like `[Google](https://google.com)`.
  - **Placeholders:** Use `<ALL_CAPS_WITH_UNDERSCORES>` for user-specific placeholders. Never use `example.com` or similar as a placeholder destination.
  - **NO ICONS:** Never include icons (emojis, etc.) in any document unless explicitly asked to do so by the user.
- **Visuals:**
  - **Location:** All images MUST be stored in the same folder as the lab's `index.md`.
- **Featured Image:** The main lab image MUST be named `featured.ext` (supported extensions: `.svg`, `.png`, `.jpg`, `.gif`, `.webp`).
- **Additional Images:** Other images can have any name but must also be stored in the same lab folder.
- **Reference:** Ensure all referenced images exist in the lab folder.
- **Diagramming Standard:** Prefer **Data-Driven Diagramming**. Use AI to transform raw scan results into structured formats (JSON/CSV) that can be ingested by specialized visualization tools. This is preferred over manual drawing for scalability and accuracy.

## Workflows

### Creating a New Lab
1. **Research:** Check `README.md` for the planned lab list to ensure the topic is needed.
2. **Drafting:** Use the Lab Template above.
3. **Validation:** Ensure all links and commands are accurate and functional.

### Updating Existing Labs
1. **Verify:** Check if the tool or service (e.g., Netlify UI, AWS Console) has changed.
2. **Refine:** Improve clarity based on common points of confusion.
