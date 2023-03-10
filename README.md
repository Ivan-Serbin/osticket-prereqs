<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Virtual Machine 
- Enable ISS using CGI
- osTicket installation files
- HeidiSQL
- Install C++ distributions
- "installation files: https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6" 

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/VdP4MxR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

First start off by creating a virtual machine. As seen in the image above, the VM was created in Microsoft Azure. Following that create a username and password. Once the VM is created, then RDC into the VM and login. 
</p>
<br />

<p>
<img src="https://i.imgur.com/v5teA3W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Once inside the remote desktop, go to windows > control panel > programs > turn windows features on or off > internet information services (IIS) > world wide web services > appliation developer > CGI > ok. This will enable us to later install PHP manager.
</p>
<br />

<p>
<img src="https://i.imgur.com/JwsT3TO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Following those steps the next thing is to install is all of the installation files as specified from the "Installation Files", download and install PHP Manager for IIS > download and install the Rewrite Module > Create the directory C:\PHP > download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP > download and install VC_redist.x86.exe > download and install MySQL 5.5.62. After all of that is done we can continue to launch the configuration wizard for the MySQL program and choose the standard configuration, click next until greeted with a root password screen, then choose a password to your liking.
</p>
<br />

<p>
<img src="https://i.imgur.com/y02siPj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Open IIS as an Admin, register PHP from within IIS then Reload IIS (Open IIS, Stop and Start the server). Install osTicket, download osTicket from the "Installation Files" folder. Extract and copy ???upload??? folder to c:\inetpub\wwwroot, then Within c:\inetpub\wwwroot, rename ???upload??? to ???osTicket???. Reload IIS (Open IIS, Stop and Start the server). Go to sites > Default > osTicket. On the right, click ???Browse *:80???. Note that some extensions are not enabled. Go back to IIS, sites > Default > osTicket > Double-click PHP Manager > Click ???Enable or disable an extension??? > Enable: php_imap.dll, Enable: php_intl.dll, Enable: php_opcache.dll > Refresh the osTicket site in your browse, observe the changes. Following that rename: ost-config.php from: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to: C:\inetpub\wwwroot\osTicket\include\ost-config.php > Assign Permissions: ost-config.php > Disable inheritance > Remove All > New Permissions > Everyone > All. Continue Setting up osTicket in the browser (click Continue), name Helpdesk, default email (receives email from customers). From the Installation Files, download and install HeidiSQL. Then open Heidi SQL > create a new session > root and created password > connect to the session > create a database called ???osTicket???. Continue Setting up osticket in the browser, then  click ???Install Now!???
</p>
<br />

<p>
<img src="https://i.imgur.com/ShP8Aim.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
 Congradulations you will have now successfully installed osTicket and can not start using it to learn how the ticketing system works. Now for the finishing touches delete: C:\inetpub\wwwroot\osTicket\setup, Set Permissions to ???Read??? only: C:\inetpub\wwwroot\osTicket\include\ost-config.php and thats all!


  
  
