# Suspicious Remote Service Execution

## MITRE ATT&CK

- T1021.002 — SMB/Windows Admin Shares
- T1569.002 — Service Execution

## Detection

Look for:

- remote service creation;
- ADMIN$ access;
- service executable from unusual path;
- PsExec-like behavior;
- remote execution from workstation.

## Investigation

```text
Source Host
    ↓
ADMIN$
    ↓
Service Creation
    ↓
Remote Process
    ↓
Credential / Discovery / Execution
