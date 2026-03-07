---
title: "Static Hosting Using Github and Netlify"
date: 2026-03-07
description: "Hosting static files (client side scripting too).  Use AI or hand code something and serve it over CDN to the world, Free."
tags: ["devops", "netlify", "github", "hosting", "beginner"]
showTableOfContents: true
---
# Static Hosting Using Github and Netlify

## Objective

By the end of this lab you will have a live website on the internet, auto-deploying from GitHub, optionally on your own domain with HTTPS --for free.

## Prerequisites

- A computer with a web browser
- An email address for signups

## Why This Matters

Static hosting is the simplest form of deployment, and it's everywhere.  Landing pages, documentation sites, internal tools, dashboards --companies host these as static sites.  Knowing how to ship code from a repo to a live URL through a CI/CD pipeline (even a simple one like Netlify) is a real DevOps skill.  This is the foundation for everything else.

## 1. Think of What to Put Online

Nothing wrong with using AI to help you plan out something useful.  [Gemini](https://gemini.google.com), [ChatGPT](https://chatgpt.com), [Grok](https://grok.com/), [Claude](https://claude.ai), [Manus](https://manus.com), etc.  Take your pick.

Thinking (and now augmented thinking) is the most important part of anything.  What does a month, a year, 10 years benefit of this thing provide me or provide the world?

- Poem/Song/Art
- Resume
- Business Brochure
- Hobby Notes
- JavaScript App
- JavaScript Tool
- JavaScript Game
- Templates to Share
- Affiliate Review
- Lead Collection Form

## 2. Create the Asset

Upload your resume into the LLM of choice, some are better than others for specific tasks.  Don't focus on perfect, just get through this step then you can do a "perfect version" later.  Ask LLM of your choice to make a static webpage out of it with separate style.css as single blocks of code for you to cut and paste (an example project).  Or use AI to make a pretty website, or app in html/css/javascript.  Now you have 2 files in a separate folder of your projects.

```
projects/resume/index.html
projects/resume/style.css
```

For example [Google AI Studio](https://aistudio.google.com), [Lovable](https://lovable.dev/), and [Claude](https://claude.ai) can all make beautiful websites.  AI Studio comes with Gemini and is free to use --great for quick prototyping.

> **Tip:** When prompting the AI, be specific.  Instead of "make me a resume site" try "Create a single-page responsive resume website for a cybersecurity analyst. Use a clean dark theme with separate style.css. Include sections for summary, skills, experience, certifications, and contact."

### What Your Files Should Look Like

Your `index.html` is the page content.  Your `style.css` controls colors, fonts, layout.  At minimum, your index.html should link the stylesheet in the `<head>`:

```html
<link rel="stylesheet" href="style.css">
```

If the AI gave you everything in one file, ask it to split the CSS into a separate `style.css`.  Keeping them separate is a good habit --it's how real projects work.

## 3. Setup Editing Workflow (options)

You need to edit your coded object somehow in the future.  There are many options.  Here are just a few:

### Notepad++

[Download Notepad++](https://notepad-plus-plus.org/downloads/)

You are hard core, stubborn and refuse to learn new tools.  This option is for you.

### Visual Studio Code

[Download VS Code](https://code.visualstudio.com/download)

If you want to learn a bit about code, useful coding and development tools, and have plugins to assist you.  If it's in a folder called projects/resume --you would "open the folder" in Visual Studio Code.  This allows you to see and make minor changes.  I use Visual Studio Code and combine it with Claude Code to edit my projects now.

**Recommended extensions for this lab:**
- **Live Server** --preview your site locally before pushing to GitHub
- **Prettier** --auto-format your HTML/CSS

![VS Code with project folder open](vscode-open-folder.png)

### GPT/Project

If you are saving money nearly all LLMs now have project spaces, customGPT, etc.  You can build your workflow around one of their tools and refresh their knowledge by uploading your files each session.

### Claude Code

[Install Claude Code](https://docs.anthropic.com/en/docs/claude-code/overview)

You can go to the CLI at your project folder and type `claude` if you've installed Claude Code, and can further edit your project using Claude.  Claude Code has replaced all of my other tools for serious coding work.  Nothing compares to its power.  The only limit is the cost and on the Pro plan I don't run out of tokens or wait.  The basic plan is good enough for most.

## 4. Setup GitHub Account

[GitHub](https://github.com/) --Sign up if you don't have an account.

GitHub is where the files live, and where backups and revisions are done.  This is version control --every change you make is tracked and reversible.  Every tech company uses it or something like it (GitLab, Bitbucket).  Getting comfortable with GitHub is non-negotiable for security/DevOps roles.

### Create Your Repository

- Click the **+** in the top right corner, then **New repository**
- Name it `resume` (or whatever your project is)
- Set it to **Public** (required for free Netlify -- we'll make it private later)
- Check **Add a README file**
- Click **Create repository**

![GitHub new repository page](github-new-repo.png)

### Upload Your Files

- In your new repo, click **Add file** > **Upload files**
- Drag in your `index.html` and `style.css`
- Write a commit message like "initial resume site"
- Click **Commit changes**

![GitHub upload files interface](github-upload-files.png)

> **Note:** Later you'll learn to use `git` from the command line, which is faster and more powerful.  For now, the web upload works fine.

## 5. Connect GitHub to Netlify

[Netlify](https://app.netlify.com/) --Sign up with your GitHub account.

Netlify is a CDN (Content Delivery Network), and much more.  It will monitor GitHub for changes and auto-publish to the CDN.  This is a CI/CD pipeline --Continuous Integration / Continuous Deployment.  You push code, it goes live automatically.  That concept is the backbone of DevOps.

### Deploy Your Site

- Log into Netlify and click **Add new site** > **Import an existing project**

![Netlify add new site](netlify-new-site.png)

- Choose **GitHub** as your Git provider
- Authorize Netlify to access your GitHub account
- Select your `resume` repository

![Netlify select repository](netlify-select-repo.png)

- Leave the build settings as defaults (no build command needed for static files)
- Click **Deploy site**

![Netlify deploy settings](netlify-deploy-settings.png)

- Netlify will assign a random name like `wonderful-torvalds-a1b2c3.netlify.app`
- Go to **Site configuration** > **Change site name** to something readable like `yourname-resume`
- Visit `yourname-resume.netlify.app` to see it live

![Netlify site live](netlify-site-live.png)

> **Now you can go back to GitHub and make the repository private.** Netlify already has access and will continue deploying.

## 6. Configure a Custom Domain (Optional)

This step costs ~$10/year for a domain.  Skip it if you're just practicing.

### Buy a Domain on Cloudflare

[Cloudflare Dashboard](https://dash.cloudflare.com/) --Sign up if you don't have an account.

Use Cloudflare --not GoDaddy, Namecheap, 1&1, or anything else.  Cloudflare sells domains at cost (no markup), includes free DNS, free CDN, free DDoS protection, and free SSL.  There is no reason to use anyone else for registration.

Buy and add a domain name for ~$10.44.  `yourname.com` is a good one.  Buy it.  Domains are like real estate.  Build up something useful on it and it's worth thousands.  Think of `location+service.com` if you get stuck and just need something, or think of a 2 word, easy to spell combo like mine: `digitalcrunch.com` --or get one that is your hobby: `6holeocarina.com`, etc.

### Cloudflare DNS Settings

Add these two records in the Cloudflare DNS dashboard for your domain:

| Type | Name | Content |
|------|------|---------|
| A | `@` | `75.2.60.5` |
| CNAME | `www` | `yourdomainname.com` |

![Cloudflare DNS records](cloudflare-dns-records.png)

> The A record points your root domain (`yourname.com`) to Netlify's load balancer.  The CNAME makes `www.yourname.com` work too.

### Netlify Domain Settings

In [Netlify](https://app.netlify.com/):

- Go to your **Project** > **Domain management**
- Click **Add a domain** and enter your custom domain
- Set it as the **primary domain**

![Netlify domain management](netlify-domain-management.png)

- Go to **Domain management** > **HTTPS**
- Click **Verify DNS configuration**
- Click **Provision certificate** -- Netlify will issue a free Let's Encrypt SSL cert

![Netlify HTTPS certificate](netlify-https-cert.png)

> **DNS can take up to 48 hours to propagate**, but usually it's under 30 minutes.  If the certificate won't provision, wait and try again.

## 7. Test Your Work

Now verify the whole pipeline works end to end:

- Visit `yourname-resume.netlify.app` (or `yourdomain.com` if you set one up)
- Go to your repo on GitHub and edit a file -- change a color, a word, anything
- Commit the change
- Watch the deploy status in Netlify (usually 30 seconds or less)

![Netlify deploy log](netlify-deploy-log.png)

- Refresh your site and see the change live

You just deployed code to production.  That's the job.

## What You Learned

- **Static hosting** --serving HTML/CSS/JS without a backend server
- **Git and GitHub** --version control, the foundation of all collaborative development
- **CI/CD basics** --code goes from repo to live site automatically (Netlify watches GitHub)
- **DNS fundamentals** --A records, CNAMEs, how domain names resolve to servers
- **HTTPS/TLS** --free SSL certificates with Let's Encrypt, why encryption matters
- **CDN** --content delivery networks and why they make sites fast and resilient

These are real skills that show up in job descriptions for SOC analysts, DevOps engineers, cloud security roles, and penetration testers.  You now have a live project to put on your resume --and the resume itself can *be* that project.
