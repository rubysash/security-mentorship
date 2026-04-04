---
title: "Linux Foundations: The Command Line (CLI)"
date: 2026-04-04
description: "A comprehensive cheatsheet of essential commands for Debian and RedHat-based Linux systems."
tags: ["foundational", "linux", "cli", "cheatsheet"]
showTableOfContents: true
---

# Linux Foundations: The Command Line (CLI)

## Objective
Identify and memorize the essential commands required to navigate, manage, and troubleshoot Linux systems from the terminal.

## Legal & Ethical Disclaimer
**FOR EDUCATIONAL USE ONLY.** Only execute these commands on systems you own or have explicit permission to manage. Commands like `rm -rf` or package installations can permanently modify or damage a system if used incorrectly.

## Prerequisites
- Access to a Linux terminal (Raspberry Pi or WSL).
- Completion of the **Linux Foundations: The Filesystem** lab.

## Why This Matters
The GUI (Graphical User Interface) is for consumers; the CLI is for professionals. Whether you are automating a cloud deployment or performing a forensic analysis, you must be comfortable working in a text-based environment.

---

## Linux CLI Cheatsheet

### File and Directory Navigation
| Command | Description |
|---------|-------------|
| `pwd` | Print Working Directory (shows exactly where you are). |
| `ls -la` | List all files, including hidden ones, with detailed info. |
| `cd <DIRECTORY>` | Change directory. |
| `mkdir <NAME>` | Create a new directory. |
| `rm -r <NAME>` | Remove a file or directory recursively. |
| `cp -r <SRC> <DEST>` | Copy a file or directory. |
| `mv <SRC> <DEST>` | Move or rename a file or directory. |

### System Information and Management
| Command | Description |
|---------|-------------|
| `top` or `htop` | Monitor system resources and running processes. |
| `df -h` | Show disk space usage in human-readable format. |
| `du -sh` | Show the size of a specific directory. |
| `uname -a` | Show detailed system and kernel information. |
| `uptime` | Show how long the system has been running. |
| `sudo` | Execute a command with superuser (root) privileges. |

### Networking Basics
| Command | Description |
|---------|-------------|
| `ip addr` | Show all network interfaces and IP addresses. |
| `ip route` | Show the system routing table (default gateway). |
| `ping <TARGET>` | Test connectivity to a host. |
| `ss -tulpn` | Show all listening ports and active connections. |
| `curl -I <URL>` | Fetch the HTTP headers of a URL. |

### Package Management (The Big Two)
Linux distributions use different managers. Most labs in this project use **Debian/Apt**.

| Task | Debian / Ubuntu / Pi OS (APT) | RedHat / Fedora / Alma (DNF) |
|------|-------------------------------|------------------------------|
| Update Cache | `sudo apt update` | `sudo dnf check-update` |
| Upgrade All | `sudo apt upgrade` | `sudo dnf upgrade` |
| Install Tool | `sudo apt install <TOOL>` | `sudo dnf install <TOOL>` |
| Remove Tool | `sudo apt remove <TOOL>` | `sudo dnf remove <TOOL>` |
| Search Tool | `apt search <KEYWORD>` | `dnf search <KEYWORD>` |

### File Content and Searching
| Command | Description |
|---------|-------------|
| `cat <FILE>` | Display the entire contents of a file. |
| `grep "<PATTERN>" <FILE>` | Search for a specific string within a file. |
| `tail -f <FILE>` | Follow a file in real-time (Great for watching logs in `/var/log`). |
| `find / -name <NAME>` | Search the entire system for a file by name. |
| `nano <FILE>` | A simple, beginner-friendly text editor. |
| `vi` or `vim` | The industry-standard advanced text editor. |

---

## Learning Resources

### YouTube Channels to Follow
*   **Linux Overdose:** [https://www.youtube.com/@LinuxOverdose](https://www.youtube.com/@LinuxOverdose) (Quick command tips).
*   **Learn Linux TV:** [https://www.youtube.com/@LearnLinuxTV](https://www.youtube.com/@LearnLinuxTV) (Comprehensive Bash tutorials).
*   **NetworkChuck:** [https://www.youtube.com/@NetworkChuck](https://www.youtube.com/@NetworkChuck) (Linux for Beginners series).

### Online Manuals
*   **Linux Command Library:** [https://linuxcommandlibrary.com/](https://linuxcommandlibrary.com/)
*   **ExplainShell:** [https://explainshell.com/](https://explainshell.com/) (Paste a command to see exactly what each flag does).

---

## What You Learned
*   **Navigation:** How to move through the Linux hierarchy.
*   **Package Management:** The difference between `apt` and `dnf`.
*   **Troubleshooting:** Essential commands for checking disk space, networking, and logs.
*   **Editing:** Basic familiarity with terminal-based text editors.
