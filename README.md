## Script that will only run if called directly from interactive command processor session

Script will detect if it's run from non-interactive session (`cmd.exe /c detect-batch-subshell.cmd`) and show approriate error message.

Non-interactive shell includes PowerShell/PowerShell ISE, Explorer, etc... Basically anything that will try to execute script by running it in the separate `cmd.exe` instance.

Hovewer, dropping into the `cmd.exe` session from PowerShell/PowerShell ISE and executing script there will work.

## Dependencies

* [wmic.exe](https://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/wmic.mspx) - comes with Windows XP Professional and up.

### Example:

1. Open `cmd.exe`
2. Type `detect-batch-subshell.cmd`

### Output:

```none
> detect-batch-subshell.cmd

Running interactively in cmd.exe session.
```

### Example:

1. Open `powershell.exe`
2. Type `detect-batch-subshell.cmd`

### Output:

```none
PS > detect-batch-subshell.cmd

detect-batch-subshell.cmd only works if run directly from cmd.exe!
```
