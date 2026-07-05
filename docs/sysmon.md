# Sysmon Configuration

## Overview

Sysmon extends Windows logging by providing detailed endpoint telemetry for security monitoring.

This project uses Sysmon to improve visibility into process execution, network activity, registry modifications, and file creation.

---

# Monitored Events

- Process Creation
- Network Connections
- DNS Queries
- File Creation
- Registry Changes
- Driver Loading

---

# Common Event IDs

| Event ID | Description |
|----------|-------------|
| 1 | Process Creation |
| 3 | Network Connection |
| 11 | File Created |
| 13 | Registry Value Set |
| 22 | DNS Query |

---

# Benefits

- Improved endpoint visibility
- Better threat hunting
- Detection engineering
- Incident investigation
