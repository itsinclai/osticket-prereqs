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

- Webserver to be installed and configured (IIS)
- Database to be installed and configured (mySQL)

<h2>Installation Steps</h2>

<b>Step 1: Enable IIS and CGI on Your VM</b>

- Open Control Panel > Programs > Programs and Features.
- Click Turn Windows Features On or Off.
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

Next download and install the Microsoft Visual C++ Redistributable package that matches your system architecture.

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
