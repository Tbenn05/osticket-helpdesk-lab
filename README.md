# osTicket Help Desk Lab

## Overview

This project documents my experience deploying osTicket in a local Windows lab environment. The goal was to get a help desk ticketing system running and troubleshoot the issues that came up during installation.

## Environment

- Windows virtual machine
- XAMPP
- Apache
- PHP
- MariaDB
- phpMyAdmin
- osTicket

## Setup and Troubleshooting

## 1. Configuring the Web Server

I used XAMPP to run the services needed for osTicket. Apache initially conflicted with IIS because both were using port 80, so I configured Apache to use port 8080.

2. Installing osTicket:

I downloaded and extracted osTicket into the XAMPP web directory and accessed the installer through the local web server.

3. Troubleshooting Installation Errors:

During installation, I encountered HTTP 404 and HTTP 500 errors. I checked the Apache error log at C:\xampp\apache\logs\error.log to investigate the problem.

The log revealed a database authentication error:

Access denied for user 'root'@'localhost' (using password: YES)

I investigated the MariaDB account configuration through phpMyAdmin and updated the database account password to resolve the authentication issue.

4. Successful Installation:

After correcting the database authentication issue, I reran the installer and received the successful installation confirmation. I then accessed the osTicket Staff Control Panel.

Results:

Configured Apache to run on port 8080 alongside IIS.

Created the osTicket database through phpMyAdmin.

Used Apache error logs to identify a database authentication issue.

Successfully installed osTicket and accessed the Staff Control Panel.

Future Improvements:

Document a complete ticket submission and resolution workflow.

Capture screenshots of the working installation and troubleshooting process.

Review post-installation security settings and remove installation files if still present.

Explore agent accounts, departments, and ticket permissions.

Notes:

This is a local learning lab, not a production deployment. Credentials and passwords are intentionally excluded from this documentation.
