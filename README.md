# Business IT Stack

> [!NOTE]
> **This is a conceptual business IT stack, not a representation of my current company's infrastructure, tools, or security posture.** The services and recommendations listed here are illustrative and would be adapted to the specific needs, requirements, budget, and operational constraints of an organization's IT department.


A minimal self-hosted business infrastructure stack focused on IT asset management, documentation, monitoring, security, and operational reliability. Designed to reduce licensing costs while maintaining visibility and control over business IT resources.

## Microsoft Enterprise Stack

| Category | Name / Link | Purpose | Deployment |
| -------- | ----------- | ------- | ---------- |
| Identity Management | [Microsoft Entra ID](https://www.microsoft.com/en-us/security/business/identity-access/microsoft-entra-id) | Cloud identity, SSO, MFA, and conditional access | Cloud |
| Device Management | [Microsoft Intune](https://intune.microsoft.com/) | Manage Windows devices, mobile devices, compliance policies, and application deployments | Cloud |
| Productivity | [Microsoft 365](https://www.microsoft.com/microsoft-365/business) | Business email, Office applications, Teams, and collaboration | Cloud |
| Endpoint Security | [Microsoft Defender for Business](https://www.microsoft.com/en-us/security/business/endpoint-security/microsoft-defender-business) | Endpoint protection, threat detection, and response | Cloud |
| Identity Protection | [Microsoft Entra ID Protection](https://learn.microsoft.com/en-us/entra/id-protection/overview-identity-protection) | Identify risky sign-ins and compromised identities | Cloud |
| Security Management | [Microsoft Defender XDR](https://www.microsoft.com/en-us/security/business/siem-and-xdr/microsoft-defender-xdr) | Correlate security signals across supported Microsoft security products | Cloud |
| SIEM / SOAR | [Microsoft Sentinel](https://azure.microsoft.com/en-us/products/microsoft-sentinel) | Centralized security analytics, incident investigation, and automated response | Azure |
| Data Protection | [Microsoft Purview](https://www.microsoft.com/en-us/security/business/microsoft-purview) | Data governance, information protection, retention, and compliance capabilities | Cloud |

## IT Management & Documentation

| Category | Name / Link | Purpose | Server |
| -------- | ----------- | ------- | ------ |
| Asset Management | [Snipe-IT](https://snipeitapp.com/) | Track hardware assets, serial numbers, assignments, warranties, and software licenses | Docker |
| Documentation | [BookStack](https://www.bookstackapp.com/) | Centralized IT documentation, procedures, and troubleshooting guides | Docker |
| IP Address Management | [NetBox](https://netboxlabs.com/) | Document IP addresses, subnets, VLANs, devices, and network infrastructure | Docker |
| Password Management | [Bitwarden](https://bitwarden.com/) | Centralized credential management for supported business use cases | Cloud / Self-hosted |

## Monitoring & Operations

| Category | Name / Link | Purpose | Server |
| -------- | ----------- | ------- | ------ |
| Uptime Monitoring | [Uptime Kuma](https://uptime.kuma.pet/) | Monitor service availability and alert on outages | Docker |
| Container Management | [Portainer](https://www.portainer.io/) | Manage Docker containers and application stacks | Docker |
| Log Management | [Graylog](https://graylog.org/) | Centralized collection and analysis of system and application logs | Docker |
| Automation | [Ansible](https://www.ansible.com/) | Automate server configuration, deployments, and routine administration | Linux VM |

## Security & Access Control

| Category | Name / Link | Purpose | Server |
| -------- | ----------- | ------- | ------ |
| Identity Management | [Microsoft Entra ID](https://www.microsoft.com/en-us/security/business/identity-access/microsoft-entra-id) | Cloud identity, SSO, MFA, and conditional access | Cloud |
| Security Monitoring | [Wazuh](https://wazuh.com/) | Endpoint security monitoring, log analysis, and threat detection | Linux VM |
| Reverse Proxy | [Nginx Proxy Manager](https://nginxproxymanager.com/) | Manage reverse proxy routes and TLS certificates | Docker |
| Remote Access | [Tailscale](https://tailscale.com/) | Secure remote administration without directly exposing management interfaces | Linux VM |
| DNS Filtering | [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) | DNS filtering and domain-based blocking | Linux VM |

## Backup & Disaster Recovery

| Category | Name / Link | Purpose | Server |
| -------- | ----------- | ------- | ------ |
| Backup Management | [Proxmox Backup Server](https://www.proxmox.com/en/products/proxmox-backup-server/overview) | Deduplicated backups of Proxmox VMs and containers | Dedicated backup host |
| Configuration Backup | [Restic](https://restic.net/) | Encrypted, versioned backups of application data and configuration files | Backup host |
| Offsite Storage | Microsoft Azure | Offsite storage for encrypted backup copies | Cloud |

## Coming Soon

| Name | Purpose |
| ---- | ------- |
| Automated Asset Discovery | Discover and reconcile devices against the Snipe-IT inventory |
| Configuration Compliance | Standardize server configurations and identify configuration drift with Ansible |
| Centralized Alerting | Consolidate monitoring and security alerts into a single notification workflow |
| Disaster Recovery Testing | Schedule restoration tests to verify that backups are usable |

## Deployment Principles

- **Least Privilege** — Restrict administrative access to authorized personnel and separate management access from public-facing services.
- **Minimal Exposure** — Avoid exposing management interfaces directly to the internet; use controlled remote access.
- **Centralized Documentation** — Maintain current network diagrams, asset records, procedures, and recovery instructions.
- **Automated Operations** — Use repeatable configuration management and scheduled backups to reduce manual work.
- **Defense in Depth** — Combine identity controls, endpoint monitoring, logging, patch management, and tested recovery procedures.
