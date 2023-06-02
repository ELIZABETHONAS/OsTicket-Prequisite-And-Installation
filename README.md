# osTicket-Prequisite-and-installation
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This project outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Microsoft Remote Desktop
- Internet Information Services (IIS)
- PHP Manager
- OsTicket
- MySQL
- HeidiSQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Resource Group
- Azure Virtual Machine
- Virtual Network

<h2>Installation Steps</h2>

<p>

![thisismyimage](https://github.com/ELIZABETHONAS/OsTicket-Prequisite-And-Installation/blob/main/1.png)
</p>
<p>

- (Create Virtual Machine in Azure)
   -  Create a Resource Group
   -  Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs
   -  When creating the VM, allow it to create a new Virtual Network (Vnet)  
</p>
<br />

<p>
   
![thisismyimage](https://github.com/ELIZABETHONAS/OsTicket-Prequisite-And-Installation/blob/main/2.png?raw=true)
</p>
<p>

-  Create an Azure Virtual Machine Windows 10, 4 vCPUs
   -  Name: VMOSTICKET
   -  Username: labuser09 (for example/whatever you chose)
   -  Password: osTicketPassword1! (for example/whatever you chose)
<p>
   
![thisismyimage](https://github.com/ELIZABETHONAS/OsTicket-Prequisite-And-Installation/blob/main/3.png?raw=true)
</p>
<p>

-  Install and download the following files as a prequisite for this project: 
   -  IIS in Windows WITH CGI
   -  World Wide Web Services -> Application Development Features -> [X] CGI
   -  PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
   -  Rewrite Module (rewrite_amd64_en-US.msi)
   -  Create the directory C:\PHP
   -  VC_redist.x86.exe.
</p>
<br />


<p>
   
![thisismyimage](https://github.com/ELIZABETHONAS/OsTicket-Prequisite-And-Installation/blob/main/4.png?raw=true)
</p>
<p>

-  MySQL 5.5.62 (mysql-5.5.62-win32.msi)
     - Typical Setup ->
     - Launch Configuration Wizard (after install) ->
     - Standard Configuration ->
     - Password1
     - download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
</p>
<br />

<p>
   
![thisismyimage](https://github.com/ELIZABETHONAS/OsTicket-Prequisite-And-Installation/blob/main/5.png?raw=true)
![thisismyimage](https://github.com/ELIZABETHONAS/OsTicket-Prequisite-And-Installation/blob/main/6.png?raw=true)   
</p>
<p>

-  Open IIS as an Admin
-  Register PHP from within IIS
-  Reload IIS (Open IIS, Stop and Start the server) 
</p>
<br />

<p>
   
![thisismyimage](https://github.com/ELIZABETHONAS/OsTicket-Prequisite-And-Installation/blob/main/7.png?raw=true)
</p>
<p>

-  Install osTicket v1.15.8
   -  Download osTicket from the Installation Files Folder
   -  Extract and copy “upload” folder to c:\inetpub\wwwroot
   -  Within c:\inetpub\wwwroot, Rename “upload” to “osTicket"
</p>
<br />

<p>
   
![thisismyimage](https://github.com/ELIZABETHONAS/OsTicket-Prequisite-And-Installation/blob/main/IMG_0033.png)
</p>
<p>

-  Reload IIS (Open IIS, Stop and Start the server)
   -  Go to sites -> Default -> osTicket
   -  On the right, click “Browse *:80”  
</p>
<br />

<p>
   
![thisismyimage]()
</p>
<p>

-  Observe some of the extensions are not enabled
   -  Go back to IIS, sites -> Default -> osTicket
   -  Double-click PHP Manager
   -  Click “Enable or disable an extension”
   -  Enable: php_imap.dll
   -  Enable: php_intl.dll
   -  Enable: php_opcache.dll
   -  Refresh the osTicket site in your browse, observe the changes

</p>
<br />

<p>
   
![thisismyimage]()
</p>
<p>
   
-  Rename: ost-config.php
   -  From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
   -  To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

-  Assign Permissions: ost-config.php
   -  Disable inheritance -> Remove All
   -  New Permissions -> Everyone -> All

</p>
<br />

<p>
   
![thisismyimage]()
</p>
<p>

-  Continue Setting up osTicket in the browser (click Continue)
   Name Helpdesk
   -  Default email (receives email from customers)

</p>
<br />

<p>
   
![thisismyimage]()
</p>
<p>

-  Open Heidi SQL
   -  Create a new session, root/Password1
   -  Connect to the session
   -  Create a database called “osTicket”


-  MySQL Database: osTicket
   -  MySQL Username: root
   -  MySQL Password: Password1
   -  Click “Install Now!”
   
</p>
<br />

<p>
   
![thisismyimage]()
</p>
<p>

-    Delete: C:\inetpub\wwwroot\osTicket\setup
-    Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>
<br />

<p>

![thisismyimage]()
</p>
<p>

-    Browse to your help desk login page: http://localhost/osTicket/scp/login.php
-    End User login: http://localhost/osTicket/ 
</p>
<br />

<p>

![thisismyimage]()
</p>
<p>

-   Osticket has now been successfully deployed, congratulations
   -  The End.
</p>
<br />

