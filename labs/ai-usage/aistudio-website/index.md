---
title: "Rapid Website Prototyping and Sales with Google AI Studio"
date: 2026-04-04
description: "Design, build, and pitch a custom website in minutes using Gemini 1.5 Pro and Google AI Studio."
tags: ["ai-usage", "aistudio", "web-design", "entrepreneurship", "sales"]
showTableOfContents: true
---

# Rapid Website Prototyping and Sales with Google AI Studio

## Objective
By the end of this lab, you will have used Google AI Studio to generate a complete, themed website for a real-world business and developed a high-conversion sales pitch to sell that site to a local client.

## Legal & Ethical Disclaimer
**FOR EDUCATIONAL AND PROFESSIONAL USE ONLY.** While using AI to generate websites for sales is a legitimate business model, always ensure the final product is functional, secure, and provides real value to the client. Never misrepresent yourself or your skills. Ensure you have the rights to use any images or videos included in the final product.

## Prerequisites
- A Google account to access [https://aistudio.google.com](https://aistudio.google.com).
- Basic understanding of how to host a static site (Review the **Static Hosting Using Github and Netlify** lab).
- A target local business (e.g., a hair salon, coffee shop, or law firm) that currently lacks a modern website.

## Why This Matters
Technical skills are most valuable when they solve a problem for someone else. Being able to build a professional-grade website in 30 minutes instead of 30 hours allows you to provide immediate value to a client before they even hire you. This "Show, Don't Tell" approach is the fastest way to generate quick cash and build a professional portfolio.

---

## Identify the Target and Gather Data
Find a local business that has a "Google Business Profile" but no website, or an outdated one.

*   **Gather Intelligence:** Copy their business name, address, services, and current photos from their Google profile.
*   **The Goal:** You aren't just making a "salon site"; you are making "The [Business Name] Hair Salon Site."

---

## Prototyping in Google AI Studio
Google AI Studio provides access to **Gemini 1.5 Pro**, which has a massive context window and advanced coding capabilities.

*   **Set the Model:** Choose `Gemini 1.5 Pro` in the model selector.
*   **The Master Prompt:** Use the following structure to generate the first draft:
    > "Create a modern, dark-themed website for [Business Name] with a premium and stylish design. The website should include a strong hero section with a placeholder logo, headline, short description, and a 'Book Appointment' button. Include pages for Home, Services, Gallery, About, and Contact. Appointments should be bookable via a form or a direct WhatsApp button. Use the following business details: [PASTE BUSINESS DETAILS HERE]."

---

## Refinement and Customization
AI-generated sites often need minor adjustments. Use these targeted prompts to fix common issues:

### Fixing Broken Images
If an image isn't showing or you have a specific one you want to use:
> "In the Gallery section, the 5th image is not showing. Please use this specific image URL: [https://images.pexels.com/photos/1231312/photo.jpg](https://images.pexels.com/photos/1231312/photo.jpg)"

### Adding Functional Links (WhatsApp/Social)
Ensure the CTA (Call to Action) actually works:
> "Update the WhatsApp button to link directly to this number: [https://wa.me/14702362870](https://wa.me/14702362870)"

### Connecting Forms
To make the contact form actually send emails, use a service like Formspree:
*   Create a form at [https://formspree.io/](https://formspree.io/).
*   Get your "Endpoint Link."
*   **Prompt:** "Update the contact form's action attribute to use this Formspree endpoint: [PASTE_ENDPOINT_LINK]."

---

## Adding Rich Media (Videos)
Video builds trust. If the business has a promotional video:
*   Upload it to YouTube as "Unlisted."
*   **Prompt:** "Embed this YouTube video into the 'About' section: [PASTE_YOUTUBE_LINK]."

---

## Hosting and Delivery
You need a live link to show the client.

*   **Option A:** Publish directly from Google AI Studio (for quick previews).
*   **Option B: Professional Deployment:** Download the code and host it on Netlify for a professional URL (e.g., `[https://businessname-preview.netlify.app](https://businessname-preview.netlify.app)`). This allows for custom domains and automatic updates.

---

## Next Step: Permanent Hosting
To get your prototype online for the client to see, you need to host it. Proceed to the **Static Hosting Using Github and Netlify** lab in the `labs/devops/` directory to learn how to deploy your AI-generated code to a global CDN for free.

---

## What You Learned
Don't ask them for a job; show them the solution you already built.

### The Pitch Script
Reach out via DM, Email, or Social Media:
> "Hi [Owner Name], I noticed your business on Google and saw you don't have a modern website yet. I am currently expanding my web design portfolio and I learn best by doing. I actually took the liberty of creating a prototype for you already to show you what's possible. What do you think of this design? [LINK_TO_SITE]"

### The Psychology of the Sale
*   **The Hook:** "I saw your business and built this for you." (Immediate value).
*   **The Proof:** The actual working link.
*   **The CTA:** "What do you think?" (Low pressure, high engagement).

---

## What You Learned
*   **Rapid Prototyping:** Using Gemini 1.5 Pro to generate functional web code in minutes.
*   **Problem-Solution Selling:** Identifying a business need and solving it before the first contact.
*   **Functional Integration:** Connecting AI code to real-world tools like Formspree and WhatsApp.
*   **The Portfolio Strategy:** Building a body of work while simultaneously hunting for clients.
