# Brute Force Attack Simulation

## Overview

This scenario demonstrates a Windows brute-force attack by generating multiple failed authentication attempts against a Windows Server 2022 system.

The objective is to validate custom Wazuh detection rules and monitor authentication events through the SOC dashboards.

---

# Objective

Detect repeated failed login attempts that may indicate a password guessing or brute-force attack.

---

# Lab Environment

| Component | Value |
|----------|-------|
| Attacker | Kali Linux |
| Target | Windows Server 2022 |
| SIEM | Wazuh |
| Monitoring | Sysmon + Windows Event Logs |

---

# Attack Technique

| MITRE ATT&CK | Description |
|--------------|-------------|
| T1110 | Brute Force |

---

# Attack Steps

Attempt multiple incorrect logins on Windows Server.

Generate at least six failed authentication attempts within one minute.

---

# Expected Detection

Custom Rule

```
100100
```

Windows Event ID

```
4625
```

Alert Severity

```
High
```

---

# Dashboard Verification

Verify the alert appears in:

- Authentication Dashboard
- Threat Detection Dashboard
- SOC Overview

---

# Remediation

- Lock affected account
- Investigate source IP
- Reset compromised credentials
- Enable MFA
- Review authentication logs

---

# Outcome

The attack successfully triggered the custom brute-force detection rule and generated a high-severity security alert.
