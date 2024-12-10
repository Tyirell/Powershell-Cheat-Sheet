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

# Classwork Commands

