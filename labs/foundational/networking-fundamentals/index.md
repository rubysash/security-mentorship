---
title: "Networking Foundations"
date: 2026-04-04
description: "Master the vocabulary and concepts of the OSI model, routing, switching, and address assignment."
tags: ["foundational", "networking", "theory"]
showTableOfContents: true
---

# Networking Foundations

## Objective
Memorize and understand the key protocols, addressing schemes, and the 7-layer OSI model used in modern computer networks.

## Legal & Ethical Disclaimer
**FOR EDUCATIONAL USE ONLY.** Unauthorized network scanning or probing is illegal. These concepts are to be practiced only on personal or authorized test environments.

## Prerequisites
- A desire to understand how the internet actually works.

## Why This Matters
Networking is the foundation of everything. Whether you're configuring a Cloud VPC, securing a server, or deploying a DevOps pipeline, you're working with the OSI model, IP addresses, and ports.

---

## The OSI Model (The Language of the Internet)
Memorize these 7 layers. They are the universal framework for troubleshooting and communication.

*   **Layer 7 - Application:** What the user interacts with.
    *   *Examples:* HTTP, HTTPS, DNS, SSH, SMTP, FTP.
*   **Layer 6 - Presentation:** Data encryption, compression, and translation.
    *   *Examples:* SSL/TLS, JPEG, GIF, MPEG, ASCII.
*   **Layer 5 - Session:** Manages the start, stop, and restart of connections.
    *   *Examples:* NetBIOS, RPC, Sockets.
*   **Layer 4 - Transport:** How data moves across the network.
    *   *Examples:* TCP (Reliable), UDP (Fast).
*   **Layer 3 - Network:** Where logical addressing and routing happen.
    *   *Examples:* IPv4, IPv6, ICMP (Ping), IPSec, Routers.
*   **Layer 2 - Data Link:** Where physical addressing (MAC) and switching happen.
    *   *Examples:* Ethernet, MAC Addresses, ARP, Switches, Wi-Fi (802.11).
*   **Layer 1 - Physical:** The actual cables and electrical signals.
    *   *Examples:* Fiber Optics, CAT6 Cables, Hubs, Repeaters.

---

## Core Vocabulary and Concepts

### The TCP 3-Way Handshake
This is the "handshake" used to establish a reliable connection (Layer 4).
*   **SYN (Synchronize):** Client asks to connect.
*   **SYN-ACK (Synchronize-Acknowledge):** Server acknowledges and asks to connect back.
*   **ACK (Acknowledge):** Client confirms connection is established.

### IP Addressing and Subnetting
*   **IP Address (IPv4):** A 32-bit logical identifier (e.g., `192.168.1.1`).
*   **Subnet Mask:** Defines the network vs. host portion (e.g., `/24`).
*   **Default Gateway:** The router IP used to exit your local network.

### Core Protocols
*   **DNS (Domain Name System):** Resolves names to IPs.
*   **DHCP (Dynamic Host Configuration Protocol):** Automatically assigns IP addresses.
*   **VLAN (Virtual LAN):** Logically separating devices on a physical switch.

### Common Ports (The "Doors")
*   **Port 22:** SSH (Secure Remote Access)
*   **Port 53:** DNS (Name Resolution)
*   **Port 80/443:** HTTP/HTTPS (Web Traffic)
*   **Port 445:** SMB (Windows File Sharing)

---

## Learning Resources

### YouTube Channels to Follow
*   **Jeremy's IT Lab:** [https://www.youtube.com/@JeremysITLab](https://www.youtube.com/@JeremysITLab)
*   **Professor Messer:** [https://www.youtube.com/@professormesser](https://www.youtube.com/@professormesser)
*   **NetworkChuck:** [https://www.youtube.com/@NetworkChuck](https://www.youtube.com/@NetworkChuck)

### Udemy Search Terms
*   "CompTIA Network+ N10-008" (Jason Dion)
*   "Cisco CCNA 200-301" (Neil Anderson)

---

## Recommended Certifications
*   **CompTIA Network+:** [https://www.comptia.org/certifications/network](https://www.comptia.org/certifications/network)
*   **Cisco CCNA (200-301):** [https://www.cisco.com/c/en/us/training-events/training-certifications/certifications/associate/ccna.html](https://www.cisco.com/c/en/us/training-events/training-certifications/certifications/associate/ccna.html)

---

## What You Learned
*   **OSI Layers:** Troubleshooting from Layer 1 to Layer 7.
*   **Handshakes:** How TCP establishes reliable connections.
*   **Addressing:** The roles of IP, Subnetting, and DNS.
