# azure-database-migration389

## Azure Data Migration Project

# Overview

This project involves migrating and setting up a production environment using Azure SQL. It encompasses steps to configure a Windows Virtual Machine (VM), installation of SQL Server, and restoring the AdventureWorks database.

## Setup and Configuration

**1. Setting Up Windows Virtual Machine**
VM Details:
OS: Windows 11
Name: production-vm
Resource Group: my-vm-rg

**2. Remote Connection to VM**
Remote Desktop Connection:
Establish a secure connection using RDP protocol.
Use Microsoft Remote Desktop for access.

**3. Installation of SQL Server and SSMS**
SQL Server and SSMS:
Installed on the VM to facilitate database management.

**4. Database Restoration**
AdventureWorks Database:
Restored from Backup File:
[AdventureWorks Database Backup File](https://aicore-portal-public-prod-307050600709.s3.eu-west-1.amazonaws.com/project-files/93dd5a0c-212d-48eb-ad51-df521a9b4e9c/AdventureWorks2022.bak)
Contains a comprehensive sample database for a fictional manufacturing company.

## Usage Instructions

**Accessing the Production Environment:**

Use Remote Desktop to connect to the production-vm.
Database Management:

Utilize SQL Server Management Studio (SSMS) for database operations.
Resources

Note
Ensure proper firewall rules and network settings are configured for secure connectivity.
