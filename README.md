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

<p>
Create an Azure Virtual Machine Windows 10 (22H2)

When Choosing the size, you need at least 2 vCPUs

- Name: osticket-vm

- Username: johndoe

- Password: Password1!
</p>

<p>
<img src="https://i.imgur.com/1gi6Igw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Log into the VM with Remote Desktop using the Public IP address.
<p>
  
<p>
<img src="https://i.imgur.com/LHs8IIY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Within the VM (osticket-vm), go to your browser and search "osticket.com/download". 
</p>

<p>
Make an account and download the zip folder. The folder should be called “osTicket-Installation-Files”.
</p>

<p>
<img src="https://i.imgur.com/R0dvY6K.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Go to World Wide Web Services Application, Click on Development Features, and enable CGI.
</p>

<p>
<img src="https://i.imgur.com/G91CQUW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS.
</p>

<p>
<img src="https://i.imgur.com/6LXKdbq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
From the “osTicket-Installation-Files” folder install the Rewrite Module 
</p>  

<p>
<img src="https://i.imgur.com/jlpphJU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Go to "This PC", then to "Windsows (C:)", and create a new folder naemd "PHP".

From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 into the “C:\PHP” folder.
</p>

<p>
<img src="https://i.imgur.com/n5ubJlL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
From the “osTicket-Installation-Files” folder, install VC Redist.
</p>

<p>
<img src="https://i.imgur.com/Stv2w6n.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 & choose "Typical Setup".
</p>

<p>
<img src="https://i.imgur.com/jSAobnY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Now launch Configuration Wizard (after install) using Standard Configuration.

(Username: johndoe / Password: Password1!)
</p>

<p>
<img src="https://i.imgur.com/F2HSyKP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Open IIS as an Admin.
</p>

<p>
<img src="https://i.imgur.com/1YcoaZ9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
  
Reload IIS (Open IIS, Stop and Start the server).
</p>

<p>
<img src="https://i.imgur.com/fi0Vqcl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Finally, you can install osTicket v1.15.8.
</p>

<p>
<img src="https://i.imgur.com/ybfk2uQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”

Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”.
</p>


<p>
<img src="https://i.imgur.com/Qa5XJni.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Go back to IIS, sites, click default, and then to osTicket.

Double-click PHP Manager & Click “Enable or disable an extension”

  - Enable: php_imap.dll

  - Enable: php_intl.dll

  - Enable: php_opcache.dll

Refresh the osTicket site, and ensure new extensions are enabled.
</p>

<p>
<img src="https://i.imgur.com/yISekEi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Rename: ost-config.php

- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

<p>
<img src="https://i.imgur.com/kV7CAUH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Assign Permissions: ost-config.php

- Disable inheritance -> Remove All

- New Permissions -> Everyone -> All]

<p>
<img src="https://i.imgur.com/nscQjnk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Continue Setting up osTicket in the browser (click Continue)

- Name helpdesk

- Make a fake email (receives email from customers) 
</p>

<p>
<img src="https://i.imgur.com/WEYmqMq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
From the “osTicket-Installation-Files” folder, install HeidiSQL & open the file.
</p>

<p>
<img src="https://i.imgur.com/1ps0dEU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Create a new session (User: root / Password: root) & connect to the session.
</p>

<p>
<img src="https://i.imgur.com/YfcBjWW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Create a database called “osTicket”.
</p>

<p>
<img src="https://i.imgur.com/aFdX7rk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Continue Setting up osTicket in the browser.

- MySQL Database: osTicket

- MySQL Username: johndoe

- MySQL Password: Password1!

Click “Install Now!”
</p>
