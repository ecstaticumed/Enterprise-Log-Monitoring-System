# System Architecture

## Overview

The **Enterprise Log Monitoring System** is designed to simulate a modern Security Operations Center (SOC) environment. It centralizes security event collection, monitoring, detection, and visualization using **Wazuh** as the SIEM platform.

The environment consists of three virtual machines:

- **Ubuntu Server** hosting the Wazuh Manager, Indexer, API, and Dashboard.
- **Windows Server 2022** acting as the monitored enterprise endpoint with Sysmon and the Wazuh Agent.
- **Kali Linux** serving as the attack simulation machine to generate realistic security events.

This architecture demonstrates how enterprise SOC teams collect telemetry, detect threats, and investigate security incidents.

---

# High-Level Architecture

```
                                   Enterprise Log Monitoring System

                                             Internet
                                                 │
                                                 │
                                    +-------------------------+
                                    |       Kali Linux        |
                                    |   Attack Simulation     |
                                    | Nmap • Hydra • PowerShell|
                                    +-----------+-------------+
                                                │
                              Attack Traffic & Security Events
                                                │
      --------------------------------------------------------------------------
                                                │
                           +--------------------+--------------------+
                           |                                         |
              +------------v------------+               +------------v------------+
              |   Windows Server 2022   |               |      Ubuntu Server      |
              |-------------------------|               |-------------------------|
              | Wazuh Agent             |               | Wazuh Manager           |
              | Sysmon                 |               | Wazuh API               |
              | Windows Event Logs     |-------------->| Wazuh Indexer           |
              | Advanced Audit Policy  |               | Wazuh Dashboard         |
              +-------------------------+               +-------------------------+
                                                           │
                                                           │
                                               SOC Monitoring Dashboard
                                                           │
                                                           │
                                              Security Analysts / Administrator
```

---

# Architecture Components

## 1. Ubuntu Server

The Ubuntu Server functions as the centralized SIEM infrastructure.

### Installed Components

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Wazuh API

### Responsibilities

- Collect endpoint logs
- Analyze security events
- Apply detection rules
- Generate alerts
- Store indexed events
- Provide dashboards
- Support threat hunting

---

## 2. Windows Server 2022

Windows Server 2022 represents an enterprise production server.

### Installed Components

- Wazuh Agent
- Sysmon
- Windows Advanced Audit Policy

### Collected Telemetry

- Authentication Events
- Process Creation
- PowerShell Activity
- Network Connections
- DNS Queries
- Registry Changes
- File Creation
- User Management Events
- Privilege Escalation Events

---

## 3. Kali Linux

Kali Linux is used exclusively for attack simulation within the isolated lab environment.

### Security Tools

- Nmap
- Hydra
- Netcat
- PowerShell Testing
- Network Utilities

### Simulated Attacks

- Port Scanning
- Brute Force Attacks
- Reconnaissance
- Network Enumeration
- Service Discovery

---

# Data Flow

```
Attack Generated

        │

        ▼

Windows Server 2022

(Sysmon + Event Logs)

        │

        ▼

Wazuh Agent

        │

        ▼

Wazuh Manager

        │

        ▼

Rule Processing

        │

        ▼

Alert Generation

        │

        ▼

     Indexer

        │

        ▼

    Dashboard

        │

        ▼

SOC Analyst
```

---

# Detection Workflow

```
Security Event

        │

        ▼

Sysmon / Windows Event Logs

        │

        ▼

Wazuh Agent

        │

        ▼

Wazuh Manager

        │

        ▼

Custom Detection Rules

        │

        ▼

MITRE ATT&CK Mapping

        │

        ▼

Alert Generation

        │

        ▼

Dashboard Visualization

        │

        ▼

Incident Investigation
```

---

# Network Architecture

| Machine | Role |
|----------|------|
| Ubuntu Server | SIEM Infrastructure |
| Windows Server 2022 | Monitored Endpoint |
| Kali Linux | Attack Simulation |

---

# Security Monitoring Workflow

The monitoring process follows a standard SOC workflow:

1. Generate endpoint activity.
2. Collect telemetry using Sysmon and Windows Event Logs.
3. Forward events through the Wazuh Agent.
4. Analyze events using Wazuh detection rules.
5. Trigger alerts based on predefined conditions.
6. Map detections to the MITRE ATT&CK framework.
7. Visualize events through SOC dashboards.
8. Investigate and respond to incidents.

---

# Detection Engineering

Custom Wazuh rules were developed to detect common attack techniques including:

- Windows Brute Force
- Encoded PowerShell
- New Administrator Accounts
- Port Scanning
- Certutil Execution
- Bitsadmin Execution
- Rundll32 Execution

Each rule is mapped to relevant MITRE ATT&CK techniques.

---

# Dashboards

The project includes multiple dashboards designed for SOC monitoring.

### SOC Overview

- Total Alerts
- Critical Alerts
- High Severity Alerts
- Active Agents
- Alerts Timeline

### Authentication Monitoring

- Successful Logins
- Failed Logins
- Account Lockouts
- RDP Logins
- Login Timeline

### Windows Security Monitoring

- Process Creation
- PowerShell Activity
- Network Connections
- DNS Queries
- Sysmon Events

### Threat Detection & Incident Response

- Custom Rule Hits
- MITRE ATT&CK Coverage
- High Severity Alerts
- Attack Timeline
- Recent Security Incidents

---

# MITRE ATT&CK Integration

The project maps detections to the MITRE ATT&CK framework to improve threat classification and incident investigation.

Examples include:

| Technique ID | Technique |
|--------------|-----------|
| T1110 | Brute Force |
| T1059.001 | PowerShell |
| T1046 | Network Service Discovery |
| T1136 | Create Account |
| T1105 | Ingress Tool Transfer |
| T1197 | Bits Jobs |
| T1218.011 | Rundll32 |

---

# Design Goals

The architecture was designed with the following objectives:

- Centralized log collection
- Enterprise-grade monitoring
- Real-time alert generation
- Detection engineering
- Threat hunting
- Incident investigation
- Dashboard visualization
- Scalability for future integrations

---

# Future Enhancements

Planned improvements include:

- Active Directory integration
- Threat Intelligence (VirusTotal)
- AbuseIPDB enrichment
- Python SOC Automation
- Email notifications
- Slack integration
- Telegram alerts
- Automated Incident Response
- SOAR playbooks

---

# Summary

This architecture demonstrates a practical implementation of an enterprise Security Operations Center using open-source technologies. It provides centralized visibility into endpoint activity, supports custom detection engineering, enables attack simulation, and delivers actionable security insights through professional SOC dashboards.
