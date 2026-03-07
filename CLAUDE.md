# Security Mentorship Labs

## Project Purpose

This is a hands-on mentorship project for people breaking into cybersecurity, DevOps, automation, and coding careers. It targets entry-level learners asking "where do I start?" and "how do I skill up?" — providing structured labs they can follow to build real skills and a portfolio.

## Project Structure

- `/labs/` — Individual lab folders, each self-contained with its own instructions
  - Lab folders use kebab-case naming (e.g., `static-hosting-netlify`)
  - Each lab should have a README.md or index.md with step-by-step instructions
- `/README.md` — Master index of all planned and available labs

## Content Guidelines

- Write for beginners. Assume no prior experience unless the lab explicitly lists prerequisites.
- Every lab should be completable using free tools and free-tier cloud services.
- Include the "why" — explain what each tool/concept is used for in real jobs, not just how to click through it.
- Use practical, job-relevant examples. Frame labs around tasks a junior analyst, SOC operator, or DevOps engineer would actually do.
- When referencing certifications, tie them back to the hands-on skills covered in labs.

## Writing Style

- Clear, direct language. No jargon without explanation.
- Step-by-step numbered instructions for procedures.
- Use code blocks for all commands, config files, and terminal output.
- Include expected output or screenshots where helpful so learners can verify they're on track.
- Keep files focused — one topic per lab.

## Technical Preferences

- Prefer open-source tools when possible.
- Use Git and GitHub as the backbone for version control and collaboration labs.
- For cloud labs, default to free-tier resources (AWS, Azure, GCP).
- For web/static hosting, use Netlify or GitHub Pages.
- Python is the primary scripting language for automation labs.
- Docker for containerization labs.

## Lab Template

When creating a new lab, include:

1. **Title** — What the lab covers
2. **Objective** — What the learner will be able to do after completing it
3. **Prerequisites** — Any prior labs or knowledge needed
4. **Tools/Accounts Needed** — What to install or sign up for
5. **Steps** — Numbered walkthrough
6. **Verify It Worked** — How to confirm success
7. **What You Learned** — Brief recap of skills gained and how they apply to real jobs
