
```markdown
# WMI Event Subscription Persistence

## MITRE ATT&CK

T1546.003 — WMI Event Subscription

## Detection

Monitor:

- Sysmon 19 — WmiEventFilter
- Sysmon 20 — WmiEventConsumer
- Sysmon 21 — WmiEventConsumerToFilter
- Sysmon 1 — Process Creation
- WMI-Activity logs

## Investigation

Look for:

- CommandLineEventConsumer
- ActiveScriptEventConsumer
- unusual PowerShell execution
- wmiprvse.exe spawning suspicious processes
- unusual scripts
- encoded commands

## Investigation Chain

```text
WMI Subscription
      ↓
Event Consumer
      ↓
wmiprvse.exe
      ↓
PowerShell / CMD / DLL
      ↓
Network Connection
