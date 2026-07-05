# Encoded PowerShell Detection

## Overview

Attackers frequently use PowerShell with encoded commands to evade detection.

This scenario validates detection of suspicious PowerShell execution.

---

# MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1059.001 | PowerShell |

---

# Attack Command

```powershell
powershell.exe -EncodedCommand SQBlAGMAbwAgAHQAZQBzAHQA
```

---

# Expected Detection

Rule ID

```
100101
```

Severity

```
Critical
```

---

# Verification

Confirm alerts appear in:

- Windows Security Dashboard
- Threat Detection Dashboard

---


# Remediation

- Investigate command execution
- Decode Base64 payload
- Verify parent process
- Isolate endpoint if malicious

---

# Outcome

Encoded PowerShell execution successfully triggered the custom detection rule.
