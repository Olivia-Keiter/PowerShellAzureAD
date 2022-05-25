<h1>PowerShell Active Direcroty</h1>

<h2>Description</h2>
Project consists of PowerShell scripts to create users and groups from PowerShell environment on a Windows Server
<br />


<h2>Utilities Used</h2>

- <b>PowerShell</b> 

<h2>Environments Used </h2>

- <b>Microsoft Azure Portal</b>

<h2>Tasks:</h2>
Task 1: 
<br />
Create two local users and a local group
<br />

Task 2: 
<br />
Script a file to create users and add to the correct group.
<br />
Transcript files recording creation of the user.
<br />
Verify user accounts are created and added to the correct group.
<br />


<h2>Code:</h2>

Task 1:
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
 
 

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
