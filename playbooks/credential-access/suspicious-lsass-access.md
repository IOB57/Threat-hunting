```markdown
# Suspicious PowerShell Execution

## Objective

Detect and investigate potentially malicious PowerShell execution,
including encoded commands, download activity, obfuscation and
execution from unusual parent processes.

## MITRE ATT&CK

- T1059.001 — PowerShell
- T1027 — Obfuscated Files or Information
- T1105 — Ingress Tool Transfer

## Detection Signals

High-risk signals:

- powershell.exe from Office applications
- encoded command
- DownloadString
- Invoke-WebRequest
- WebClient
- hidden window
- bypass execution policy
- suspicious parent process
- PowerShell spawned by WMI
- PowerShell spawned by scheduled task

## Required Telemetry

- Sysmon Event ID 1
- Security Event ID 4688
- PowerShell 4103
- PowerShell 4104
- EDR process telemetry
- DNS telemetry
- Network connections

## Investigation

### 1. Process tree

Example:

```text
WINWORD.EXE
    └── powershell.exe
          └── rundll32.exe
