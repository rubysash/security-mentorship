---
title: "Advanced Network Discovery and Data-Driven Diagramming"
date: 2026-04-04
description: "Discover local subnets and hidden VLANs, then use AI to generate structured data for automated network mapping."
tags: ["network-security", "nmap", "masscan", "vlan", "ai", "diagramming"]
showTableOfContents: true
---

# Advanced Network Discovery and Data-Driven Diagramming

## Objective
By the end of this lab, you will have identified all devices on your local network and any accessible VLANs/subnets. You will then use AI to transform these raw scan results into a structured format for automated diagramming.

## Legal & Ethical Disclaimer
**PROCEED WITH CAUTION.** Network scanning and probing are highly intrusive activities. You are strictly authorized to perform these actions ONLY on equipment and networks that you own (e.g., your personal home router, Raspberry Pi, or private lab). 

Probing a network you do not own—such as your employer's, school's, or a public Wi-Fi—is often a violation of terms of service and can be considered a criminal act. High-speed scanning (Phase 1) can also disrupt network services; never perform this on a production network.

## Prerequisites
- A **Raspberry Pi** (preferred) or **WSL**.
- Connection to a network with potential VLANs (e.g., Guest Wi-Fi, IoT subnet, or a lab environment).

## Why This Matters
Finding hidden subnets or "leaky" VLANs is a critical skill for both security auditing and network troubleshooting. Moving from manual "drawing" to "data-driven" mapping is the industry standard for managing enterprise-scale infrastructure.

## Tool Selection Guide
In a professional engagement, choosing the right tool for the specific layer and speed requirement is key.

*   **arp-scan (Layer 2 - MAC):** Ultra fast. Best for finding everything on your *immediate* subnet or Wi-Fi.
*   **masscan (Layer 3 - IP):** Extreme speed. Best for rapidly finding live IPs and ports across huge ranges (VLANs or the Internet).
*   **nmap (Layer 3/4):** Moderate speed. Best for deep enumeration, OS detection, and vulnerability scripting.

---

## Local and Cross-VLAN Discovery

### Local Subnet Discovery
Use `arp-scan` to identify devices on your immediate segment.
```bash
sudo arp-scan --localnet
```

### Across VLANs Discovery
If you suspect other subnets (like `10.0.0.0/8` or `192.168.0.0/16`), `nmap` is too slow for the initial sweep. `masscan` is a stateless scanner that can find live hosts across massive ranges in seconds.

> **Warning:** Masscan is highly aggressive and will trigger alarms in hardened environments.

```bash
# -p0: Check if the IP is alive (ping-only)
# --rate 5000: Send 5000 packets per second
# --exclude: Avoid scanning your own IP or sensitive gateways
sudo masscan 192.168.0.0/16 10.0.0.0/8 -p0 --rate 5000 -oG live_hosts_masscan.txt
```

---

## The Logical Pentester Workflow
A real pentester follows a structured multi-phase approach: **Discovery**, **Targeting**, and **Deep Enumeration**.

### Phase 1: High-Speed Discovery
Identify which IP addresses are actually assigned to a device using a Ping Sweep.

```bash
# -sn: Ping scan (no port scanning)
# -PE: ICMP echo request
# -n: No DNS resolution (saves time)
# --min-rate 5000: High-speed throughput
sudo nmap -sn -PE -n --min-rate 5000 192.168.0.0/16 10.0.0.0/16 -oG - | awk '/Up$/{print $2}' > live_ips.txt
```

### Phase 2: Targeted Enumeration (Juicy Ports)
Once you have the `live_ips.txt` list, check them for high-value administrative services and shares.

```bash
# -iL: Use the live host list as input
# -p: Scan only the "Juicy" admin/share ports
# --open: Only show hosts with at least one port open
# -sV: Service version detection
sudo nmap -iL live_ips.txt -p 22,80,443,445,3389 --open -sV
```

**Pentester Logic for Juicy Ports:**
*   **22 (SSH):** Remote terminal access for Linux/Network gear.
*   **80/443 (HTTP/S):** Web admin portals.
*   **445 (SMB):** File shares (primary target for data).
*   **3389 (RDP):** Windows Remote Desktop.

### Phase 3: The Deep Dive (Vulnerabilities)
If juicy ports are open, perform deep fingerprinting to identify potential vulnerabilities.

```bash
# -sV: Service Version detection
# -O: OS Fingerprinting
# --script vuln: Check for known vulnerabilities
# --script http-headers: Grab web server metadata
sudo nmap -sV -O --script vuln,http-headers -p 22,80,443,445,3389 <TARGET_IP>
```

---

## Scope Expansion Strategy
If your targeted scan yields nothing, you must expand your scope to find services on non-standard ports.

*   **Top 1000 Ports:** Scan the most common 1000 ports (Nmap default).
    ```bash
    sudo nmap -iL live_ips.txt -sV --top-ports 1000
    ```
*   **Full Port Scan (65,535):** Scan every possible port.
    ```bash
    # -p-: Scan all 65,535 ports
    # -T4: Aggressive timing (faster but noisier)
    sudo nmap -iL live_ips.txt -p- -T4
    ```

---

## Professional Stealth and Evasion
High-speed scans are noisy and will trigger **IDS (Intrusion Detection Systems)**. In a professional engagement, stealth is often required to avoid being blocked.

### Evasion Techniques
To avoid detection, slow down the scan and fragment the traffic.

```bash
# -sS: Stealthy TCP SYN scan (half-open)
# -T2 (Polite): Slows down the scan to stay under the radar
# -f: Fragment packets to bypass simple firewalls
# --data-length 24: Appends random data to change packet signatures
sudo nmap -sS -T2 -f --data-length 24 <TARGET_IP>
```

### Decoy Scanning
Mask your identity by blending in with decoy traffic.
```bash
# -D RND:10: Generate 10 random decoy IP addresses alongside your own
sudo nmap -sS -T2 -D RND:10 <TARGET_IP>
```

---

## The AI Data Workflow
Modern workflows use AI to bridge the gap between terminal output and professional documentation.

### Step 1: Export Results
Export your final deep-dive findings into a format the AI can easily parse.
```bash
# -oG: Grepable output format
sudo nmap -sV -O --top-ports 100 -oG scan_results.txt <TARGET_RANGE>
```

### Step 2: AI Transformation (The Master Prompt)
Paste your `scan_results.txt` into an LLM (Gemini, Claude, or ChatGPT) with the following "Master Prompt" to structure your data:

> "Act as a Senior Network Security Architect. I have provided raw Nmap scan results in grepable format. 
> 
> 1. Transform this data into a clean CSV table with columns: [IP, MAC, Manufacturer, OS, Open Ports, Service].
> 2. Then, convert that table into a structured JSON array for a network visualization tool like the sample I'm uploading (upload a sample json from the python-diagram tool). Each object must include: 'id' (the IP), 'label' (the OS or Manufacturer), and 'type' (choose from: gateway, server, workstation, iot, mobile).
> 3. Ensure the JSON is valid and the CSV is properly delimited."

or create a mermaid diagram [https://mermaid.live/](https://mermaid.live/) if you do not have the [https://github.com/rubysash/python-diagrams](https://github.com/rubysash/python-diagrams) tool installed.

Once the AI has structured your data, use this specific prompt to generate a visual representation for your documentation:

> "Now, using the data we just structured, generate a Mermaid.js 'graph TD' diagram. 
> - Use a cloud icon for the Internet.
> - Represent the Router as a central hub.
> - Group devices into subnets or categories (e.g., IoT, Workstations) using subgraphs.
> - Use different styles or colors for each category.
> - Ensure the syntax is clean and ready for a Markdown file."

---

## Automated Visualization
*   **JSON Tool:** Import the generated JSON array into your specialized diagramming tool for a dynamic, interactive view.
*   **Markdown Documentation:** Copy and paste the Mermaid code directly into your lab report or GitHub README to render a professional, static network topology.

---

## What You Learned
*   **Layered Discovery:** Using the right tool for local vs. cross-VLAN segments.
*   **Structured Methodology:** Moving from discovery to deep enumeration logically.
*   **Stealth Tactics:** Applying evasion and decoy techniques for real-world scenarios.
*   **Data-Driven Mapping:** Using AI to automate professional documentation.
