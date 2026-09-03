# Windows Telemetry

## Sysmon

### Event ID 1 — Process Creation

Purpose:
Records creation of a new process.

Useful fields:
- Image
- CommandLine
- ParentImage
- ParentCommandLine
- User
- ProcessGuid
- ProcessId
- Hashes

Elastic ECS mappings observed:
- Image → process.executable
- CommandLine → process.command_line
- ParentImage → process.parent.executable
- ProcessId → process.pid

Detection uses:
- Suspicious PowerShell
- LOLBins
- Office spawning script interpreters
- Unexpected process ancestry
- Encoded command execution
