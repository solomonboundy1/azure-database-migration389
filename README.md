# azure-database-migration389

## Azure Data Migration Project

## Overview

This project involves migrating and setting up a production environment using Azure SQL. It encompasses steps to configure a Windows Virtual Machine (VM), installation of SQL Server, and restoring the AdventureWorks database.

# Milestone 2:

## Setup and Configuration

**1. Setting Up Windows Virtual Machine**

VM Details:

OS: Windows 11 <br/>
Name: production-vm<br>
Resource Group: my-vm-rg

**Creating the VM**

To create the VM:

- From the Azure portal homepage, select the 'Create a resource' button from the top left corner of the dashboard.
- Click on 'Virtual machine' to start the creation process.
- Choose the appropriate subscription and allocate the VM to a specific resource group, e.g., 'my-vm-rg'.
- Select the region geographically closest to you.
- Specify an administrator username and password that will be used to log in to the virtual machine's operating system.
- Ensure Remote Desktop Protocol (RDP) is enabled, allowing access using the administrator credentials.
- Review and create the VM, and download the private key.
  <br>
  <br>

**2. Remote Connection to VM**<br>

Remote Desktop Connection:
Establish a secure connection using RDP protocol.
Use Microsoft Remote Desktop for access.

**Connecting to the VM**

To connect to the VM:

- Navigate to the resource page under the 'Connect' panel for RDP connection and follow the instructions.
- Download the RDP connection file using the 'Download RDP file' button.
- Once downloaded, double-click the RDP file and use the username and password set up earlier.
  <br>
  <br>

**3. Installation of SQL Server and SSMS**<br>

Download and Install latest versions of SQL Server and SSMS

**Installing SSMS**

To install SSMS:

- Download the SQL Server Developer installer from the Microsoft Download Center onto your VM.
- Choose the 'Basic' option during installation.
- After installing SQL Server, proceed to install SQL Server Management Studio (SSMS) on the VM using the 'Install SSMS' button.
- Launch SSMS and connect to the VM via the popup window by clicking the 'Connect' button using the provided credentials.

**4. Database Restoration**
AdventureWorks Database:
Restored from [this](https://aicore-portal-public-prod-307050600709.s3.eu-west-1.amazonaws.com/project-files/93dd5a0c-212d-48eb-ad51-df521a9b4e9c/AdventureWorks2022.bak) Backup File.

Contains a comprehensive sample database for a fictional manufacturing company.

**Restoration process**

To restore the database:

- Download the AdventureWorks2022.bak file locally on your VM.
- Copy the downloaded file to `C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\Backup`.
- In SQL Server Management Studio, right-click on the 'Databases' node in the Object Explorer and choose 'Restore Database...'.
- In the 'Restore Database' window, select the 'Device' option, click the '...' button to select the backup files to restore, choose the full backup, and click 'OK' to start the restoration process.

## Usage Instructions

**Accessing the Production Environment:**

Connect via Remote Desktop to the production-vm.
For Database Management:

Use SQL Server Management Studio (SSMS) to manage and operate the database.

**Note:**
Ensure proper firewall configurations and network settings for secure connectivity.

# Milestone 3:

## Migrate to Azure SQL Database

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

# Milestone 4:

## Data Backup and Restore

1. **Create Full Backup of Production Database**

   - Generate a full backup of the production database hosted on the Windows VM. This serves as a safety net for unforeseen issues.
   - Store the resultant backup file in a designated location on your computer.

2. **Configure Azure Blob Storage Account**

   - Configure an Azure Blob Storage account as a secure online repository for database backups.
   - Upload the previously created database backup file to the Blob Storage container, ensuring an extra layer of backup protection through remote redundancy.

3. **Setup Development Environment**

   - Replicate a controlled and isolated environment, like a sandbox, for controlled experimentation and development.
   - Provision a new Windows VM mirroring the development setup.
   - Install SQL Server on this VM to mirror necessary database infrastructure.
   - Restore the database backup onto this new "sandbox" environment to safely explore new concepts without impacting production data.

4. **Automate Development Database Backups**
   - Utilize SSMS on your development Windows VM to establish a Management Task for automating regular backups.
   - Configure a weekly backup schedule to consistently protect evolving work and simplify recovery if necessary for the development environment.

**Note:** Ensure proper configuration and monitoring of backup processes to maintain data integrity and security.

# Milestone 5:

## Simulation of Data Integrity Loss

1. **Data Integrity Simulation:**
   - Intentionally remove crucial data from the production database to mimic a scenario of compromised data integrity.
   - Create detailed documentation outlining the specifics of this simulated data loss for future reference and recovery testing.
     Find the documentation by clicking [here](data_corruption_process.docx)
   - After the simulation, validate its impact by examining the Azure SQL Database using the established connection in Azure Data Studio.

## Database Restoration and Validation

2. **Database Recovery:**
   - Use Azure SQL Database Backup to restore the production database to a point just before the simulated data loss occurred.
   - Verify the successful restoration by reviewing the restored data through the Azure Data Studio connection.
   - As the prior production database lacks vital data, the restored database becomes the new production database.
   - Post-restoration, delete the database affected by data loss from the Azure portal.

## Usage Instructions

**Accessing the Production Environment:**

Connect via Remote Desktop to the production-vm.
Database Management:

Leverage Azure Data Studio for database operations.

# Milestone 6:

## Implement Geo-Replication and Failover

1. **Setting Up Geo-Replication**

   - Initiate the setup of geo-replication for your production Azure SQL Database. This process involves creating a synchronized replica of your primary database.
   - The replica will be hosted on another SQL server located in a different geographical region than your primary database server.

2. **Simulating Real-world Challenges**
   - Orchestrate a planned failover to the secondary region to transition operations to the secondary copy.
   - Evaluate the availability and data consistency of the failover database during this process.
   - Perform a failback to the primary region.

# Milestone 7:

## Enabling Microsoft Entra ID Authentication

1. **Configure Microsoft Entra ID as Trusted Identity Provider**
   - Navigate to the server and access Microsoft Entra ID in the side pane.
   - Click on "Set Admin" and select the Microsoft account, then save the settings.

### User Account Creation and Access Configuration

2. **Create DB Reader User Account in Microsoft Entra ID**

   - Go to the Entra ID homepage and select "Add" then create a new user.
   - Generate a user named "DB_Reader".

3. **Assign Permissions Using Azure Data Studio**
   - In Azure Data Studio within the 'production-vm', right-click on the 'adworks1' server and choose 'New Query'.
   - Execute the following query to grant the `db_datareader` role to the DB_Reader user:
     ```sql
     CREATE USER [DB_Reader@YourDomain.com] FROM EXTERNAL PROVIDER;
     ALTER ROLE db_datareader ADD MEMBER [DB_Reader@YourDomain.com];
     ```
     **Note:** ensure you replace 'YourDomain' with your domain.

### Validating User Access and Permissions

4. **Testing User Access**
   - Disconnect from the database if signed in with admin account.
   - Sign in using the DB_Reader account. Upon login, change the password if prompted.
   - Run ALTER queries to verify the assigned privileges. Inability to alter tables confirms the privilege setup.

## DB UML

![DB_UML](Azure%20Database%20Migration%20UML.jpeg)
