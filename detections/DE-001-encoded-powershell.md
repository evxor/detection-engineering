# DE-001: PowerShell Encoded Command Execution
## Detection objective

Identify Windows PowerShell launched with the `-EncodedCommand` parameter. Attackers can use encoded commands to obscure command content, but administrators and software may also use this feature legitimately. The rule therefore identifies behavior requiring investigation rather than proving maliciousness.

## Detection logic

```kql
event.code : "1" and
process.name.caseless : "powershell.exe" and
process.args : "-EncodedCommand"
```

## Detection validation

Executed in PowerShell on the controlled Windows lab VM:

```powershell
$TestCommand = 'Write-Output "Elastic detection lab test"'
$EncodedCommand = [Convert]::ToBase64String(
    [Text.Encoding]::Unicode.GetBytes($TestCommand)
)
powershell.exe -NoProfile -EncodedCommand $EncodedCommand
Remove-Variable TestCommand, EncodedCommand
```

Expected console output:

```text
Elastic detection lab test
```
