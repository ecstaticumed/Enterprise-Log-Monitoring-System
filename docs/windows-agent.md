# Windows Agent Configuration

## Overview

Windows Server 2022 acts as the monitored endpoint within the SOC environment.

The Wazuh Agent collects security events and forwards them to the Wazuh Manager.

---

# Responsibilities

- Collect Windows Event Logs
- Forward Sysmon Events
- Monitor Authentication
- Monitor Processes
- Monitor PowerShell
- Monitor Registry Activity

---

# Monitored Event Categories

- Authentication
- Process Creation
- Network Connections
- DNS Queries
- File Creation
- User Management
- Privilege Escalation

---

# Verification

Confirm the agent is:

- Connected
- Active
- Sending events
- Visible in the Wazuh Dashboard
