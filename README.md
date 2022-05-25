<h1>PowerShell Active Direcrory</h1>

<h2>⭐️THIS SCRIPT IS UNDER CONSTRUCTION AND NOT READY FOR PRODUCION ENVIRONMENTS⭐️</h2>

<h2>Description</h2>
Project consists of PowerShell scripts to create users and groups from PowerShell environment on a Windows Server
<br />


<h2>Utilities Used</h2>

- <b>PowerShell</b> 

<h2>Environments Used </h2>

- <b>Microsoft Azure Portal</b>

<h2>Tasks:</h2>
<b>Task 1:</b>
<br />
Create two local users and a local group
<br />
<br />
<b>Task 2:</b>
<br />
Script a file to create users and add to the correct group
<br />
Verify user accounts are created and added to the correct group
<br />
<br />
<b>Task 3:</b>
<br />
Script file that will export users and group membership
<br />
Exported user details to CSV file
<br />
Exported group membership to a JSON file
<br />
<br />
<b>Task 4:</b>
<br />
Command to input file and pass to script
<br />
Users created from NewUsers.txt 
<br />
Script file or options to disable users
<br />
Command to input RemoveUsers.txt file to pass to script
<br />


<h2>Demonstration:</h2>

<b>Task 1:</b>
<br />
$password = read-host -AsSecureString
<br />
new-localUser -Name "Frankie Friend" -Pasword $password -FullName "FrankieFriend"
<br />
new-lcoalUser -Name "Georgia Green" -Password $password -FullName "GeorgiaGreen"
<br />
new-localGroup -Name Accounting -description Accountants Group
<br />
add-localGroupMember -group Accounting -member "Frankie Friend","Georgia Green"
<br />
get-localUser
<br />
get-localGroup -name Accounting
<br />


<p align="center">
Step 1: <br/>
<img src="Photo" height="80%" width="80%" alt="First photo here"/>
<br />
<br />
 
<b>Task 2:</b>
<br />
param([string]$name
<br />
)
<br />
$splitName = $name.split(' ')
<br />
$username = $splitName[0].substring(0,1) + $splitName[1]
<br />
$password = converTo-secureString "Passw0rd!1234" -AsPlainText -Force
<br />
new-localUser -fullname $username -Name "$name" -password $password
<br />
add-localGroupMember -Group Accounting -Member "$name"
<br />
get-localGroupMember -group Accounting 
<br />

<p align="center">
Step 1: <br/>
<img src="Photo" height="80%" width="80%" alt="First photo here"/>
<br />
<br />
 
<b>Task 3:</b>
<br />
Get-LocalUser |Select-Object -Property Name,Fullname,SID,enabled,lastlogon,passwordlastset 
<br />
|ConvertTo-Csv |out-file "C:\Desktop\UserDetails.csv"Get-LocalGroupMember -Group LegacyAppAccess 
<br />
 |ConvertTo-Json |Out-File "C:\Desktop\LegacyAppAccessMember.JSON"
<br />
.\Desktop\ExportUserData.ps1
 <br />
 
 
<p align="center">
Step 1: <br/>
<img src="Photo" height="80%" width="80%" alt="First photo here"/>
<br />
<br />
 
<b>Task 4:Command to create multiple users via NewUsers.txt </b>
 <br />
 Get-content "E:\challengeday\newUsers.txt" |Foreach {C:\Desktop\newusers.ps1 -Name $_}
 <br />
 #to call above command in PowerShell:
 <br />
 ./Desktop/newUsers.ps1 -name "FirstName LastName"
 
<p align="center">
Step 1: <br/>
<img src="Photo" height="80%" width="80%" alt="First photo here"/>
<br />
<br />
 
<b>Task 4: To create single new user</b>
<br />
 $splitName = $name.split(' ')
<br />
$username = $splitName[0].substring(0,1) + $splitName[1]
<br />
$password = converTo-secureString "Passw0rd!1234" -AsPlainText -Force
<br />
new-localUser -fullname $username -Name "$name" -password $password
<br />
add-localGroupMember -Group Accounting -Member "$name"
<br />
get-localGroupMember -group Accounting 
<br />
 
 
<p align="center">
Step 1: <br/>
<img src="Photo" height="80%" width="80%" alt="First photo here"/>
<br />
<br />
 
<b>Task 4:Command to disable multiple users via DisableUsers.txt </b>
 Get-content "C:\Desktop\DisableUsers.txt" | Foreach {C:\Desktop\DisableUsers.ps1 -Name $_}
 <br />
 #to call above command in PowerShell:
 <br />
 ./Desktop/disableUsers.ps1 -name "FirstName LastName"
 <br />
 
 <b>Task 4: To disable single user</b>
<br />
 $splitName = $name.split(' ')
<br />
$username = $splitName[0].substring(0,1) + $splitName[1]
<br />
disable-LocalUser -Name $username
 <br />
 

<p align="center">
Step 1: <br/>
<img src="Photo" height="80%" width="80%" alt="First photo here"/>
<br />
<br />
 
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
