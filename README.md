<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>


<p>
1) Log into Microsoft Azure (or any alternative virtual machine environment) and create a new virtual machine.  Ensure the virtual machine is running Windows 10 and has at least 2vCPUs.
</p>
<br />
<p>
<img src="https://i.imgur.com/S63hZuT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Bx0BqcA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<br />

<p>
2a) Navigate to: <strong>Control Panel > Programs > Programs and Features</strong>. Then, select <strong>"Turn Windows Features on or off"</strong>
<br />
<br />
2b) Select: <strong>Internet Information Services > World Wide Web Services > Application Development Features > <em>CGI</em></strong>.  Select OK and wait for changes to apply.
</p>
<br />
<p>
<img src="https://i.imgur.com/gEED7Tc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/RvxtdMp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<br />

<p>
3a) Navigate to your prerequestites folder and install and enable both <strong>PHP Manager for IIS</strong> & the <strong>Rewrite Module</strong>. 
  <br/>
  <br/>
3b) Navigate to: <strong>This PC > Windows (C:)</strong> and create the folder <strong>"PHP"</strong>
</p>
<br />
<p>
<img src="https://i.imgur.com/vMu6dKI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
4a) We will be going back to the prerequisites folder to conduct additional instillations for back-end support of our osTicket system.  Install VC Redist.
<br />
<br />
4b) Install mySQL, be sure make sure the following are in place when going through both the installation & setup wizards.  This step is crucial for the rest of the osTicket system to be installed properly so double-check before continuing to Step 5.<br>
  1)Choose Setup Type: Typical <br/>
  2)MySQL Server Instance Configuration: Standard  <br/>
  3)Modify Security Settings: Pasword = "root"<br/>
</p>
<br />
<p>
<img src="https://i.imgur.com/Qt7qKgk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/VyJmNZk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/szjPgy3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<br />

<p>
5) Navigate to Internet Information Services (IIS) and open the application as an administrator.  Then, navigate to PHP Manager and navigate to the aforementioned PHP folder from step 3b.  Within this folder, select "php-cgi.exe" to ensure PHP Manager can find the executable file.<br />
  <br />
5b)Reload IIS by right-clicking on the "windows-vm" header on the left hand sidebar under "connections" selecting stop, waiting briefly, and then selecting start.  After this step the web server should've refreshed.<br />
  <br />
5c) Navigate to the loopback address 127.0.0.1 to confirm that the previous steps worked, if they have been executed effectively your web browser should display an image similar to the second image in this step.<br />
  <br />
</p>
<br />
<p>
<img src="https://i.imgur.com/b63ehHN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Bv2nY45.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<br />

<p>
6a) Now, we are goign to install osTicket in place of this website we created, to do this we will navigate to the prerequisite file.  Within the prerequisite file, unzip the "osTicket-Installation-Files" folder.  If you didn't assemble a prerequisite file you can simply download the latest version of osTicket and follow along.<br />

6b)Extract this zip folder into a folder of your choice, but copy the "upload" folder into the directory (c:\inetpub\wwwroot). Rename the "upload" folder "osTicket".<br />

6c)
</p>
<br />
<p>
<img src="https://i.imgur.com/4wpBeln.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<br />

7) Go back into Information Internet Services (IIS), refresh the web-server again as explained previously.  Navigate to Sites > Default > osTicket and confirm that osTicket is installed.
</p>
<br />
<p>
<img src="https://i.imgur.com/qDAYlUS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<i>Note: If osTicket is not showing up, or you are getting an error message run through steps 2-6 before starting from scratch.  Common troubleshooting could include ensuring osTicket is properly named in the C drive, and ensuring prerequisite software is installed.</i>
</p>
<br />
<br />
<br />
<br />

<p>
8) Notice how there are disabled extensions in the osTicket installation wizard.  Now, we are goign to activate <i> necessary </i> extensions so osTicket can function properly. 
8b) Navigate to PHP Manager and select "Enable or disable an extension" and select the plugins that are listed on the website.
</p>
<br />
<p>
<img src="https://i.imgur.com/NboGmin.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
<p/>
<br />
<br />
<br />
<br />

<p>
9a) Navigate to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php. Modify the "ost-sampleconfig.php" to "ost-config.php"<br/>
  <i>Note: It's crucial that this "ost-config.php" file is labeled in this way exactly</i><br/>
9b) Next, in the ost-config.php file disable inheritance by going Security > Advanced > Disable Inheritance <br/>
9c) Set new permissions for everyone by going back into Security > Advanced > Add > Set Principal.  Name the principal "everyone" for the sake of simplicity, and set permissions to full-access as is shown below.<br/>
</p>
<br />
<p>
<img src="https://i.imgur.com/YM5iLn0.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
<img src="https://i.imgur.com/sNo4pJ9.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
<img src="https://i.imgur.com/bZLaq40.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
<img src="https://i.imgur.com/mtKk5ja.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
<img src="https://i.imgur.com/qZcj7je.png" height="40%" width="40%" alt="Disk Sanitization Steps"/><br/>
</p>
<br />
<br />
<br />
<br />

<p>
10a) Continue setting-up with the osTicket installer in the web-browser. Fill in System Settings & Admin User information at your own discretion.<br/>
10b) Database Settings: Mandatory Settings (Ensure accuracy before moving on to next step)<br/>
  1)MySQL Database = osTicket<br/>
  2)MySQL Username = root<br/>
  2)MySQL Password = root<br/>
</p>
<br />
<p>
<img src="https://i.imgur.com/4CEsXfH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<br />

<p>
11a) Download & Install Heidi SQL.<br/>
11b) 
</p>
<br />
<p>
<img src="https://i.imgur.com/S63hZuT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Bx0BqcA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
<br />
<br />

