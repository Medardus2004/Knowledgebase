# Windows 

## Most Useful Powershell comands

### Get-Help
as the name suggests, is part of PowerShell's integrated help system. 
It helps you find necessary information for the command, concepts, and functions, identify alias, scripts, and more.

### Get-Process
helps you retrieve and show a list of all the active system processes with their identifiers (IDs). 
You can use it as an efficient alternative to Windows Task Manager to view, stop and restart system processes.

$> Get-Process -ID 20496 | Stop-Process

### Start-Process 
 cmdlet in PowerShell used to start one or more processes on a local computer. To use the cmdlet, type Start-Process followed by the process name. 

### Get-Command 
 lets you view all the PowerShell commands installed on your computer. 
 Similar to Get-Help, you can use the Get-Command followed by a search query to find commands for a specific feature




