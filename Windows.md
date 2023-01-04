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

$> Get-Command -Name A* -CommandType cmdlet

### Get-Service 
cmdlet lets you view your computer's status and list of services. By default, the Get-Service command returns all the (stopped and running) services.

$> Get-Service -Name "Win*"

### Get-ChildItem 
command is a handy cmdlet to look for folders and files and quickly perform content-based searches without using File Explorer.

$> Get-ChildItem -Path "C:\Program Files\Fodler_Name" -Recurse | Select FullName

### Copy-Item 
cmdlet lets you copy-paste files and folders and their contents to a different directory. To copy files and folders, 
type Copy-Item followed by the source -Path, -Destination parameter, 
and destination address. For example, to copy E:\Folder1 and its contents to E:\Folder2, type:

$> Copy-Item "E:\Folder1" -Destination "E:\Folder2" -Recurse

### Move-Item
Similarly, to move an item, you can use the Move-Item cmdlet.

### Remove-Item 
cmdlet lets you delete files

### Get-Content 
cmdlet lets you view the content of an item item without using a text editor.

### Set-ExecutionPolicy 
cmdlets let you change the security levels for script execution.
To know your current execution policy, type:

$> Get-ExecutionPolicy

### Export-CSV
If you want to export and present PowerShell output in a more organized way, you can use the Export-CSV cmdlet. It takes the output file for the specified command and converts it to a CSV file.

$> Get-Process | Export-CSV PSprocess.csv

### ConvertTo-HTML
If you would rather create an HTML report, you can use the ConvertTo-HTML Cmdlet. To create an HTML report for all the running process on your PC, type :

Get-Process | ConvertTo-HTML > PSprocess.html

### Get-History
You can use the Up-Down arrow key to scroll through the recently executed commands in PowerShell. However, to view a list of all the recently executed commands in your current session at once, you can use the Get-History cmdlet.
