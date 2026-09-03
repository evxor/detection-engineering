# Telemetry Inventory

## Current Windows sources

The Windows endpoint is enrolled in the `windows-detection-lab` Fleet policy with the System and Windows integrations.

| Source | Dataset or channel | Detection value |
|---|---|---|
| Sysmon | `windows.sysmon_operational` | Process creation and other enriched host activity |
| PowerShell | Windows PowerShell operational logs | Script and engine activity when enabled by policy |
| Windows Defender | Microsoft Defender operational logs | Antivirus and protection events |
| Windows System/Security | Windows event logs | Authentication and operating-system context |
