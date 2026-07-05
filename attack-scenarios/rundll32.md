# Rundll32 Abuse Detection

## Overview

Rundll32 is a legitimate Windows binary frequently abused to execute malicious DLLs.

This scenario validates detection of Rundll32 execution.

---

# MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1218.011 | Rundll32 |

---

# Attack Command

```cmd
rundll32.exe shell32.dll,Control_RunDLL
```

---

# Expected Detection

Rule ID

```
100106
```

Severity

```
Critical
```

---

# Verification

Confirm detection in:

- Threat Detection Dashboard
- Windows Security Dashboard

---


# Remediation

- Validate DLL execution
- Review parent process
- Investigate command-line arguments
- Isolate endpoint if malicious

---

# Outcome

The custom Rundll32 detection rule successfully generated a security alert.
