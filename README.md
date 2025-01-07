<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Creating Users with Powershell  (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Deployment and Configuration Steps</h2>

<h2>Step 1: Enable Remote Desktop Access for Domain Users</h2>

<p>
<img src="https://github.com/user-attachments/assets/30f302a8-289c-4aeb-bdb7-72f813332d3b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log in to Client-1 as mydomain.com\jane_admin.

Right-click the Windows icon in the lower-left corner and select System.

In the System window, click About.

Select Remote Desktop from the options.

Click Select users that can remotely access this PC.

In the new window, click Add.

Enter Domain Users in the field.

Click Check Names to verify the entry.

Click OK, then click OK again to finalize.
</p>
<br />

<h2>Step 2: Run a PowerShell Script to Create Users</h2>

<p>
<img src="https://github.com/user-attachments/assets/0787938f-ea00-47a7-8160-eef862bdb7fc" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log in to DC-1 as mydomain.com\jane_admin.

Use the Search bar at the bottom to search for Windows PowerShell ISE.

Right-click Windows PowerShell ISE and select Run as Administrator.

In PowerShell ISE, click the New File icon (the first page icon in the upper-left corner).

Open the following link in your browser:
GitHub - Generate-Names-Create-Users.ps1

Copy the entire script from the GitHub page.

Return to PowerShell ISE on DC-1 and paste the copied script into the new file.

Save the file by pressing Ctrl + S.

Name the file create-users.ps1, then click Save.

Click the Green Triangle in PowerShell ISE to execute the script.

When prompted, click OK to confirm and run the script.
</p>
<br />


<h2>Step 3: Verify User Creation in Active Directory</h2>

<p>
<img src="https://github.com/user-attachments/assets/ba51d7b6-eedf-4205-8453-d5922540c912" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Active Directory Users and Computers on DC-1.

Expand mydomain.com in the left-hand menu.

Right-click the _EMPLOYEES Organizational Unit.

Click Refresh from the context menu.

Confirm that the newly created users are visible within the _EMPLOYEES Organizational Unit.
</p>
<br />

<h2>Step 4: Test a User Account by Logging into Client-1</h2>

<p>
<img src="https://github.com/user-attachments/assets/e62873b0-32e2-40bb-b14e-1b99384c4ad9" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Active Directory Users and Computers on DC-1, select a random user from the _EMPLOYEES Organizational Unit.

Note the user's credentials:

Username: The username of the selected user.
Password: Password1 (default for all users).
Log in to Client-1 using the selected user's credentials.

Once logged in, click the Search bar in the lower-left corner of the screen.

Type Command Prompt and open it.

Verify that the user shown in the Command Prompt is the account you logged in as.
</p>
<br />
