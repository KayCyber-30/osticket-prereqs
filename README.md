# osticket-prereqs<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />






<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create an Azure Virtual Machine Windows 10 with  4 vCPUs

  ![image](https://github.com/user-attachments/assets/4e04513f-a178-42ef-9e4e-874a6bbdcfbd)




- Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
We will use the files in this folder to install osTicket and some of the dependencies.

![image](https://github.com/user-attachments/assets/214d44e7-4504-41f7-b196-e199cc18ffb6)

- Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI

![image](https://github.com/user-attachments/assets/97255c0f-f641-4ecd-8aac-7e3887dfeb28)


- From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

![image](https://github.com/user-attachments/assets/cfd7b4bf-6bca-447d-ba97-d0034cebeb5a)
 

- From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

![image](https://github.com/user-attachments/assets/991e434d-f194-41c4-b197-80a1f5157c0c)

- Create the directory C:\PHP

![image](https://github.com/user-attachments/assets/995b0836-1e16-4653-80c8-24c801ff77db)


- From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

![image](https://github.com/user-attachments/assets/2aefde21-0aad-4b84-93e8-bd489882c675)


- From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

![image](https://github.com/user-attachments/assets/5cb63d1e-548a-4eae-a0b5-fd22fb04415a)


- From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->

![image](https://github.com/user-attachments/assets/fadcf814-f751-4f32-9a00-bc6f7c733086)


- Open IIS as an Admin, Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe), Reload IIS (Open IIS, Stop and Start the server)

![image](https://github.com/user-attachments/assets/f450d093-54d5-4b9a-9396-cbf51c92a3b4)

- Install osTicket v1.15.8
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, rename “upload” to “osTicket”, Reload IIS (Open IIS, Stop and start the server)

![image](https://github.com/user-attachments/assets/36758585-0be4-4413-a801-852d04ec9ce6)


- Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

![image](https://github.com/user-attachments/assets/34cce359-2a23-4cde-a3d8-523c1628656d)


- Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension.”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browser, and observe the changes

![image](https://github.com/user-attachments/assets/77436053-e02c-44c6-a6e3-ccbbe53af432)


- Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![image](https://github.com/user-attachments/assets/a27de6f3-aa3e-4f87-a311-7ac70be74e50)


- Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

![image](https://github.com/user-attachments/assets/1b039ec3-294b-4cfa-bf0b-15064890fc50)


- Continue setting up osTicket in the browser (click Continue)
Name Helpdesk
The default email (receives email from customers)

![image](https://github.com/user-attachments/assets/002c2bfa-3ccd-455b-a1c9-6a4e65dcc12a)


- From the “osTicket-Installation-Files” folder, install HeidiSQL.
Open Heidi SQL
Create a new session, root/root
Connect to the session
Create a database called “osTicket”



- Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”









  









<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
