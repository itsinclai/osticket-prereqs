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

- Install and configure IIS
- Set up a database using mySQL

<h2>Installation Steps</h2>

<b>Step 1: Enable IIS and CGI on Your VM</b>

- Open Control Panel > Programs > Programs and Features.
- Click Turn Windows Features On or Off.

<p>
![image](https://github.com/user-attachments/assets/34417fef-1147-467a-a929-8c1cf7305e48)
</p>
<p>

- In the features list, locate Internet Information Services (IIS) and check its box.
- Expand IIS and ensure that CGI is also enabled.
- Click OK to install and configure IIS and CGI.
</p>


<b>Step 2: Install PHP Manager for IIS</b>

Installing PHP Manager makes it easy to configure and manage PHP in IIS.

- Download PHP Manager for IIS from a trusted source or the official IIS extensions site.
- Run the installer and follow the on-screen instructions to complete the installation.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Step 3: Set Up PHP</b>

- Create a directory on your system called C:\PHP. This directory will house all the PHP files needed for osTicket to function.
- Download the PHP installation files (typically provided as a ZIP file).
- Extract the PHP files into the C:\PHP directory.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Step 4: Install Microsoft Visual C++ Redistributable</b>

- Next download and install the Microsoft Visual C++ Redistributable package that matches your system architecture.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Step 5: Install MySQL</b>

Next, install MySQL file. MySQL is a relational database management system that osTicket uses to store critical data, such as user accounts, ticketing information, and configuration settings.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

- Download and install MySQL.
- During installation, select the Standard Configuration option to simplify setup.

Now our database is installed!

<b>Step 6: Configure PHP in IIS</b>

IIS needs to know where PHP is installed to process PHP scripts for osTicket. By registering PHP with IIS, we’re connecting the two systems.
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

- Open IIS Manager as an administrator.
- Locate PHP Manager in IIS.
- Click Register New PHP Version and browse to the PHP folder (C:\PHP).
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

- Click Register New PHP Version and browse to the PHP folder (C:\PHP).
- Select the PHP executable file (php-cgi.exe) and confirm.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

- Next, we’re going to reload IIS meaning that we will start and stop the web server
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Step 7: Install osTicket</b>

osTicket’s files need to be placed in IIS’s root directory so that the web server can serve them to users.

- Download and extract the osTicket installation files (e.g., osTicket-v1.15.8.zip).
- Locate the upload folder inside the extracted files.
- Copy the upload folder into C:\inetpub\wwwroot.
- Rename the folder from upload to osTicket.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Step 8: Access osTicket</b>

This step ensures that osTicket is correctly installed and accessible through a web browser. If the page doesn’t load, it may indicate misconfiguration in previous steps.

- Open IIS Manager.
- Navigate to: [Your VM Name] > Sites > Default Web Site > osTicket.
- Click Browse on the right-hand side to open the osTicket site in your default browser.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Step 9: Verify Prerequisites and Enable PHP Extensions</b>

osTicket requires specific PHP extensions to unlock full functionality. These extensions add capabilities such as email handling (php_imap.dll), internationalization (php_intl.dll), and performance optimization.

- On the osTicket installation page, verify that PHP and MySQL prerequisites are checked.
- Open PHP Manager in IIS and click Enable or Disable an Extension.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Enable the following extensions:
- php_imap.dll
- php_intl.dll
- php_opcache.dll
- Refresh the osTicket page to confirm that the extensions are now enabled.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Now you will see that more of your recommended extensions are enabled.

<b>Step 10: Verify Prerequisites and Enable PHP Extensions</b>

osTicket requires a specific configuration file (ost-config.php) to store important settings like database credentials and other system configurations. By default, this file is provided as a sample (ost-sampleconfig.php). In this step we will rename it and set appropriate permissions.

- Navigate to the following directory C:\inetpub\wwwroot\osTicket\include.
- Locate the file named ost-sampleconfig.php.
- Rename it to ost-config.php.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Now we're going to set the file permissions.

- Right-click on the newly renamed ost-config.php file and select Properties.
- Go to the Security tab and click Edit.
- For the purposes of this lab, grant Full Control to Everyone:
- Click Add.
- Enter Everyone and click OK.
- Check the box for Full Control.
- Apply and close.

<b>Step 11: Begin osTicket Basic Installation</b>

- First your going to fill out your credentials for osTicket.
- Enter an admin Username and password

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Step 12: Connect Database to osTicket using HeidiSQL</b>

- Navigate to the osTicket-Installation-Files folder.
- Locate the HeidiSQL installer and install the application.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

- Open HeidiSQL and create a new connection:
- Launch the application.
- Click New Session.
- Enter the following credentials:
- Username: root
- Password: root
- Click Open to connect.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Next we will create the osTicket database:

- Once connected, right-click on the server name in the left panel.
- Select Create New > Database.
- Name the database: osTicket.
- Save and close HeidiSQL.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<b>Step 13: Finalize osTicket Setup </b>

This step completes the installation process by linking osTicket to the database you just created and setting up initial system credentials.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

- Go back to the osTicket installation page in your browser.
- Fill in the required fields:
- MySQL Database Name: osTicket
- MySQL Username: root
- MySQL Password: root
- Click Install Now!

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
