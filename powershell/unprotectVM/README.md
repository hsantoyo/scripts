# Unprotect a VM using PowerShell

Warning: this code is provided on a best effort basis and is not in any way officially supported or sanctioned by Cohesity. The code is intentionally kept simple to retain value as example code. The code in this repository is provided as-is and the author accepts no liability for damages resulting from its use.

This PowerShell script removes a VM from a protection job.

## Components

* unprotectVM.ps1: the main PowerShell script
* cohesity-api.ps1: the Cohesity REST API helper module

Place all files in a folder together (see download instructions below), and run the script like so:

```powershell
./unprotectVM.ps1 -vip mycluster -username myuser -domain local -vmName myvm
```

```text
Connected!
VM ID is 1757
Removing myvm from Prod VM Backup
```

## Download the script

Run these commands from PowerShell to download the script(s) into your current directory

```powershell
# Download commands
(Invoke-WebRequest -Uri https://raw.githubusercontent.com/bseltz-cohesity/scripts/master/powershell/unprotectVM/unprotectVM.ps1).content | Out-File unprotectVM.ps1; (Get-Content unprotectVM.ps1) | Set-Content unprotectVM.ps1
(Invoke-WebRequest -Uri https://raw.githubusercontent.com/bseltz-cohesity/scripts/master/powershell/unprotectVM/cohesity-api.ps1).content | Out-File cohesity-api.ps1; (Get-Content cohesity-api.ps1) | Set-Content cohesity-api.ps1
# End download commands
```
