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

<p>
<img src="https://i.imgur.com/aRW1okf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI
  
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS

From the “osTicket-Installation-Files” folder install the Rewrite Module 
<br />

<p>
<img src="https://i.imgur.com/HM1XDYy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Create the directory C:\PHP

From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 into the “C:\PHP” folder

From the “osTicket-Installation-Files” folder, install VC Redist

From the “osTicket-Installation-Files” folder, install MySQL 5.5.62
</p>
<p>
Typical Setup ->
</p>
<br />

<p>
<img src="https://i.imgur.com/jpyS5tH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

<p>
<img src="https://i.imgur.com/uaKykUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Open IIS as an Admin

Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

Reload IIS (Open IIS, Stop and Start the server)

Finally, you can install osTicket v1.15.8

From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”

Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
</p>
<br />

<p>
<img src="https://i.imgur.com/9hFM7in.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Note that some extensions are not enabled

- Go back to IIS, sites -> Default -> osTicket

- Double-click PHP Manager

- Click “Enable or disable an extension”

  - Enable: php_imap.dll

  - Enable: php_intl.dll

  - Enable: php_opcache.dll

- Refresh the osTicket site in your browser, observe the changes  
</p>

<p>
<img src="https://i.imgur.com/0dAk01s.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Rename: ost-config.php

- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php

- Disable inheritance -> Remove All

- New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)

- Name Helpdesk

- Default email (receives email from customers)
</p>

<p>
<img src="https://i.imgur.com/VmxgCsj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

From the “osTicket-Installation-Files” folder, install HeidiSQL.

- Open Heidi SQL

- Create a new session, root/root

- Connect to the session

- Create a database called “osTicket”

Continue Setting up osTicket in the browser

- MySQL Database: osTicket

- MySQL Username: johndoe

- MySQL Password: Password1!

Click “Install Now!”
</p>

