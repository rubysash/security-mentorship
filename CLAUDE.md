# Security Mentorship Labs

## Project Purpose

This is a hands-on mentorship project for people breaking into cybersecurity, DevOps, automation, and coding careers. It targets entry-level learners asking "where do I start?" and "how do I skill up?" --providing structured labs they can follow to build real skills and a portfolio.

## Project Structure (Hugo Blowfish Compatible)

This project is structured for the Hugo Blowfish theme using page bundles.

- `/labs/_index.md` -- Branch bundle (section list page for all labs)
- `/labs/some-lab-name/index.md` -- Leaf bundle (individual lab page)
- Images and assets go in the same folder as their `index.md`, not in subfolders
- Reference images as `image.png` not `images/image.png` or `/images/image.png`
- Lab folders use kebab-case naming (e.g., `static-hosting-netlify`)
- `/README.md` -- Master index of all planned and available labs (GitHub-facing)

## Content Guidelines

- Write for beginners. Assume no prior experience unless the lab explicitly lists prerequisites.
- Every lab should be completable using free tools and free-tier cloud services.
- Include the "why" --explain what each tool/concept is used for in real jobs, not just how to click through it.
- Use practical, job-relevant examples. Frame labs around tasks a junior analyst, SOC operator, or DevOps engineer would actually do.
- When referencing certifications, tie them back to the hands-on skills covered in labs.

## Writing Style

- Clear, direct language. No jargon without explanation.
- Never use em dashes. Use commas, periods, or " -- " (spaced double hyphens) instead.
- Never use emojis in any content.
- Step-by-step numbered instructions for procedures.
- Never nest numbered lists inside numbered lists. Use numbers for the top level, then bullets for sub-steps. If a third level is needed, use letters or roman numerals.
- Use code blocks for all commands, config files, and terminal output.
- Include expected output or screenshots where helpful so learners can verify they're on track.
- Keep files focused, one topic per lab.

## Technical Preferences

- Prefer open-source tools when possible.
- Use Git and GitHub as the backbone for version control and collaboration labs.
- For cloud labs, default to free-tier resources (AWS, Azure, GCP).
- For web/static hosting, use Netlify or GitHub Pages.
- Python is the primary scripting language for automation labs.
- Docker for containerization labs.

## Lab Template

When creating a new lab, include:

1. **Title** -- What the lab covers
2. **Objective** -- What the learner will be able to do after completing it
3. **Prerequisites** -- Any prior labs or knowledge needed
4. **Tools/Accounts Needed** -- What to install or sign up for
5. **Steps** -- Numbered walkthrough
6. **Verify It Worked** -- How to confirm success
7. **What You Learned** -- Brief recap of skills gained and how they apply to real jobs

Front matter should always include:

```yaml
---
title: "Lab Title"
date: YYYY-MM-DD
description: "Short description for search and previews."
tags: ["relevant", "tags"]
showTableOfContents: true
---
```
