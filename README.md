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
<p>
<br>-  From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP </b>
</p>
