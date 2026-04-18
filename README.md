# Security Learning Labs (2026+)

A comprehensive repository of hands-on tutorials and guides for a learning path in Cybersecurity, Cloud, DevOps, and AI-assisted Engineering.

## Project Structure

This is a sampling, it may not be updated with the latest labs.

```text
security-mentorship/
├── certifications/             # Vendor paths, salary data, and roadmap
├── labs/                       # Hands-on tutorials (organized by category)
│   ├── ai-usage/               # LLMs, prompting, AI-assisted coding, CLIs
│   ├── cloud/                  # AWS, Azure, GCP labs
│   ├── devops/                 # CI/CD, IaC (Terraform), hosting (Netlify)
│   ├── foundational/           # Linux, Git, Markdown, Networking basics
│   ├── job-hunting/            # Resume building, portfolios, interview prep
│   ├── linux/                  # Administration, hardening, and shell scripting
│   ├── network-security/       # Nmap, Burp Suite, Wireshark, pentesting
│   └── python/                 # Scripting, automation, security tools
├── reference/                  # Deep-dive conceptual material (by category)
│   ├── networking/             # Protocols (DNS, DHCP, SMTP, etc.)
│   ├── security-frameworks/    # NIST, OWASP, MITRE ATT&CK
│   └── os-internals/           # Linux/Windows deep dives
├── flashcards/                 # Study material (organized by vendor/cert)
│   ├── aws/                    # Cloud Practitioner, Security Specialty
│   ├── azure/                  # AZ-900, AZ-500
│   ├── comptia/                # Sec+, Net+, CySA+, PenTest+
│   └── cisco/                  # CCST, CyberOps
├── images/                     # Global assets (if not lab-specific)
└── README.md                   # Project index and roadmap
```

---

## Active Labs (Completed)

### Foundational
*   **AI Usage Foundations: Power User Edition:** [labs/foundational/ai-usage-fundamentals/index.md](labs/foundational/ai-usage-fundamentals/index.md)
*   **Cloud Foundations:** [labs/foundational/cloud-fundamentals/index.md](labs/foundational/cloud-fundamentals/index.md)
*   **DevOps Foundations:** [labs/foundational/devops-fundamentals/index.md](labs/foundational/devops-fundamentals/index.md)
*   **Git Foundations: Version Control:** [labs/foundational/git-version-control/index.md](labs/foundational/git-version-control/index.md)
*   **Linux Foundations: The Command Line (CLI):** [labs/foundational/linux-cli/index.md](labs/foundational/linux-cli/index.md)
*   **Linux Foundations: The Filesystem:** [labs/foundational/linux-filesystem-basics/index.md](labs/foundational/linux-filesystem-basics/index.md)
*   **Networking Foundations:** [labs/foundational/networking-fundamentals/index.md](labs/foundational/networking-fundamentals/index.md)
*   **Security Foundations:** [labs/foundational/security-fundamentals/index.md](labs/foundational/security-fundamentals/index.md)

### AI Usage
*   **Beginner Gemini CLI: AI-Powered Engineering:** [labs/ai-usage/gemini-cli/index.md](labs/ai-usage/gemini-cli/index.md)
*   **Gemini Ecosystem with Focus on Gemini CLI:** [labs/ai-usage/gemini-cli-lecture/index.md](labs/ai-usage/gemini-cli-lecture/index.md)
*   **Prompting vs. Context Prompting:** [labs/ai-usage/prompting-vs-context/index.md](labs/ai-usage/prompting-vs-context/index.md)
*   **Rapid Website Prototyping and Sales with Google AI Studio:** [labs/ai-usage/aistudio-website/index.md](labs/ai-usage/aistudio-website/index.md)

### Network Security
*   **Home Network Pentest: The Professional Lifecycle:**
    *   **Overview & Legal:** [labs/network-security/home-network-pentest/index.md](labs/network-security/home-network-pentest/index.md)
    *   **Phase 1: Discovery:** [labs/network-security/home-network-pentest/phase-1-discovery/index.md](labs/network-security/home-network-pentest/phase-1-discovery/index.md)
    *   **Phase 2: Enumeration:** [labs/network-security/home-network-pentest/phase-2-enumeration/index.md](labs/network-security/home-network-pentest/phase-2-enumeration/index.md)
    *   **Phase 3: Vulnerability Research:** [labs/network-security/home-network-pentest/phase-3-vulnerability-research/index.md](labs/network-security/home-network-pentest/phase-3-vulnerability-research/index.md)
    *   **Phase 4: Hardening:** [labs/network-security/home-network-pentest/phase-4-hardening/index.md](labs/network-security/home-network-pentest/phase-4-hardening/index.md)
    *   **Phase 5: Reporting:** [labs/network-security/home-network-pentest/phase-5-reporting/index.md](labs/network-security/home-network-pentest/phase-5-reporting/index.md)

### DevOps
*   **Static Hosting Using Github and Netlify:** [labs/devops/static-hosting-netlify/index.md](labs/devops/static-hosting-netlify/index.md)

### Job Hunting
*   **The 'Recruit the Recruiter' Protocol:** [labs/job-hunting/recruit-the-recruiter/index.md](labs/job-hunting/recruit-the-recruiter/index.md)

### Python
*   **Python venv Tutorial:** [labs/python/python-venv/index.md](labs/python/python-venv/index.md)

---

## Planned Labs (Roadmap)

This section contains all originally planned labs, sorted by category of things we are planning or considering.  

### Foundational Labs (Theory & Basics)
- **Markdown**
- **HTML**
- **Clients and Servers**
- **GitHub** (the labs and docs setup here)
- **SSH Server**
- **UFW Host Firewall**

### Raspberry Pi Setup
- **Image** (noobs/kali)
- **Wifi**
- **Power, Cables, Pins, etc**

### Core Network Services (Protocol Deep Dives)
- **Time (NTP):** Synchronizes clocks across devices; critical for logs, auth, certs
- **Name Resolution:**
    - **DNS (Domain Name System):** Translates names to IPs
    - **mDNS (Multicast DNS):** Local network discovery (.local addresses)
- **IP Address Assignment:**
    - **DHCP:** Assigns IPs, gateways, DNS to clients
    - **APIPA:** Self-assigned 169.254.x.x when DHCP fails
- **Email:**
    - **SMTP:** Sends mail between servers (port 25, 587)
    - **IMAP:** Retrieves mail, keeps on server (port 143, 993)
    - **POP3:** Retrieves mail, downloads locally (port 110, 995)
    - **SPF, DKIM, DMARC:** Email authentication and anti-spoofing
- **Web:**
    - **HTTP/HTTPS:** Web traffic (port 80, 443)
    - **TLS/SSL:** Encryption layer for HTTPS and other protocols
- **File Transfer:**
    - **FTP/SFTP:** File transfers (port 21 / 22)
    - **SCP:** Secure copy over SSH
    - **SMB/CIFS:** Windows file sharing (port 445)
    - **NFS:** Unix/Linux file sharing
- **Remote Access:**
    - **SSH:** Encrypted remote terminal (port 22)
    - **RDP:** Windows remote GUI (port 3389)
    - **VNC:** Cross-platform remote desktop
- **Directory & Authentication:**
    - **LDAP:** Directory lookups, user/group info
    - **Active Directory:** Microsoft's LDAP + Kerberos implementation
    - **Kerberos:** Ticket-based authentication
    - **RADIUS:** Network access authentication (WiFi, WiFi, VPN)
- **Network Management:**
    - **SNMP:** Monitor and manage network devices
    - **Syslog:** Centralized logging (port 514)
    - **ICMP:** Ping, traceroute, network diagnostics
- **Database:**
    - **MySQL/MariaDB** (Port 3306)
    - **PostgreSQL** (Port 5432)
    - **MongoDB** (Port 27017)
    - **Redis** (Port 6379)

### Python Labs
- **Update pip**
- **git clone**
- **File Encryptor**
- **pdf2text**
- **pirategems**
- **Python Book**

### AI Usage (Planned Projects)
- **Custom GPT**
- **Claude Project + Skill**
- **NotebookLM Podcast**
- **Rent GPU Hugging Face, Photo Shoot**
- **Create Code Page Using AI**

### Docker & Infrastructure
- **Basic Docker Container**
- **Uptime Kuma** – Self-hosted uptime monitoring
- **AdGuard Home** – Network-wide ad blocking and DNS
- **Terraform Basic VM**
- **Terraform deploy to AWS/Azure free tier**
- **GitHub Actions CI/CD pipeline**
- **Deploy container to AWS ECS or Azure Container Instances**

### Monitoring & Visibility
- **Log locations**
- **tcpdump**
- **Wireshark**
- **Suricata**
- **Wazuh**

### Network Security & Pentesting
- **DVWA** (Damn Vulnerable Web Application)
- **Juice Shop**
- **Fing**
- **Angry IP Scanner**
- **Nmap + Zenmap**
- **arp-scan**
- **Netbox / Draw.io**
- **Nikto**
- **WPScan**
- **ffuf**
- **SQLMap**
- **Burp Suite**

### Cloud Labs (Free Tier)
#### AWS Free Tier
- Create IAM users, groups, roles, policies
- Launch EC2 instance + SSH access
- Security Groups – inbound/outbound rules
- S3 bucket with access policies
- CloudWatch logs and alarms
- VPC basics – subnets, route tables, internet gateway
- AWS CLI setup and usage
- Lambda function – trigger from S3 or API Gateway

#### Azure Free Tier
- Azure Portal navigation
- Create VM + Network Security Groups
- Azure Active Directory basics
- Blob Storage with access controls
- Azure Monitor and Log Analytics
- Azure CLI / Cloud Shell
- Azure Functions

#### GCP Free Tier
- Compute Engine e2-micro instance
- Cloud Storage buckets
- IAM and service accounts
- Cloud Shell

#### Cloud Security
- **Prowler** – AWS security auditing
- **ScoutSuite** – Multi-cloud security auditing
- **Checkov** – IaC security scanning
- **Trivy** – Container and IaC vulnerability scanning
- **AWS Config** rules for compliance
- **Secrets Manager / Key Vault basics**

---

## Certifications

Generally you get foundations, then specialize in specific vendors/products afterwards. See the full roadmap and vendor paths here:

*   **Certification Roadmap:** [certifications/index.md](certifications/index.md)
