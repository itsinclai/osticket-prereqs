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

![image](https://github.com/user-attachments/assets/0acddc92-7930-483b-ad9b-0b2bc893de72)


- In the features list, locate Internet Information Services (IIS) and check its box.
- Expand IIS and ensure that CGI is also enabled.
- Click OK to install and configure IIS and CGI.
</p>


<b>Step 2: Install PHP Manager for IIS</b>

Installing PHP Manager makes it easy to configure and manage PHP in IIS.

- Download PHP Manager for IIS from a trusted source or the official IIS extensions site.
- Run the installer and follow the on-screen instructions to complete the installation.

![image](https://github.com/user-attachments/assets/4963077b-9f7a-44b9-bab5-1acf608fe4f9)


<b>Step 3: Set Up PHP</b>

Create a directory on your system called C:\PHP. This directory will house all the PHP files needed for osTicket to function.

- Download the PHP installation files (typically provided as a ZIP file).
- Extract the PHP files into the C:\PHP directory.

![image](https://github.com/user-attachments/assets/e2ce2bee-fe93-47de-86b5-d14c83eaf02b)


<b>Step 4: Install Microsoft Visual C++ Redistributable</b>

- Next download and install the Microsoft Visual C++ Redistributable file from within the osTicket Installation folder.

![image](https://github.com/user-attachments/assets/1b426dcb-0842-4efe-8aa3-fca3734cfbb2)


<b>Step 5: Install MySQL</b>

Next, install MySQL file. MySQL is a relational database management system that osTicket uses to store critical data, such as user accounts, ticketing information, and configuration settings.

![image](https://github.com/user-attachments/assets/715cd77d-83d9-4a63-92bd-2933b7c20f7c)


- Download and install MySQL.
- During installation, select the Standard Configuration option to simplify setup.

Now our database is installed.

<b>Step 6: Configure PHP in IIS</b>

IIS needs to know where PHP is installed to process PHP scripts for osTicket. By registering PHP with IIS, we’re connecting the two systems.

![image](https://github.com/user-attachments/assets/3c18846c-1178-4c77-b5eb-330c13337d49)

- Open IIS Manager as an administrator.
- Locate PHP Manager in IIS.

![image](https://github.com/user-attachments/assets/6cbcb5b4-ead9-4955-92fb-6b007308872e)

- Click Register New PHP Version and browse to the PHP folder (C:\PHP).
- Select the PHP executable file (php-cgi.exe) and confirm.

![image](https://github.com/user-attachments/assets/83062d67-b9cf-468e-a428-fdf8983c6771)

- Next, we’re going to reload IIS meaning that we will start and stop the web server

![image](https://github.com/user-attachments/assets/10edea1e-7f71-41fc-9af9-3187fd569428)

<b>Step 7: Install osTicket</b>

osTicket’s files need to be placed in IIS’s root directory so that the web server can serve them to users.

- Download and extract the osTicket installation files (e.g., osTicket-v1.15.8.zip).
- Locate the upload folder inside the extracted files.
- Copy the upload folder into C:\inetpub\wwwroot.
- Rename the folder from upload to osTicket.

![image](https://github.com/user-attachments/assets/c93568dd-6914-48c1-9e45-1eae03d54b52)

<b>Step 8: Access osTicket</b>

This step ensures that osTicket is correctly installed and accessible through a web browser. If the page doesn’t load, it may indicate misconfiguration in previous steps.

- Open IIS Manager.
- Navigate to: [Your VM Name] > Sites > Default Web Site > osTicket.
- Click Browse on the right-hand side to open the osTicket site in your default browser.

![image](https://github.com/user-attachments/assets/d24bf4ee-cc63-4c61-a247-132d033b6e90)

<b>Step 9: Verify Prerequisites and Enable PHP Extensions</b>

osTicket requires specific PHP extensions to unlock full functionality. These extensions add capabilities such as email handling (php_imap.dll), internationalization (php_intl.dll), and performance optimization.

- On the osTicket installation page, verify that PHP and MySQL prerequisites are checked.
- Open PHP Manager in IIS and click Enable or Disable an Extension.

![image](https://github.com/user-attachments/assets/ea684640-7712-4655-9fa1-ddc18330c873)

Enable the following extensions:
- php_imap.dll
- php_intl.dll
- php_opcache.dll
- Refresh the osTicket page to confirm that the extensions are now enabled.

![image](https://github.com/user-attachments/assets/48ae505d-c1fd-47b6-a482-03c864661832)

Now you will see that more of your recommended extensions are enabled.

<b>Step 10: Verify Prerequisites and Enable PHP Extensions</b>

osTicket requires a specific configuration file (ost-config.php) to store important settings like database credentials and other system configurations. By default, this file is provided as a sample (ost-sampleconfig.php). In this step we will rename it and set appropriate permissions.

![image](https://github.com/user-attachments/assets/6bb55b37-eb69-453b-a4be-787d26155e1d)

- Navigate to the following directory C:\inetpub\wwwroot\osTicket\include.
- Locate the file named ost-sampleconfig.php.
- Rename it to ost-config.php.

Now we're going to set the file permissions.

![image](https://github.com/user-attachments/assets/db28ac3d-467f-4f46-be7d-f7ea3036dd69)

- Right-click on the newly renamed ost-config.php file and select Properties.
- Go to the Security tab and click Edit.
- For the purposes of this lab, grant Full Control to Everyone:
- Click Add.
- Enter Everyone and click OK.
- Check the box for Full Control.
- Apply and close.

<b>Step 11: Begin osTicket Basic Installation</b>

- First you're going to fill out your credentials for osTicket.
- Enter an admin Username and password

![image](https://github.com/user-attachments/assets/56057eb1-7e1b-487c-84ab-7a98fb3e771e)


<b>Step 12: Connect Database to osTicket using HeidiSQL</b>

- Navigate to the osTicket-Installation-Files folder.
- Locate the HeidiSQL installer and install the application.

![image](https://github.com/user-attachments/assets/0686e865-d74e-4044-a906-853f0d49b4fb)

- Open HeidiSQL and create a new connection:
- Launch the application.
- Click New Session.
- Enter the following credentials:
- Username: root
- Password: root
- Click Open to connect.

![image](https://github.com/user-attachments/assets/855a7f31-afbd-4cce-bb14-6d98cb07dbff)

Next we will create the osTicket database:

- Once connected, right-click on the server name in the left panel.
- Select Create New > Database.
- Name the database: osTicket.
- Save and close HeidiSQL.

![image](https://github.com/user-attachments/assets/1cc7d169-d8ba-484a-8555-f809bab6be0c)


<b>Step 13: Finalize osTicket Setup </b>

This step completes the installation process by linking osTicket to the database you just created and setting up initial system credentials.

![image](https://github.com/user-attachments/assets/cf87a908-4f4c-4a12-b2f5-97d5c13eff12)


- Go back to the osTicket installation page in your browser.
- Fill in the required fields:
- MySQL Database Name: osTicket
- MySQL Username: root
- MySQL Password: root
- Click Install Now.

![image](https://github.com/user-attachments/assets/201ad406-9eca-4d40-9c11-813e5a357a6b)

osTicket is now installed.

<br />

<br />
