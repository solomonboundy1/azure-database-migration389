# Azure Database Migration Project

## Overview

This project revolves around the migration and establishment of a cloud-based database system on Microsoft Azure. The primary goal was to seamlessly transfer data from a local SQL source to the cloud, focusing on enhancing accessibility, security, and scalability.

## Project Goals

### 1. VM Setup

I setup two virtual machines on Azure, a production one and a testing one called sandbox in order to undertake all the latter goals. I then established a connection to the VM using the RDP protocol

### 2. Cloud Migration

The primary objective was to transition the database from an on-premise setup to Azure, leveraging its capabilities for improved data management and accessibility. This migration aimed to optimize data processing while ensuring data security and scalability in a cloud environment.

I achieved this first by installing

### 3. Security Measures

To fortify the database against unauthorized access and ensure data integrity, Microsoft Entra ID integration was implemented. This integration defined access roles, allowing only authorized personnel to make updates or alterations to the database, significantly enhancing its security posture.

### 4. Automated Backups

To safeguard against potential data loss or corruption, a robust backup strategy was devised. Regular automated backups were scheduled to mitigate risks associated with accidental deletion, corruption, or alterations to critical tables, ensuring data recoverability and system reliability.
Along with automated backups, I had first established a backup of the full database and assigned it to a seperate back up server. I did this to ensure that whether there was an issue with the server or the actual database, the data could still be recovered easily.

### 5. Disaster Recovery Simulation

Simulating a disaster recovery scenario was a critical phase to validate the database restoration process. This exercise aimed to ensure the seamless recovery of data, should any unforeseen issues like data loss or corruption occur, reinforcing the database's reliability. I did this by first corrupting the data with the following SQL queries:

```sql
-- Intentional Deletion
DELETE TOP (100)
FROM HumanResources.EmployeePayHistory;

-- Data Corruption
UPDATE TOP (100) HumanResources.EmployeePayHistory
SET Rate = 1;
```

The first SQL block deletes vital information from the main database, and the second one corruptes the data with false information. This simulated a disaster on the main database, and to ensure that disaster recovery run as expected I then set the backup point to an hour before the point of disaster, and recovered the backup file. I then run a simple SQL query:

```sql
SELECT *
FROM HumanResources.EmployeePayHistory;
```

Which returned the results prior to the backup, ensuring the success of disaster recovery. Now the newly restored database has become my main database.

### 6. Geo-Replication and Failover

Implementing geo-replication and configuring failover procedures were essential steps to ensure data availability in challenging scenarios. <br/> <br/>
Through the Azure portal I navigated to my database via the SQL Database dashboard and created a replica of my database on a new server to host the replica. I set the region of this server to US East. By doing this, if an outtage or unexpected interference happens within my main server in the UK South region, the workload will be swithed from the primary region (UK) to the secondary region (US) and will tailback to the primary region once service has been restored. I did this to provide redundancy and resilience in case of network issues or outages.

## Key Objectives Achieved

- Successfully migrated data to Azure for enhanced accessibility and processing capabilities.
- Implemented Microsoft Entra ID for access control and enhanced database security.
- Automated regular backups to mitigate data loss risks and ensure recoverability.
- Validated the disaster recovery process through simulated scenarios.
- Configured geo-replication and failover for improved data availability and resilience.

## UML

![DB_UML](Azure%20Database%20Migration%20UML.jpeg)
