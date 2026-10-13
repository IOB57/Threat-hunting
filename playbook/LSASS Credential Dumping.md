
```markdown
# Suspicious LSASS Access

## Objective

Detect processes accessing LSASS memory for potential credential theft.

## MITRE ATT&CK

- T1003.001 — LSASS Memory

## Required Telemetry

- Sysmon Event ID 10
- Sysmon Event ID 1
- Security 4688
- EDR ProcessAccess telemetry

## Detection Signals

Investigate:

- unusual process accessing lsass.exe;
- unsigned executable;
- user-writable path;
- unusual administrative tool;
- process launched shortly before LSASS access;
- subsequent network authentication.

## Investigation

```text
Suspicious Process
       |
       v
Access lsass.exe?
       |
      YES
       |
       v
Is process trusted?
    /       \
  YES        NO
   |          |
Check usage   HIGH RISK
   |
   v
Check subsequent authentication
