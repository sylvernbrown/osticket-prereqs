<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation (1/3)</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


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
- <strong>Link to Installation File:</strong> https://drive.google.com/drive/folders/1Na1sFRC39mexXaobzKW4VAsLuCyz4muv?usp=sharing
<h2>Installation Steps</h2>

<p>
0) Begin by collecting all necessary applications & ensure you are not missing any prerequisite programs.<br />
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
4) Navigate to the prerequestites folder and install both <strong>PHP Manager for IIS</strong> & the <strong>Rewrite Module</strong>. 
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
<br />
<br />
<br />
<br />
6)  Unzip <strong><i>php-7.3.8-nts-Win32-VC15-x86.zip</i></strong> and extract into <strong>C:PHP</strong><br />
  <br />
<img src="https://i.imgur.com/GxpQ8C8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />
<br />
<br />
<br />

<p>
7) Navigate to the prerequisites folder to complete additional instillations for back-end support of our osTicket system.  Install <strong>VC Redist</strong>.<br />
<br />
<br />
  <img src="https://i.imgur.com/zA7nQTH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <br/>
  <br/>
  <br/>
8) Install <strong>mySQL</strong>, ensure the following settings are in place when going through both the installation & setup wizards.<br />
  8a) Choose Setup Type: <strong>Typical</strong> <br/>
    <br />
    <br />
  <img src="https://i.imgur.com/Qt7qKgk.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
  <br />
  <br />
  <br />
  8b) MySQL Server Instance Configuration: <strong>Standard</strong>  <br/>
  <br />
  <img src="https://i.imgur.com/VyJmNZk.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br />
    <br />
    <br />
    <br />
  8c) Modify Security Settings: <strong>Pasword</strong> = "root"<br/>
  <br />
  <img src="https://i.imgur.com/szjPgy3.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
  <strong><i>Note: It's crucial that "root" or something you can easily remember is set as the password.  Otherwise, you'll be forced to start the entire process from scratch due to being unable to use MySQL.</i></strong>
    <br />
    <br />

</p>

<p>
9) Navigate to <strong>Internet Information Services (IIS)</strong>and open the application as an administrator.  Then, navigate to <strong>PHP Manager > Register New PHP Version</strong> and navigate to <strong>C:PHP</strong>. Select <strong>"php-cgi.exe"</strong>.  The executable path is shown below.<br />
  <br />
  <img src="https://i.imgur.com/b63ehHN.png" height="40%" width="60%" alt="Disk Sanitization Steps"/>
  <br />
  <br />
  <br />
10) Reload IIS by right-clicking on the "windows-vm" header on the left hand sidebar under "connections" selecting stop, waiting briefly, and then selecting start.<br />
  <br />
  <img src="https://i.imgur.com/BCi54zK.png" height="40%" width="60%" alt="Disk Sanitization Steps"/>
  <br />
  <br />
  <br />
11) Navigate to the loopback address 127.0.0.1 to confirm that the previous steps worked, if they have been executed effectively your web browser should display an image similar to the image shown below.<br />
  <br />
  <img src="https://i.imgur.com/gIVhcdI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
  <br />
  <Strong><i>Note: If by this step your web-browser isn't showing this image, go back to PHP Manager and ensure the PHP path is correct.</i></Strong>
</p>
  <br />
  <br />
  <br />
  
<p>
12) Now, we are going to install osTicket in place of this website we created, to do this we will navigate to the prerequisite file.  Within the prerequisite file, unzip the <strong>"osTicket-Installation-Files"</strong> folder.<br />
  <br />
  <img src="https://i.imgur.com/OpQj8Zy.png" height="80%" width="100%" alt="Disk Sanitization Steps"/>
</p>
  <br />
  <br />
  <br />
13) Extract this zip folder into a folder of your choice, but copy the <Strong>"upload"</Strong> folder into the directory <strong>(c:\inetpub\wwwroot)</strong>. Rename the <strong>"upload"</strong> folder <strong>"osTicket"</strong>.<br/>
  <br />
<img src="https://i.imgur.com/4wpBeln.png" height="60%" width="80%" alt="Disk Sanitization Steps"/>
</p>
  <br />
  <br />
  <br />

  <p>
14) Go back into <strong>Information Internet Services (IIS)</strong>, refresh the web-server again as explained previously.  Navigate to <strong>Sites > Default > osTicket > Browse*.80(http)</strong> and confirm that osTicket is installed.<br />
</p>
<br />
<p>
<img src="https://i.imgur.com/1i65nFd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<strong><i>Note: If osTicket is not showing up, or you are getting an error message run through steps 2-14 before starting from scratch.  Common troubleshooting could include ensuring osTicket is properly named in the C drive, ensuring prerequisite software is installed, and double-checking the PHP executable path.</i></strong>
</p>
  <br />
  <br />
  <br />

<p>
15) Notice the disabled extensions in the osTicket installation wizard.  Next, proceed to activate <i> necessary </i> extensions so osTicket can function properly.<br />
  <br />
  <img src="https://i.imgur.com/0ankb3Y.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />
    <br />
16) Navigate to PHP Manager and select <strong>"Enable or Disable an extension"</strong> and select the extensions that are listed as inactive on the osTicket installer.  I'd recommend the list of extensions provided below at a minimum.<br />
  <br />
  <img src="https://i.imgur.com/NboGmin.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />
    <br />
  
<p>
17) Navigate to <strong>C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php</strong>. Modify the <strong>"ost-sampleconfig.php"</strong> to <strong>"ost-config.php"</strong><br/>
  <i>Note: It's crucial that this <strong>"ost-config.php"</strong> file is labeled exactly this way</i><br/>
  <br />
  <img src="https://i.imgur.com/gSfVy07.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />
    <br />
18) Next, in the <strong>ost-config.php</strong> file disable inheritance by going <strong>Security > Advanced > Disable Inheritance</strong> <br/>
  <br />
  <img src="https://i.imgur.com/YM5iLn0.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
  <img src="https://i.imgur.com/sNo4pJ9.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />
    <br />
20) Set new permissions for everyone by going back into <strong>Security > Advanced > Add > Set Principal</strong>.  Name the principal "everyone" for the sake of simplicity, and set permissions to full-access as is shown below.<br/>
</p>
<br />
<p>

<img src="https://i.imgur.com/bZLaq40.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br/>
<img src="https://i.imgur.com/mtKk5ja.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
<strong><i>Note: This is purely for demonstration purposes and to display how to alter permissions, I do not recommend this configuration outside of a lab setting.</strong></i>
  <br />
  <br />
  <br />
21) Make sure that your principal has <strong>"full control</strong>.<br/>
<br />
<img src="https://i.imgur.com/qZcj7je.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
</p>
  <br />
  <br />
  <br />



<p>
22) Download & Install <strong>Heidi SQL</strong>.<br/>
  <br />
  <img src="https://i.imgur.com/xIkqm9o.png" height="60%" width="80%" alt="Disk Sanitization Steps"/>
    <br />
    <br />
    <br />
</p>
  
<p>
23) In the <strong>Heidi SQL</strong> session manager, create a new session.<br/>
  <br />
  <img src="https://i.imgur.com/RkG6aeA.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br/>
    <br/>
    <br/>
    <br/>
24) User: <strong>root</strong><br />
    Password: <strong>root</strong><br />
  <br />
  <img src="https://i.imgur.com/Q06VCZv.png" height="40%" width="60%" alt="Disk Sanitization Steps"/><br />
    <br />
    <br />
    <br />
25) Create a new database called <strong>osTicket</strong>, navigate to the <strong>[right click on session] > Databases > New Database</strong>.<br />
  <br />
  <img src="https://i.imgur.com/USX7x1B.png" height="60%" width="60%" alt="Disk Sanitization Steps"/><br/>
  <img src="https://i.imgur.com/nwLbNbv.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
    <br />
    <br />
    <br />
</p>

<p>
26) Continue setting-up with the osTicket installer in the web-browser. Fill in System Settings & Admin User information at your own discretion. Once you reach the <strong>"Database Settings"</strong> part of the installation the following information must be filled in.
  
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
  <p>
 27)  If osTicket is properly installed you should be at the point where you can access both the <strong>Admin</strong> and <strong>User</strong> panels. <br />
    <br />
    <img src="https://i.imgur.com/qhxljCx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
    <img src="https://i.imgur.com/xyTmmkA.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
  </p>
<br />
<br />
<br />
