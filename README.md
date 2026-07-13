<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11 Pro (25H2)</b>

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Creating the Azure Virtual Machine</b> — Provisioned a Windows 10 virtual machine in Microsoft Azure with 4 vCPUs, configured with a username and password, to serve as the osTicket hosting environment.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Logging into the VM via Remote Desktop</b> — Connected to the Azure virtual machine remotely using Remote Desktop Protocol (RDP) to begin the osTicket installation process.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Downloading and unzipping the installation files</b> — Downloaded the osTicket Installation Files zip archive inside the VM and extracted its contents to the desktop for use during setup.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Enabling IIS with CGI</b> — Enabled Internet Information Services (IIS) in Windows Features, including CGI support under Application Development Features, to allow the server to host web applications.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Installing PHP Manager for IIS</b> — Installed PHP Manager for IIS to allow IIS to manage and configure PHP settings needed to run osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Installing the IIS Rewrite Module</b> — Installed the URL Rewrite Module for IIS to enable clean URL routing required by osTicket
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Creating the C:\PHP directory</b> — Created a dedicated PHP directory at C:\PHP to house the PHP runtime files used by the web server.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Extracting PHP 7.3.8 into C:\PHP</b> — Unzipped the PHP 7.3.8 runtime into the C:\PHP folder so IIS can use it to process PHP-based web applications.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Installing Visual C++ Redistributable</b> — Installed VC_redist.x86.exe, a required dependency that provides runtime components PHP relies on to function.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Installing MySQL 5.5.62</b> — Installed the MySQL database server using Typical Setup, then configured it via the Configuration Wizard using Standard Configuration with root credentials.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Opening IIS as Administrator</b> — Launched IIS Manager with administrative privileges to configure the web server settings for osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Registering PHP in IIS</b> — Used PHP Manager within IIS to register the PHP executable (php-cgi.exe) so IIS can process PHP files
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Reloading IIS</b> — Stopped and restarted the IIS server to apply the PHP registration and ensure all configurations were active.</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Installing osTicket v1.15.8</b> — Unzipped the osTicket package and copied the "upload" folder into the IIS web root directory (C:\inetpub\wwwroot), then renamed it to "osTicket."
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Reloading IIS again</b> — Restarted IIS after placing the osTicket files to ensure the new site was recognized by the server.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Browsing to the osTicket site</b> — Navigated to the osTicket site through IIS (Sites > Default > osTicket > Browse *:80) to verify it was loading in the browser.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Enabling required PHP extensions</b> — Opened PHP Manager in IIS and enabled three required extensions — php_imap.dll, php_intl.dll, and php_opcache.dll — then refreshed the browser to confirm the changes.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Renaming ost-sampleconfig.php</b> — Renamed the sample configuration file from ost-sampleconfig.php to ost-config.php in the osTicket include directory to activate the configuration file.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Setting permissions on ost-config.php</b> — Disabled inherited permissions on ost-config.php and assigned full access to "Everyone," allowing the osTicket installer to write to the file during setup.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Running the osTicket browser setup</b> — Completed the osTicket installation form in the browser, entering the helpdesk name and default email address for receiving customer tickets.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Installing HeidiSQL and creating the database</b> — Installed HeidiSQL, connected to MySQL using root credentials, and created a new database named "osTicket" for the application to use.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Completing the osTicket installation</b> — Entered the MySQL database credentials into the osTicket browser installer and clicked "Install Now" to finalize the installation.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Verifying the installation</b> — Confirmed a successful installation by navigating to the helpdesk login page (localhost/osTicket/scp/login.php) and the end-user ticket portal.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Post-install cleanup</b> — Deleted the setup directory from the osTicket installation folder and changed the permissions on ost-config.php to Read-only to secure the system.
</p>
<br />
