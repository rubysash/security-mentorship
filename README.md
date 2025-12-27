# Security Learning Labs

I'll be adding tutorials, but here are some of the planned ones.

## Foundational Labs

- Markdown
- HTML
- Clients and Servers
- GitHub (the labs and docs setup here)
- SSH Server
- UFW Host Firewall
- Linux Commands

## Core Network Services

Understanding the protocols that make everything work.

### Time

- **NTP (Network Time Protocol)** – Synchronizes clocks across devices; critical for logs, auth, certs

### Name Resolution

- **DNS (Domain Name System)** – Translates names to IPs
- **mDNS (Multicast DNS)** – Local network discovery (.local addresses)

### IP Address Assignment

- **DHCP (Dynamic Host Configuration Protocol)** – Assigns IPs, gateways, DNS to clients
- **APIPA** – Self-assigned 169.254.x.x when DHCP fails

### Email

- **SMTP (Simple Mail Transfer Protocol)** – Sends mail between servers (port 25, 587)
- **IMAP (Internet Message Access Protocol)** – Retrieves mail, keeps on server (port 143, 993)
- **POP3 (Post Office Protocol)** – Retrieves mail, downloads locally (port 110, 995)
- **SPF, DKIM, DMARC** – Email authentication and anti-spoofing

### Web

- **HTTP/HTTPS** – Web traffic (port 80, 443)
- **TLS/SSL** – Encryption layer for HTTPS and other protocols

### File Transfer

- **FTP/SFTP** – File transfers (port 21 / 22)
- **SCP** – Secure copy over SSH
- **SMB/CIFS** – Windows file sharing (port 445)
- **NFS** – Unix/Linux file sharing

### Remote Access

- **SSH (Secure Shell)** – Encrypted remote terminal (port 22)
- **RDP (Remote Desktop Protocol)** – Windows remote GUI (port 3389)
- **VNC** – Cross-platform remote desktop

### Directory & Authentication

- **LDAP (Lightweight Directory Access Protocol)** – Directory lookups, user/group info
- **Active Directory** – Microsoft's LDAP + Kerberos implementation
- **Kerberos** – Ticket-based authentication
- **RADIUS** – Network access authentication (WiFi, VPN)

### Network Management

- **SNMP (Simple Network Management Protocol)** – Monitor and manage network devices
- **Syslog** – Centralized logging (port 514)
- **ICMP** – Ping, traceroute, network diagnostics

### Database

- **MySQL/MariaDB** – Port 3306
- **PostgreSQL** – Port 5432
- **MongoDB** – Port 27017
- **Redis** – Port 6379

## Python Labs

- Update pip
- git clone
- venv
- File Encryptor
- pdf2text
- pirategems
- Python Book

## GitHub Labs

- GitHub simple docs in markdown
- git scm basics
- Collaboration

## AI Usage Labs

- Custom GPT
- Gemini Gem
- Claude Project + Skill
- NotebookLM
- NotebookLM Podcast
- Rent GPU Hugging Face, Photo Shoot
- Create Code Page Using AI


## Docker Labs

- Basic Docker Container
- Uptime Kuma – Self-hosted uptime monitoring
- AdGuard Home – Network-wide ad blocking and DNS

## Visibility Labs

- Log locations
- tcpdump
- Wireshark
- Suricata
- Wazuh

## Network Security Labs

- DVWA
- Juice Shop
- Fing
- Angry IP Scanner
- Nmap + Zenmap
- arp-scan
- Netbox / Draw.io
- Nikto
- WPScan
- ffuf
- SQLMap
- Burp Suite

## DevOps Labs (part 1)

- Netlify.app the code page with GitHub trigger
- Hugo Local Site to GitHub, Netlify
- Domain Name + Hugo
- OWASP ZAP or Nikto to scan DVWA

## DevOps Labs (part 2)

- Terraform Basic VM
- Terraform deploy to AWS/Azure free tier
- GitHub Actions CI/CD pipeline
- Deploy container to AWS ECS or Azure Container Instances


## Cloud Labs (Free Tier)

### AWS Free Tier

- Create IAM users, groups, roles, policies
- Launch EC2 instance + SSH access
- Security Groups – inbound/outbound rules
- S3 bucket with access policies
- CloudWatch logs and alarms
- VPC basics – subnets, route tables, internet gateway
- AWS CLI setup and usage
- Lambda function – trigger from S3 or API Gateway

### Azure Free Tier

- Azure Portal navigation
- Create VM + Network Security Groups
- Azure Active Directory basics
- Blob Storage with access controls
- Azure Monitor and Log Analytics
- Azure CLI / Cloud Shell
- Azure Functions

### GCP Free Tier

- Compute Engine e2-micro instance
- Cloud Storage buckets
- IAM and service accounts
- Cloud Shell

### Cloud Security Labs

- Prowler – AWS security auditing
- ScoutSuite – Multi-cloud security auditing
- Checkov – IaC security scanning
- Trivy – Container and IaC vulnerability scanning
- AWS Config rules for compliance
- Secrets Manager / Key Vault basics



## Certifications

Generally you get foundations, then specialize in specific vendors/products afterwards.  Certs "expire" but are easy to renew.    I have 31 certifications.   Far more than a degree, the certs opened doors.

### Entry Level (Start Here)

- **AWS Cloud Practitioner (CLF-C02)** – Cloud fundamentals
- **Azure Fundamentals (AZ-900)** – Microsoft cloud basics
- **LPI Linux Essentials** – Linux basics (free exam objectives)
- **CompTIA A+** – IT fundamentals, hardware, troubleshooting
- **CompTIA Network+** – Networking concepts, protocols, infrastructure

### Security Foundations

- **CompTIA Security+** – Industry standard entry security cert
- **CompTIA Linux+** – Deeper Linux administration
- **Cisco Certified Support Technician (CCST) Cybersecurity** – Entry-level Cisco path

### Intermediate Security

- **CompTIA CySA+** – Blue team, SOC analyst focus
- **CompTIA PenTest+** – Offensive security basics
- **AWS Security Specialty** – Cloud security
- **Azure Security Engineer (AZ-500)** – Microsoft security
- **Cisco CyberOps Associate** – SOC and defense

### Suggested Path

1. Network+ → Security+ → CySA+ (defensive track)
2. Network+ → Security+ → PenTest+ → OSCP (offensive track)
3. AWS Cloud Practitioner → AWS Security Specialty (cloud track)
