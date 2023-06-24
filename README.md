<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
Welcome, this tutorial will outline the prerequisites and installation of the open-source help desk ticketing system, osTicket.
Prior to the Installation steps, we have created a Virtual Machine in Microsoft Azure and connected to it using remote desktop. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine Windows 10, 4vCPUs
- osTicket Installation files
- Heidi SQL


<h2>Installation Steps</h2>

<p> 
Step 1: If not done so already, please connect to your Virtual Machine you created in Azure using remote desktop.  </p>
<img src="https://i.imgur.com/7lNy37j.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Step 2: We will Install/Enable IIS in Windows with CGI. This is the Web Server that the osTicket will be running on. </p>
Go to Windows Features -> Turn Windows features on or off -> Scroll down to Internet Information Services, Click & Expand - Expand World Wide Web Services -> Expand Application Development Features -> Checkmark CGI </p>
<br />
<img src="https://i.imgur.com/7EFtFWh.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Step 3: We will now download and install, PHP Manager for IIS & the Rewrite Module.  </p> 
Afterwards we will create the Directory C:\PHP. </p> 
--> Then download PHP 7.3.8 and unzip the contents into C:\PHP. </p> 
For these installation files, you may use the provided link here: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6.   
</p>
<img src="https://i.imgur.com/5RzHq0w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
Step 4: Download and install VC redist.x86.exe & MySQL 5.5.62  </p> 
-> Launch Wizard -> Standard Configuration -> Create a simple password (Do not forget). 
  </p>
<img src="https://i.imgur.com/TcGcQ2J.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/cFQRZoX.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ZG7Qe2L.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Step 5: Next we will Open IIS as an Admin and Register PHP from with IIS. </p>
Please refer to the pictures for further detail. 
</p>
<img src="https://i.imgur.com/tOCxG7A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/OYtUFcr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p>
Step 6: We will download and install osTicket v1.15.8  </p> 
-> Extract and copy "upload" folder to c:\inetpub\wwwroot -> Within c:\inetpub\wwwroot, Rename "upload" to "osTicket" </p>
Now go back to the IIS and Restart the server, Next Go to Sites -> Default -> osTicket -> On the right panel, click "Browse *:80"
  </p>
<img src="https://i.imgur.com/5nY5xXS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/wg8znSi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/xmzdR18.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />

<p>
Step 7: Next we will smoothen out the osTicket experience by enabling 3 extensions inside of the IIS application. </p> 
To do this, go to Sites -> Default -> osTicket -> Click PHP manager. Click on "Disable or enable an extension":

Enable: -> php_imap.dll -> php_intl.dll -> php_opcache </p> 
Next, we will rename: > C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php </p> 
To: --> > C:\inetpub\wwwroot\osTicket\include\ost-config.php. </p> 
Afterwards --> Configure the Properties, and Assign Permissions. -> Disable all Inheritances -> Add a New Permission -> "Everyone".

  </p>
<img src="https://i.imgur.com/3q9hLD4.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ZQ6wYWU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/rULYjG5.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/2Y6SIxt.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />

<p>
Step 8: Next we will download and install HeidiSQL. </p> 
For this demonstration, I have used the username "root" and a simple password. </p>
Now we will create a database called "osTicket"  

</p>
<img src="https://i.imgur.com/m3eBOfS.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/9apEHba.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />

<p>
Step 9: Continue Setting up osTicket in the browser and plug in fictious credentials. </p> 
Use the HeidiSQL database credentials to fill out the Database settings portion. </p>
 

</p>
<img src="https://i.imgur.com/brq3jR3.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Pqu5hqw.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/nWZBb4R.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>

<br />
<p>
Step 10: For the final tasks we will clean up and delete the osTicket's "setup" file: C:\inetpub\wwwroot\osTicket\setup </p> 
--> Then Set Permissions to “Read” only for: C:\inetpub\wwwroot\osTicket\include\ost-config.php </p>
--> Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php). </p> 
Congratulations, the setup for osTicket is complete! </p>


</p>
<img src="https://i.imgur.com/cTlws6X.png" height="85%" width="85%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/EgLMFhy.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
