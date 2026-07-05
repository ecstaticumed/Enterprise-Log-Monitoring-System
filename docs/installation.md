# Installation Guide

## Overview

This document describes the deployment process for the Enterprise Log Monitoring System.

The project was built using Wazuh on Ubuntu Server, Windows Server 2022, Sysmon, and Kali Linux.

---

# Prerequisites

- Ubuntu Server 22.04 LTS
- Windows Server 2022
- Kali Linux
- VirtualBox or VMware
- Internet Connection

---

# Components

| Component | Purpose |
|----------|----------|
| Wazuh Manager | Log Collection |
| Wazuh Indexer | Event Storage |
| Wazuh Dashboard | Visualization |
| Wazuh Agent | Endpoint Monitoring |
| Sysmon | Windows Telemetry |

---

# Installation Steps

## 1. Install Ubuntu Server

Deploy Ubuntu Server and update packages.

```bash
sudo apt update && sudo apt upgrade -y
```

---

## 2. Install Wazuh

Install:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

Verify services:

```bash
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-dashboard
```

---

## 3. Install Windows Agent

Install the Wazuh Agent on Windows Server 2022 and register it with the manager.

---

## 4. Install Sysmon

Deploy Sysmon using a recommended enterprise configuration.

---

## 5. Configure Audit Policies

Enable:

- Logon Events
- Process Creation
- Account Management
- Object Access
- PowerShell Logging

---

## 6. Verify Data Collection

Confirm events appear in the Wazuh Dashboard.

---

# Result

The Enterprise Log Monitoring System is now operational and ready for dashboard creation and detection engineering.
