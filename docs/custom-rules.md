# Custom Detection Rules

## Overview

The Enterprise Log Monitoring System extends Wazuh using custom detection rules to identify common attack techniques.

---

# Implemented Rules

| Rule ID | Detection |
|----------|-----------|
| 100100 | Windows Brute Force |
| 100101 | Encoded PowerShell |
| 100102 | Administrator Account Creation |
| 100103 | Port Scan |
| 100104 | Certutil Execution |
| 100105 | Bitsadmin Execution |
| 100106 | Rundll32 Execution |

---

# Detection Goals

- Improve visibility
- Detect attacker behavior
- Reduce response time
- Support incident investigation

---

# MITRE ATT&CK

All rules are mapped to the MITRE ATT&CK framework to improve threat classification.
