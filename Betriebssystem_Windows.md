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

## Most useful comands in comandline

### cipher
Deleting files on a mechanical hard drive doesn't really delete them at all. Instead, it marks the files as no longer accessible and the space they took up as free. The files remain recoverable until the system overwrites them with new data, which can take some time.

The cipher command, however, lets you wipe a directory on an NTFS-formatted volume by writing random data to it. To wipe your C drive, for example, you'd use the cipher /w:d command, which will wipe free space on the drive. The command does not overwrite undeleted data, so you will not wipe out the files you need by running this command.

When you run the cipher command by itself, it returns the encryption state of the current directory and the files it contains. Use cipher /e:<filename> to encrypt a file, cipher /c:<filename> to retrieve information about encrypted files, and cipher /d:<filename> to decrypt the selected file. Most of these commands are redundant with the Windows encryption tool BitLocker.
 
### File Compare
You can use this command to identify differences in text between two files. It's particularly useful for writers and programmers trying to find small changes between two versions of a file. Simply type fc and then the directory path and file name of the two files you want to compare.

You can also extend the command in several ways. Typing /b compares only binary output, /c disregards the case of text in the comparison, and /l only compares ASCII text.

So, for example, you could use the following:

fc /l "C:\Program Files (x86)\example1.doc" "C:\Program Files (x86)\example2.doc"
 
### netstat
 Entering the command netstat -an will provide you with a list of currently open ports and related IP addresses. This command will also tell you what state the port is in; listening, established, or closed.

This is a great command for when you're trying to troubleshoot devices connected to your PC or when you fear a Trojan infected your system and you're trying to locate a malicious connection.
 
 ### Pathping 
 This is a more advanced version of ping that's useful if there are multiple routers between your PC and the device you're testing. Like ping, you use this command by typing pathping followed by the IP address, but unlike ping, pathping also relays some information about the route the test packets take.
 
### System File Checker
 is an automatic scan and repair tool that focuses on Windows system files.

You will need to run the command prompt with administrator privileges and enter the command sfc /scannow. If SFC finds any corrupt or missing files, it will automatically replace them using cached copies kept by Windows for this purpose alone. The command can require a half-hour to run on older notebooks.
 
### Schtasks
 is your command prompt access to the Task Scheduler, one of many underrated Windows administrative tools. While you can use the GUI to manage your scheduled tasks, the command prompt lets you copy&paste complex commands to set up multiple similar tasks without having to click through various options. Ultimately, it's much easier to use, once you've committed key parameters to memory.
 
 ### Format
 
 When you need to format a drive, you can either use the Windows File Explorer GUI or you can turn to the command prompt. You'll need Administrator rights to use this command. Be sure you specify the volume you want to format, followed by the desired parameters.

The command below will quick-format the D drive with the exFAT file system, with an allocation unit size of 2048 bytes, and rename the volume to "label" (without the quotes).

format D: /Q /FS:exFAT /A:2048 /V:label

 ### Systeminfo
 This command will give you a detailed configuration overview of your computer. The list covers your operating system and hardware. For example, you can look up the original Windows installation date, the last boot time, your BIOS version, total and available memory, installed hotfixes, network card configurations, and more.

Use systeminfo /s followed by the hostname of a computer on your local network, to remotely grab the information for that system. This may require additional syntax elements for the domain, user name, and password, like this:
