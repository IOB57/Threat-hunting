```markdown
# Suspicious Scheduled Task

## MITRE ATT&CK

T1053.005 — Scheduled Task/Job: Scheduled Task

## Detection Signals

- new scheduled task;
- task created by unusual user;
- task executes from Temp/AppData;
- PowerShell/CMD execution;
- task running with SYSTEM;
- task created remotely.

## Telemetry

- Security 4698
- Sysmon 1
- Windows Task Scheduler logs
- EDR

## Investigation

Check:

- task name;
- author;
- command;
- executable path;
- execution account;
- creation time;
- trigger;
- parent process.

Suspicious example:

```text
Task: WindowsUpdateCheck

Action:
C:\Users\Public\update.exe

RunAs:
SYSTEM
