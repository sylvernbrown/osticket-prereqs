<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.  For purposes of demonstration & practicing with Microsoft Azure, the entirety of this tutorial will be taking place in a virtual machine on the cloud.  If you're installing on  a local machine, skip to step 2 and begin the tutorial there.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Subscription
- Windows App for MacOS (To access the Azure VM)
- Internet Information Services (IIS)
- MySQL Server (version 5.5)
- osTicket (version 1.15.8)
- HeidiSQL (version 12.3.0.6589)
- PHP (version 7.3.8)
- PHP Manager For IIS (v1.5)
- VC Redist
- Rewrite Module

<h2>Installation Steps</h2>

<p>
0) Begin by collecting all necessary applications & make sure you are not missing any programs.<br />
  <br />
  <br />
<img src="https://i.imgur.com/BZRDB1w.png" height="80%" width="100%" alt="Disk Sanitization Steps"/><br/>
</p>
<br />
<br />
<br />
<br />

<p>
1) Log into <strong>Microsoft Azure</strong> (or any alternative virtual machine environment) and create a new virtual machine.  Ensure the virtual machine is running <strong>Windows 10</strong> and has at least <strong>2vCPUs</strong>.
</p>
<p>
<img src="https://i.imgur.com/S63hZuT.png" height="80%" width="100%" alt="Disk Sanitization Steps"/><br/>
<img src="https://i.imgur.com/Bx0BqcA.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<br />

<p>
2) Navigate to: <strong>Control Panel > Programs > Programs and Features</strong>. Then, select <strong>"Turn Windows Features on or off"</strong>
<br />
<br />
<img src="https://i.imgur.com/gEED7Tc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<p>
3) Select: <strong>Internet Information Services > World Wide Web Services > Application Development Features > <em>CGI</em></strong>.  Select OK and wait for changes to apply.<br />
<br />
<img src="https://i.imgur.com/RvxtdMp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<br />

<p>
4) Navigate to your prerequestites folder and install and enable both <strong>PHP Manager for IIS</strong> & the <strong>Rewrite Module</strong>. 
  <br/>
  <br/>
<img src="https://i.imgur.com/vMu6dKI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<p>
5) Navigate to: <strong>This PC > Windows (C:)</strong> and create the folder <strong>"PHP"</strong> <br />
  <br />
<img src="https://i.imgur.com/AV5LCR0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  <i>Note: It's important that the PHP folder is in this location as we are going to come back to this part for an executable file.  Be sure to double check before progressing to step 4.</i>
</p>
<br />
<br />
<br />
<br />

<p>
6) We will be going back to the prerequisites folder to conduct additional instillations for back-end support of our osTicket system.  Install <strong>VC Redist</strong>.<br />
<br />
<br />
  <img src="https://i.imgur.com/zA7nQTH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <br/>
  <br/>
  <br/>
7) Install <strong>mySQL</strong>, be sure make sure the following are in place when going through both the installation & setup wizards.<br />
  7a) Choose Setup Type: <strong>Typical</strong> <br/>
    <br />
    <br />
  <img src="https://i.imgur.com/Qt7qKgk.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
  <br />
  <br />
  <br />
  7b) MySQL Server Instance Configuration: <strong>Standard</strong>  <br/>
  <br />
  <img src="https://i.imgur.com/VyJmNZk.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br />
    <br />
    <br />
    <br />
  7c) Modify Security Settings: <strong>Pasword</strong> = "root"<br/>
  <br />
  <img src="https://i.imgur.com/szjPgy3.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />

</p>

<p>
8) Navigate to <strong>Internet Information Services (IIS)</strong>and open the application as an administrator.  Then, navigate to <strong>PHP Manager</strong> and navigate to the PHP folder from <strong>Step 5</strong>.  Within this folder, select <strong>"php-cgi.exe"</strong> to ensure PHP Manager can find the executable file.<br />
  <br />
  <img src="https://i.imgur.com/b63ehHN.png" height="40%" width="60%" alt="Disk Sanitization Steps"/>
  <br />
  <br />
  <br />
9) Reload IIS by right-clicking on the "windows-vm" header on the left hand sidebar under "connections" selecting stop, waiting briefly, and then selecting start.<br />
  <br />
  <img src="https://i.imgur.com/BCi54zK.png" height="40%" width="60%" alt="Disk Sanitization Steps"/>
  <br />
  <br />
  <br />
10) Navigate to the loopback address 127.0.0.1 to confirm that the previous steps worked, if they have been executed effectively your web browser should display an image similar to the image shown below.<br />
  <br />
  <img src="https://i.imgur.com/gIVhcdI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <br />
  <Strong><i>Note: If by this step your web-browser isn't showing this image, go back to PHP Manager and ensure the PHP directory is correct as stated in Step 8.</i></Strong>
</p>
  <br />
  <br />
  <br />
  
<p>
11) Now, we are going to install osTicket in place of this website we created, to do this we will navigate to the prerequisite file.  Within the prerequisite file, unzip the "osTicket-Installation-Files" folder.  If you didn't assemble a prerequisite file you can simply download the latest version of osTicket and follow along.<br /></p>
  <p>
12) Extract this zip folder into a folder of your choice, but copy the "upload" folder into the directory <strong>(c:\inetpub\wwwroot)</strong>. Rename the <strong>"upload"</strong> folder <strong>"osTicket"</strong>.<br/>
  <br />
<img src="https://i.imgur.com/4wpBeln.png" height="40%" width="60%" alt="Disk Sanitization Steps"/>
</p>
  <br />
  <br />
  <br />

  <p>
13) Go back into <strong>Information Internet Services (IIS)</strong>, refresh the web-server again as explained previously.  Navigate to <strong>Sites > Default > osTicket</strong> and confirm that osTicket is installed.<br />
</p>
<br />
<p>
<img src="https://i.imgur.com/1i65nFd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<i>Note: If osTicket is not showing up, or you are getting an error message run through steps 2-6 before starting from scratch.  Common troubleshooting could include ensuring osTicket is properly named in the C drive, and ensuring prerequisite software is installed.</i>
</p>
  <br />
  <br />
  <br />

<p>
14) Notice how there are disabled extensions in the osTicket installation wizard.  Now, we are goign to activate <i> necessary </i> extensions so osTicket can function properly.<br />
  <br />
  <img src="https://i.imgur.com/0ankb3Y.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />
    <br />
15) Navigate to PHP Manager and select "Enable or disable an extension" and select the plugins that are listed on the website.<br />
  <br />
  <img src="https://i.imgur.com/NboGmin.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />
    <br />
  
<p>
16) Navigate to <strong>C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php</strong>. Modify the <strong>"ost-sampleconfig.php"</strong> to <strong>"ost-config.php"</strong><br/>
  <i>Note: It's crucial that this <strong>"ost-config.php"</strong> file is labeled in this way exactly</i><br/>
  <br />
  <img src="https://i.imgur.com/gSfVy07.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />
    <br />
17) Next, in the ost-config.php file disable inheritance by going Security > Advanced > Disable Inheritance <br/>
  <img src="https://i.imgur.com/YM5iLn0.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
  <img src="https://i.imgur.com/sNo4pJ9.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />
    <br />
18) Set new permissions for everyone by going back into <strong>Security > Advanced > Add > Set Principal</strong>.  Name the principal "everyone" for the sake of simplicity, and set permissions to full-access as is shown below.<br/>
</p>
<br />
<p>

<img src="https://i.imgur.com/bZLaq40.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br/>
<img src="https://i.imgur.com/mtKk5ja.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
  <br />
  <br />
  <br />
19) Make sure that your principal has <strong>"full control</strong>.<br/>
<br />
<img src="https://i.imgur.com/qZcj7je.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br/>
</p>
  <br />
  <br />
  <br />



<p>
20) Download & Install <strong>Heidi SQL</strong>.<br/>
  <br />
  <img src="https://i.imgur.com/xIkqm9o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
    <br />
    <br />
    <br />
</p>
  
<p>
21) In the <strong>Heidi SQL</strong> session manager, create a new session.<br/>
  <br />
  <img src="https://i.imgur.com/RkG6aeA.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br/>
    <br/>
    <br/>
    <br/>
22) User: <strong>root</strong><br />
    Password: <strong>root</strong><br />
  <br />
  <img src="https://i.imgur.com/Q06VCZv.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br />
    <br />
    <br />
    <br />
23) Create a new database called <strong>osTicket</strong>, navigate to the <strong>[right click on session] > Databases > New Database</strong>.<br />
  <br />
  <img src="https://i.imgur.com/USX7x1B.png" height="60%" width="60%" alt="Disk Sanitization Steps"/><br/>
  <img src="https://i.imgur.com/nwLbNbv.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />
    <br />
</p>

<p>
24) Continue setting-up with the osTicket installer in the web-browser. Fill in System Settings & Admin User information at your own discretion. Once you reach the <strong>"Database Settings"</strong> part of the installation the following information must be filled in.
  
  <strong>Database Settings:</strong><br />
  <br />
  1)MySQL Database = <strong>osTicket</strong><br/>
  2)MySQL Username = <strong>root</strong><br/>
  3)MySQL Password = <strong>root</strong><br/>
  <br />
  <br />
<img src="https://i.imgur.com/4CEsXfH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />

 25)  If osTicket is properly installed you should be at the point where you can access both the <strong>Admin</strong> and <strong>User</strong> panels.

