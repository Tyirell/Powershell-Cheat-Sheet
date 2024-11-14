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
Allows you to start processes on your computer. For example notepad, control panel etc.

### Syntax
`[[-FilePath] <string>`

`[-Credential]`

`[-Verb]`

`[-WindowStyle <ProcessWindowStyle>]`

### Screenshot/Example
In this example I used the Start-Process cmdlet to start the command prompt process. I aslo used the Verb parameter to specifically run this process as an administrator.
![image](https://github.com/user-attachments/assets/d4be9a01-f72d-451f-936c-e4d098d00740)







# Classwork Commands

