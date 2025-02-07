<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop Connection
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Prerequisites</h2>

- An Active Azure subscription.
- Azure Virtual Machine running **Windows 10 (22H2)**.
- Administrator access to the Windows VM.
<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DGbE8ZL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Create an Azure Virtual Machine Windows 10 (22H2), 2 vCPUs
</p>
<p>  
- Name: osticket-vm
</p>
<p>  
- Username: johndoe
</p>
<p>   
- Password: Password1!
</p>
<br />

<p>
<img src="https://i.imgur.com/1gi6Igw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Log into the VM with Remote Desktop using the Public IP address.
<p>
<br />
  
<p>
<img src="https://i.imgur.com/jSoUq5j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within the VM (osticket-vm), got to your browser and search "osticket.com/download". 
</p>
<p>
Make an account and download the zip folder. The folder should be called “osTicket-Installation-Files”.
</p>
<br />

<img src="https://i.imgur.com/aRW1okf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI

From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

Create the directory C:\PHP

From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
</p>
<p>
Typical Setup ->
</p>
<p>
Launch Configuration Wizard (after install) ->
</p>
<p>
Standard Configuration ->
</p>
<p>
Username: johndoe
</p>
<p>
Password: Password1!
</p>
<br />
