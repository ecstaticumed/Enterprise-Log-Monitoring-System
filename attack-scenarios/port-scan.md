# Network Port Scan Detection

## Overview

This scenario simulates reconnaissance activity using Nmap against the monitored Windows Server.

---

# MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1046 | Network Service Discovery |

---

# Tool

Nmap

---

# Attack Command

```bash
nmap -A <Windows-IP>
```

---

# Expected Detection

Rule ID

```
100103
```

Severity

```
High
```

---

# Verification

Confirm detection in:

- Threat Detection Dashboard
- SOC Overview

---


# Remediation

- Identify attacker IP
- Review firewall logs
- Block malicious host
- Investigate reconnaissance activity

---

# Outcome

Port scanning activity generated the expected detection alert.
