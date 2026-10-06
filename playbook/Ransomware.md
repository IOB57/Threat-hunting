# Ransomware Activity

## Objective

Detect early ransomware behavior and identify affected hosts.

## MITRE ATT&CK

- T1486 — Data Encrypted for Impact
- T1490 — Inhibit System Recovery
- T1562.001 — Impair Defenses
- T1059 — Command and Scripting Interpreter

## High-Risk Signals

- mass file modification;
- unusual file extensions;
- shadow copy deletion;
- backup deletion;
- security service stopping;
- suspicious administrative activity;
- rapid SMB activity.

## Attack Chain

```text
Initial Access
      ↓
Execution
      ↓
Credential Access
      ↓
Lateral Movement
      ↓
Security Tool Disable
      ↓
Backup Destruction
      ↓
Mass File Encryption
