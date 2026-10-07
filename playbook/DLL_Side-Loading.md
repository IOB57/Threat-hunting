```markdown
# Suspicious DLL Side-Loading

## MITRE ATT&CK

T1574.002 — DLL Side-Loading

## Detection

Look for:

- trusted executable;
- DLL loaded from unusual directory;
- unsigned DLL;
- user-writable directory;
- unusual parent/child relationship.

## Telemetry

- Sysmon 1
- Sysmon 7
- EDR ImageLoad
- File creation telemetry

## Investigation

```text
Trusted EXE
     |
     +---- loads DLL
              |
              v
        Unusual Path
              |
              v
          Unsigned DLL
