# Enterprise Log Monitoring System

> An enterprise-grade Security Information and Event Management (SIEM) project built using **Wazuh**, **Windows Server 2022**, **Sysmon**, and **Ubuntu Server**. This project demonstrates real-world Security Operations Center (SOC) monitoring, detection engineering, threat hunting, attack simulation, and security dashboard development.

---

## Project Overview

This project simulates a modern enterprise Security Operations Center (SOC) by collecting, analyzing, and monitoring security events from Windows and Linux systems.

The environment includes Windows Server 2022 monitored with Sysmon and Wazuh Agent, Ubuntu Server running the Wazuh Manager, and Kali Linux for controlled attack simulations. Custom detection rules, MITRE ATT&CK mapping, and professional dashboards provide visibility into security incidents.

---

## Features

- Enterprise SIEM deployment using Wazuh
- Windows Server 2022 monitoring
- Ubuntu Server monitoring
- Sysmon integration
- Windows Advanced Audit Policy configuration
- Custom Wazuh detection rules
- MITRE ATT&CK mapping
- Authentication monitoring
- Endpoint activity monitoring
- Threat detection dashboards
- Incident response dashboards
- Attack simulation using Kali Linux
- Security event investigation
- Detection engineering

---

# Architecture

```
                    Internet
                         │
                  Kali Linux (Attacker)
                         │
          ┌──────────────┴──────────────┐
          │                             │
 Windows Server 2022              Ubuntu Server
 Sysmon + Wazuh Agent            Wazuh Manager
                                 Wazuh Dashboard
                                 Wazuh Indexer
```

---

# Technology Stack

| Category | Technologies |
|----------|--------------|
| SIEM | Wazuh |
| Operating System | Ubuntu Server |
| Endpoint | Windows Server 2022 |
| Monitoring | Sysmon |
| Attack Machine | Kali Linux |
| Dashboard | Wazuh Dashboard |
| Detection | Custom Wazuh Rules |
| Framework | MITRE ATT&CK |
| Network Analysis | Nmap |
| Brute Force Testing | Hydra |

---

# Project Structure

```
Enterprise-Log-Monitoring-System/

├── architecture/
│   ├── architecture-diagram.png
│   └── architecture.md
│
├── dashboards/
│   ├── soc-overview/
│   ├── authentication-monitoring/
│   ├── windows-security/
│   └── threat-detection/
│
├── detection-rules/
│   ├── local_rules.xml
│   └── rules-documentation.md
│
├── attack-scenarios/
│   ├── brute-force.md
│   ├── powershell.md
│   ├── port-scan.md
│   ├── certutil.md
│   └── rundll32.md
│
├── docs/
│   ├── installation.md
│   ├── windows-agent.md
│   ├── sysmon.md
│   ├── dashboards.md
│   └── custom-rules.md
│
├── screenshots/
│
├── reports/
│
├── README.md
└── LICENSE
```

---

# Lab Environment

| Machine | Purpose |
|----------|---------|
| Ubuntu Server | Wazuh Manager, Indexer, Dashboard |
| Windows Server 2022 | Endpoint Monitoring |
| Kali Linux | Attack Simulation |

---

# Security Monitoring

The platform continuously monitors:

- Authentication Events
- Process Creation
- PowerShell Activity
- Registry Changes
- File Creation
- Network Connections
- DNS Queries
- User Account Management
- Privilege Escalation
- Failed Login Attempts

---

# Custom Detection Rules

Implemented custom detection rules for:

- Windows Brute Force Detection
- Encoded PowerShell Execution
- New Administrator Account Creation
- Port Scan Detection
- Certutil Execution
- Bitsadmin Execution
- Rundll32 Execution

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1110 | Brute Force |
| T1059.001 | PowerShell |
| T1046 | Network Service Discovery |
| T1105 | Ingress Tool Transfer |
| T1136 | Create Account |
| T1197 | Bits Jobs |
| T1218.011 | Rundll32 |

---

# Dashboards

## SOC Overview

- Total Alerts
- Critical Alerts
- High Severity Alerts
- Active Agents
- Alerts Timeline
- Alerts by Severity
- Top Alert Rules
- Top MITRE Techniques

---

## Authentication Monitoring

- Successful Logins
- Failed Logins
- Account Lockouts
- RDP Logins
- Authentication Timeline
- Top Targeted Users
- Top Source IPs

---

## Windows Security Monitoring

- Process Creation
- PowerShell Activity
- DNS Queries
- Network Connections
- Process Timeline
- Top Executed Processes
- Recent Sysmon Events

---

## Threat Detection & Incident Response

- Critical Alerts
- High Severity Alerts
- Custom Rule Hits
- Attack Timeline
- MITRE ATT&CK Coverage
- Top Custom Rules
- Recent Security Incidents

---

# Attack Simulations

The following attacks were simulated in a controlled lab environment:

- Windows Brute Force
- PowerShell Execution
- Encoded PowerShell Commands
- Nmap Port Scanning
- Administrator Account Creation
- Certutil Abuse
- Rundll32 Execution
- Bitsadmin Execution

---

# Skills Demonstrated

- Security Operations Center (SOC)
- Security Information and Event Management (SIEM)
- Detection Engineering
- Endpoint Security Monitoring
- Windows Event Log Analysis
- Linux Log Monitoring
- Incident Detection
- Threat Hunting
- MITRE ATT&CK
- Windows Server Administration
- Security Dashboard Development

---


# Screenshots

## SOC Overview Dashboard

<img width="1918" height="1076" alt="Screenshot 2026-07-05 180745" src="https://github.com/user-attachments/assets/c2542eb9-4df6-4c34-97fa-24b3991ef7a1" />

---

## Authentication Dashboard

<img width="1918" height="1073" alt="Screenshot 2026-07-05 180830" src="https://github.com/user-attachments/assets/b644fd95-ff03-4dbd-85f0-86ccf2d9beba" />


---


## Windows Security Dashboard

<img width="1919" height="1079" alt="Screenshot 2026-07-05 180925" src="https://github.com/user-attachments/assets/39e6410b-6282-4b76-b1f1-a60f16d28aa8" />

---

## Threat Detection Dashboard

<img width="1919" height="1065" alt="Screenshot 2026-07-05 182131" src="https://github.com/user-attachments/assets/ad937918-1e49-4e03-971f-50816b8546ae" />


---

# Future Improvements

- Threat Intelligence Integration (VirusTotal)
- AbuseIPDB Integration
- Automated Incident Reports
- Python SOC Automation
- Email Alerting
- Slack Notifications
- Telegram Notifications
- Active Response Automation

---

# Learning Outcomes

This project provided hands-on experience with enterprise log monitoring, detection engineering, SOC workflows, Windows event analysis, custom rule creation, and attack simulation in a controlled lab environment.

---

## Author

**Umed Ali**

Cybersecurity | Blue Team | SOC | Detection Engineering

GitHub: https://github.com/ecstaticumed

LinkedIn: https://www.linkedin.com/in/ecstaticumed

---

## License

This project is licensed under the MIT License.
