<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this lab i demonstrate the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Create Microsoft Azure Account
- Create a resource group
- Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPU's
- Allow for the creation of a new virtual network (vnet) when creating the new virtual machine
- Use installation files from google drive https://mail.google.com/mail/u/2/#inbox

<h2>Installation Steps</h2>
<p>
Create an Azure Virtual Machine 
<br>- Windows 10, 4 vCPUs </b>
<br>- Name: Vm-osticket </b>
<br>- Username: labuser </b> 
<br>- Password: osTicketPassword1! </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/ac5e830d-4fc7-46d8-88f4-1f4db1f89e21)




<p>
Install / Enable IIS in Windows WITH
CGI and Common HTTP Features 
<br>-  World Wide Web Services -> Application Development Features -> </b>
<br>- [X] CGI </b>
<br>- [X] Common HTTP Features </b> 
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/9af90950-677e-4539-af4c-7b237bd55e49)

<p>
AND IIS Management Console
<br>-  Internet Information Services -> Web Management Tools -> IIS Management Console </b>
<br>- [X]  IIS Management Console </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/3a83dcf4-38df-495a-89e2-e997958e1b17)

<p>
<br>-  From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) </b>
</p>
<p>
<br>-  From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi) </b>
</p>
<p>
<br>-  Create the directory C:\PHP </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/fa7969fb-1f6c-4355-b0a3-850dd848247d)


<p>
<br>-  From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/c15ac37b-2c6a-4bfe-a18a-67558257e9cd)


<p>
<br>-  from the installation files, download and install VC_redist.x86.exe</b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/d918f2e0-1d1b-47d5-9518-4c7df25d2b1c)


<p>
From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
<br>- Typical Setup -> </b>
<br>- Standard Configuration -> </b>
<br>- Password1 </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/e9541bfd-351c-4d08-8152-bdb84b747b1c)

<p>
<br>- Open IIS as an Admin</b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/1dbd1163-2625-42ce-9427-b619c5c97281)

<p>
<br>- Register PHP from within IIS</b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/581ca840-d0d8-459c-abd9-7fc8331411da)

<p>
<br>- Reload IIS (Open IIS, Stop and Start the server)</b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/75cf469c-bc5b-47ee-b0c7-c7c32f61bfd8)

<p>
Install osTicket v1.15.8
<br>- Download osTicket from the Installation Files Folder </b>
<br>- Extract and copy “upload” folder to c:\inetpub\wwwroot </b>
<br>- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/a4bb7eea-5cfc-474b-bdeb-2bc6d569e474)

<p>
<br>- Reload IIS (Open IIS, Stop and Start the server)</b>
</p>

<p>
Go to sites -> Default -> osTicket
<br>- On the right, click “Browse *:80” </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/c9e5ee6c-36d2-4b53-992f-69b02ff502a0)

<p>
enable extensions
<br>- Go back to IIS, sites -> Default -> osTicket </b>
<br>- Double-click PHP Manager </b>
<br>- Click “Enable or disable an extension” </b>
  <br>- Enable: php_imap.dll </b>
  <br>- Enable: php_intl.dll </b>
  <br>- Enable: php_opcache.dll </b>
<br>- Refresh the osTicket site in your browse, observe the changes </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/3d2c4564-b97f-40fe-975c-87b6bf4798ad)

<p>
Rename: ost-config.php
<br>- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php </b>
<br>- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/b8ecae0d-6df1-4586-a3c0-65f804c9e01c)



<p>
Assign Permissions: ost-config.php
<br>- Disable inheritance -> Remove All </b>
<br>- New Permissions -> Everyone -> All </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/9493ae6c-cfa2-44c1-8d1b-0db61770c1fe)

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/3f6a9719-8620-4ea2-9ff4-a0b3539f9bb9)

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/7d306299-dbc4-4856-a296-e2242e4ab2d3)



<p>
Continue Setting up osTicket in the browser (click Continue)
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/724586f2-b746-4398-9378-8b16560efc20)


<p>
From the Installation Files, download and install HeidiSQL
<br>- Open Heidi SQL </b>
<br>- Create a new session, root/Password1 </b>
<br>- Connect to the session </b>
<br>- Create a database called “osTicket” </b>
</p>

<p>
Continue Setting up osticket in the browser
<br>- MySQL Database: osTicket </b>
<br>- Click “Install Now!” </b>
</p>

![image](https://github.com/IZEK4K/osticket-prereqs/assets/90485066/b438d0d8-6e36-4402-8fc8-51d4d006c471)


<p>
Browse to the help desk login page: http://localhost/osTicket/scp/login.php
</p>

<p>
Continue Setting up osticket in the browser
<br>- Delete: C:\inetpub\wwwroot\osTicket\setup </b>
<br>- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php </b>
</p>

Done! osticket is now ready for use






