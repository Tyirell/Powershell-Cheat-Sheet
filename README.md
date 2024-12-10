# Powershell-Cheat-Sheet
Powershell journal that includes the commands learned, descriptions, and use cases

# Cmdlets

## Write-Host
Displays output to the Host. Commonly used when trying to create a fancy colored output to the host. Not used for providing output to the user for coding.

### Syntax
`[-Object] <Object>]`  

`[-NoNewline]`  

`[-ForegroundColor <ConsoleColor>]`  

`[-BackgroundColor <ConsoleColor>]`

### Screenshot/Example

In this example we make use of the background and foreground parameter to allow the textoutput to be red and the background to be green.

![image](https://github.com/user-attachments/assets/7ac904ce-3d34-486c-8125-554a0cf6abd6)

## Get-Service
Gets all the services on the computer. Can be used to get services on remote computers as well.

### Syntax
`[[-Name] <String[]>]`  

`[-DependentServices]`  

`[-RequiredServices]`

`[-Include <String[]>]`

`[-Exclude <String[]>]`

### Screenshot/Example
In this example I used the Get-Service cmdlet pipelined to the Where-Object cmdlet and specifed only running services to be apart of the output.
![image](https://github.com/user-attachments/assets/80bc530b-7dad-4039-8bcf-b8c1481e4a7c)

## Get-Process
Gets all the processes that are running on the computer

### Syntax
`[[-Name] <String[]>]` or `[-Id <Int32[]>]`

`[-Module]`

`[-FileVersionInfo]`

### Screenshot/Example
In this example I used the Get-Process cmdlet pipelined to the Select-Object cmdlet and specifed only the Process object to be displayed. By default the Objects shown is Handles, PM, WS, CPU, Id, SI, ProcessName.
![image](https://github.com/user-attachments/assets/3a417436-a368-4e32-a91e-a1b2a69a28d1)

## Start-Process
Allows you to start processes on your computer. For example notepad, command prompt etc.

### Syntax
`[[-FilePath] <string>`

`[-Credential]`

`[-Verb]`

`[-WindowStyle <ProcessWindowStyle>]`

### Screenshot/Example
In this example I used the Start-Process cmdlet to start the command prompt process. I also used the Verb parameter to specifically run this process as an administrator.
![image](https://github.com/user-attachments/assets/d4be9a01-f72d-451f-936c-e4d098d00740)

## Stop-Process
Allows you to stop processes on your computer. For example notepad, control prompt etc.

### Syntax
`-Name <String[]>` or `[-Id <Int32[]>]`

`[-PassThru]`

`[-Force]`

### Screenshot/Example
In this example I used the Stop-Process cmdlet to stop the notepad process I had running on my computer.
![image](https://github.com/user-attachments/assets/167be4ef-f304-43a5-8016-8c1187001d82)

## ForEachObject
Performs an action or operation on each item in a group of input objects.

### Syntax
`[-InputObject <PSObject>]`

`[-Begin <ScriptBlock>]`

`[-Process <ScriptBlock[]>]`

`[-End <ScriptBlock>]`

### Screenshot/Example
In this example I used 4 numbers to represent objects and pipelined it to the ForEachObject cmdlet. I then specified the word that I wanted to output for each object that was listed. In this case I specified 4 objects so the word hello displayed 4 times.
![image](https://github.com/user-attachments/assets/0b8316f7-913a-48d3-9136-e9dccd460fd8)

## Format-Wide
Allows you to format objects as a wider table. This can be used when trying to read output in a neater way.

### Syntax
`[[-Property] <Object>]`

`[-Autosize]`

`[-Column <int>]`

`[-GroupBy <Object>]`

### Screenshot/Example
In this example I use the Get-Service output and pipline it to the Format Wide cmdlet to allow the outputting to be changed to a wide table.
![image](https://github.com/user-attachments/assets/b3ce40ae-b36e-408e-89b9-3ebe283a0946)

## Format-List
Allows you to format objects as a list. The value is seperated by a colon. In the example it goes object then the value.

### Syntax
`[[-Property <Object[]>]`

`[-GroupBy <Object>]`

`[-View <string>]`

### Screenshot/Example
In this example I use the Get-Service cmdlet and pipeline it to the Format-List cmdlet to chnage the format to a list output.
![image](https://github.com/user-attachments/assets/538bc90e-41cc-4944-8a4d-c85b5752178c)

## Get-Help
Gives you information about a powershell command.

### Syntax
`[[-Name] <String>]`

`[-Path <String>]`

`[-Category <String[]>]`

 `[-Full]`

### Screenshot/Example
In this example I use the Get-Help command and specify the Get-Process command to figure out more about the command and what it's used for. I also use the full parameter to determine which parameters are required.
![image](https://github.com/user-attachments/assets/127f8310-38ff-46c9-8942-ab3ec8777450)

## Get-NetAdapter
Gets network adapter information.

### Syntax
`[[-Name] <String[]>]`

`[-IncludeHidden]`

`[-Physical]`

### Screenshot/Example
In this example I use the Get-NetAdapter command and again pipe it to the Where-Object cmdlet to get only net adapter information on the ones that status is up.
![image](https://github.com/user-attachments/assets/8d11a718-f671-41cb-b237-4858cdb5e623)

## Export-CSV
Allows you to convert objects into a comma seperated value format and save this to a file.

### Syntax
`-InputObject <PSObject>`

`[[-Path] <String>]`

`[-LiteralPath <String>]`

`[[-Delimiter] <Char>]`

### Screenshot/Example
In this example I use the get-service command and pipeline it to the Export-CSV cmdlet. I specified the Delimeter "/" so now between every object there will be that symbol.
![image](https://github.com/user-attachments/assets/c6ed7d6a-7aa2-4bbe-90e7-89fde40a3472)

## Get-Content
Gets the contents of an item specified by location

### Syntax
`[-ReadCount <Int64>]`

`[-TotalCount <Int64>]`

`[-Tail <Int32>]`

`[-Path] <String[]>`

### Screenshot/Example
In this example I view the contents of the Test.CSV file by using the Get-Content cmdlet.
![image](https://github.com/user-attachments/assets/d4aad676-677f-49bd-a26a-c384b9b6c950)

## Get-WMIObject
Used to get information on windows management instrumentation objects(WMI)

### Syntax
`[-Class] <String>`

`[[-Property] <String[]>]`

`[-Filter <String>]`

`[-Amended]`

### Screenshot/Example
In this example I use the Get-WMIObject cmdlet and specify the Class parameter to get information about my current operating system.
![image](https://github.com/user-attachments/assets/552bebeb-6837-4d8e-b9c0-436062e03bcf)

## Get-EventLog
Gets a list of event logs on your local or remote computers

### Syntax
`[-LogName] <String>`

`[-ComputerName <String[]>]`

`[-Newest <Int32>]`

### Screenshot/Example
In this example I use the Get-EventLog cmdlet and specify the System logs. I also use the newest parameter to only get the newest 10 events logged.
![image](https://github.com/user-attachments/assets/b86db722-78e4-4171-8a61-936ef5904b6c)

## Get-Member
Used to display the properties and methods of an objects.

### Syntax
`[-InputObject <PSObject>]`

`[[-Name] <String[]>]`

`[-MemberType <PSMemberTypes>]`

### Screenshot/Example
In this example I use the Get-Process cmdlet and pipeline it to the get-member cmdlet to get information about the properties and methods available with Get-Process.
![image](https://github.com/user-attachments/assets/6e95011f-ea9f-4137-9b8b-e67d55ec3e90)

## Enable PS-Remoting
Used to enable remoting on your remote device. In most cases you must run this command with administrator privileges.

### Syntax
`[-Force]`

`[-SkipNetworkProfileCheck]`

`[-WhatIf]`

`[-Confirm]`

### Screenshot/Example
In this example I use the Enable-PSRemoting cmdlet to allow others to remote into my computer. 
![image](https://github.com/user-attachments/assets/b8a8f262-d0c9-4bdb-983e-98c3a5607fa0)

## Enter-PSSession
Used to start a session with a remote computer.

### Syntax
`[-ComputerName] <String>`

`[-EnableNetworkAccess]`

`[[-Credential] <PSCredential>]`

### Screenshot/Example
In this example I use the Server1 VM I created that is a domain controller and remote into Server2 using the Enter-PSSession Cmdlet.
![image](https://github.com/user-attachments/assets/c990eaeb-34fb-4984-bf06-6017650f5a00)

## Invoke-Command
Used to run commands on both local and remote computers

### Syntax
`[-ScriptBlock] <ScriptBlock>`

`[[-Session] <PSSession[]>]`

`[-ThrottleLimit <Int32>]`

### Screenshot/Example
In this example I use the Invoke-Command Cmdlet to run the Get-Service command on my Server2 VM.
![image](https://github.com/user-attachments/assets/5ee7c0ed-7c14-4ef4-abac-99714f35455a)

## Import-Module
Imports module into your current session

### Syntax
`[-Global]`

`[-Prefix <String>]`

`[-Name] <String[]>`

`[-Function <String[]>]`

### Screenshot/Example
In this example I use the Import-Module cmdle to import the Net-Adapter module into my current Server1 VM session.
![image](https://github.com/user-attachments/assets/5c641540-d189-4db8-8a24-056c67b85f25)

## Get-Location
Gives you information of your current location your currently in (directory).

### Syntax
`[-PSProvider <String[]>]`

`[-PSDrive <String[]>]`

`[-Stack]`

### Screenshot/Example
In this example I use the Get-Location cmdlet to determine my current directory I'm in.
![image](https://github.com/user-attachments/assets/0a1c95cd-6918-4694-bce7-d5903817526c)

## New-Item
Allows you to create new items such as directories and files.

### Syntax
`[-Path] <String[]>`

`[-ItemType <String>]`

`[-Value <Object>]`

`[-Force]`

### Screenshot/Example
In this example I create a new file called Hi.txt. I use the itemtype parameter and specify that its a file and set the path to downloads using the New-Item cmdlet.
![image](https://github.com/user-attachments/assets/26fd5f71-83b4-4584-bdd5-4fcb43112762)

## New-SMBShare
Creates an SMBShare and allows you to specify access to it. In order to create a share you must already have a folder created.

### Syntax
`[-Path] <String>`

`[-Name] <String>`

`[-FullAccess <String[]>]`

`[-ChangeAccess <String[]>]`

### Screenshot/Example
In this example I use the New-SMBShare cmdlet and create three seperate shares for my respective groups HR, IT and Admin I created. I make sure to only allow users who are in the desginated groups access to the shares using the full access parameter. IN this I made sure to create directories ahead of time to make this work.
![image](https://github.com/user-attachments/assets/0753a4f2-1f0c-4dbb-8967-9dd0796fe0##1b)

## Get-ADComputer
Allows you to see your current computers joined to your domain.

### Syntax
`[-AuthType <ADAuthType>]`

`[-Credential <PSCredential>]`

`-Filter  <String>`

`[-Properties <String[]>]`

### Screenshot/Example
In this example I use the Get-ADComputer command to see all of the computers/servers that are currently joined to my domain.
![image](https://github.com/user-attachments/assets/f26643aa-feaf-4a8c-9c1e-22f5a35db39d)

## Install-WindowsFeature
Installs roles of features on your local or remote computer/server.

### Syntax
`[-Name] <Feature[]>`

`[-Restart]`

`[-IncludeAllSubFeature]`

`[-IncludeManagementTools]`

### Screenshot/Example
In this example I use the Install-WindowsFeature cmdlet to install the DHCP feature and I specify the include management tools parameter.
![image](https://github.com/user-attachments/assets/05c2b2eb-fac2-4601-a660-f7a6ec09c4e0)

## Get-NetIPAddress
Gets your current IP address configurations.

### Syntax
`[[-IPAddress] <String[]>]`

`[-InterfaceIndex <UInt32[]>]`

`[-InterfaceAlias <String[]>]`

### Screenshot/Example
In this example I check exactly what my IP address configuration is using the Get-NetIPAddress cmdlet.
![image](https://github.com/user-attachments/assets/bb5bd55d-694b-4112-aacd-0e33b3f1cc74)

## Set-DNSClientServerAddress
Allows you to set up an IP that points to your designated DNS server.

### Syntax
`[-InterfaceAlias] <String[]>`

`[-ServerAddresses <String[]>]`

`[-Validate]`

`[-ResetServerAddresses]`

### Screenshot/Example
In this example I use the Set-DNSClientServerAddress command to point to an IP address of 192.168.0.50. I also specify a interface index in this command which is needed for this command to work. 
![image](https://github.com/user-attachments/assets/49c73319-0c08-4fea-aa56-120d5056c5a9)

## Set-ExecutionPolicy 
Controls the execution policy on your machine. This determines if you can run scripts, load configuration files, or if scripts have to be digitally signed before they can run.

### Syntax
`[-ExecutionPolicy] <ExecutionPolicy>`

`[[-Scope] <ExecutionPolicyScope>]`

`[-Force]`

### Screenshot/Example
In this example I use the Set-ExecutionPolicy cmdlet and specify the exection policy to remote signed.
![image](https://github.com/user-attachments/assets/0975aff6-7707-4606-b176-2cbd8e7d45c2)

## New-ADOrganizationalUnit
Allows you to create an OU. You must have active directory installed for this command to work.

### Syntax
`[-Instance <ADOrganizationalUnit>]`

`[-ManagedBy <ADPrincipal>]`

`[-Name] <String>`

`[-OtherAttributes <Hashtable>]`

### Screenshot/Example
In this example I use the New-ADOrganizationalUnit command to create a new OU called Employee's and specify the -Path where this OU will be stored.
![image](https://github.com/user-attachments/assets/9aaff083-f11a-4978-8cfa-427ead775b12)

## Initializing Arrays
A data structure that stores a collection of multiple items

### Syntax for creating Arrays
`$test = @()`

`$test = @('Zero','One','Two','Three')`

`$test = @(
    'Zero'
    'One'
    'Two'
    'Three'
)`

`$data = 'Zero','One','Two','Three'`

### Screenshot/Example
In this example I create an array called TG and assign it values 4,5,6,7. I use the indexing feature to get the 2nd indexed item in the array(6).
![image](https://github.com/user-attachments/assets/a3637c09-a3bc-439f-9400-735676b92a25)

## Variables
Allows you to store a value and use it for later.

### Syntax for creating a variable

` Specify by data type [int]$i = 10`

` Just intialize a standard variable $i = "Hello"`

### Screenshot/Example
In this example I create a variable and store the Get-Service cmdlet in it. After I call this variable. Remember when you intialize a cmdlet like Get-Service only the current state of the command is saved under the variable. ![image](https://github.com/user-attachments/assets/6d1a1ec0-d6bd-4863-9f0f-d2d0d738cf9a)

## Get-Childitem
Gets the files and directories under a specified location.

### Syntax
`[[-Path] <string[]>]`

`[[-Filter] <string>]`

`[-Include <string[]>]`

`[-Exclude <string[]>]`

### Screenshot/Example
In this example I use the Get-Childitem command under my tyire directory to see all files and folders listed there.
![image](https://github.com/user-attachments/assets/8e504070-68d9-41c8-b380-909b1d3bd3a6)

## Move-Item
Allows you to move an item from one location to another.

### Syntax
`[-Path] <String[]>`

`[[-Destination] <String>]`

`[-Force]`

`[-Filter <String>]`

### Screenshot/Example
In this example I move my Test.csv file from my downloads to my Documents folder using the Move-Item cmdlet.















# Classwork Commands

