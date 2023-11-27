# azure-database-migration389

## Azure Data Migration Project

## Overview

This project involves migrating and setting up a production environment using Azure SQL. It encompasses steps to configure a Windows Virtual Machine (VM), installation of SQL Server, and restoring the AdventureWorks database.

# Milestone 2:

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
Download and Install latest versions of SQL Server and SSMS
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

# Milestone 3: Migrate to Azure SQL Database

## Steps for Migration

1. **Set Up Azure SQL Database**

   - Establish an Azure SQL Database, designated as the target for migrating the on-premise database.
   - Configure the associated SQL Server with SQL login authentication.
   - Verify and adjust the SQL Server's firewall settings, including adding your IP address for secure access.

2. **Configure Azure Data Studio**

   - Install and set up Azure Data Studio on your production Windows VM.

3. **Connect to Azure SQL Database**

   - Utilize Azure Data Studio to create a connection to the newly established Azure SQL Database.
   - This connection facilitates schema and data migration between the databases.

4. **Schema Migration with Schema Compare**

   - Integrate the SQL Server Schema Compare extension in Azure Data Studio.
   - Employ this extension to compare and move the schema from the on-premise database to Azure SQL.

5. **Data Migration via SQL Migration Extension**

   - Install and leverage the Azure SQL Migration extension in Azure Data Studio.
   - Facilitate a smooth transfer of data from the on-premise database to Azure SQL Database.

6. **Validation and Integrity Check**
   - Conduct a comprehensive validation to ensure the database migration's success.
   - Examine the migrated database thoroughly, reviewing data, schema, and configurations for a successful migration.

## Usage Instructions

**Accessing the Production Environment:**

Establish a Remote Desktop connection to the production-vm.
For Database Management:

Utilize Azure Data Studio to manage and operate the database.

**Note:**
Ensure proper firewall configurations and network settings for secure connectivity.
