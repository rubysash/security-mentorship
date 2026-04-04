---
title: "Linux Foundations: The Filesystem"
date: 2026-04-04
description: "Master the structure, navigation, and key directories of the Linux operating system."
tags: ["foundational", "linux", "theory"]
showTableOfContents: true
---

# Linux Foundations: The Filesystem

## Objective
Memorize and understand the standard directory structure (FHS) used by nearly all Linux distributions.

## Legal & Ethical Disclaimer
**FOR EDUCATIONAL USE ONLY.** This lab provides conceptual knowledge. Only practice navigation commands on your own hardware (Pi/WSL).

## Prerequisites
- Access to a Linux terminal (Raspberry Pi or WSL).

## Why This Matters
Linux is the professional standard for servers, cloud infrastructure, and security tools. If you don't know where your configuration files (`/etc`) or logs (`/var/log`) are stored, you cannot effectively troubleshoot or secure a system.

---

## The Linux Filesystem Structure
Linux uses a hierarchical structure where everything starts from the **Root** (`/`).

*   **Root (/):** The starting point of the entire filesystem.
*   **/etc:** Where system-wide configuration files are stored.
*   **/var/log:** Where system and application logs live (Critical for security analysts).
*   **/bin & /sbin:** Where essential binary commands live (e.g., `ls`, `cp`, `nmap`).
*   **/home:** Where users' personal files are stored.
*   **/root:** The home directory for the superuser (root).
*   **/tmp:** Temporary files that are usually deleted upon reboot.
*   **/dev:** Hardware device files (e.g., hard drives, USB ports).
*   **/mnt & /media:** Where you mount external drives or filesystems.

---

## Learning Resources

### YouTube Channels to Follow
*   **NetworkChuck:** [https://www.youtube.com/@NetworkChuck](https://www.youtube.com/@NetworkChuck) (Linux for Beginners series).
*   **The Linux Experiment:** [https://www.youtube.com/@TheLinuxExperiment](https://www.youtube.com/@TheLinuxExperiment) (Desktop and philosophy).
*   **Learn Linux TV:** [https://www.youtube.com/@LearnLinuxTV](https://www.youtube.com/@LearnLinuxTV) (Deep dives and administration).

### Udemy Search Terms
*   "Linux for Beginners" (Jason Cannon)
*   "LPI Linux Essentials"

---

## Recommended Certification
*   **LPI Linux Essentials:** [https://www.lpi.org/our-certifications/linux-essentials-overview](https://www.lpi.org/our-certifications/linux-essentials-overview)

---

## What You Learned
*   **Filesystem Hierarchy:** The logical flow of the Linux directory tree.
*   **Key Directories:** Knowing exactly where to find configuration files and logs.
*   **Root Logic:** Understanding the difference between user home and system root.
