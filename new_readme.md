# Azure Database Migration Project

## Overview

This project revolves around the migration and establishment of a cloud-based database system on Microsoft Azure. The primary goal was to seamlessly transfer data from a local SQL source to the cloud, focusing on enhancing accessibility, security, and scalability.

## Project Goals

### 1. Cloud Migration

The primary objective was to transition the database from an on-premise setup to Azure, leveraging its capabilities for improved data management and accessibility. This migration aimed to optimize data processing while ensuring data security and scalability in a cloud environment.

### 2. Security Measures

To fortify the database against unauthorized access and ensure data integrity, Microsoft Entra ID integration was implemented. This integration defined access roles, allowing only authorized personnel to make updates or alterations to the database, significantly enhancing its security posture.

### 3. Automated Backups

To safeguard against potential data loss or corruption, a robust backup strategy was devised. Regular automated backups were scheduled to mitigate risks associated with accidental deletion, corruption, or alterations to critical tables, ensuring data recoverability and system reliability.

### 4. Disaster Recovery Simulation

Simulating a disaster recovery scenario was a critical phase to validate the database restoration process. This exercise aimed to ensure the seamless recovery of data, should any unforeseen issues like data loss or corruption occur, reinforcing the database's reliability.

### 5. Geo-Replication and Failover

Implementing geo-replication and configuring failover procedures were essential steps to ensure data availability in challenging scenarios. The replication of databases in different geographic regions, along with failover setup, aimed to provide redundancy and resilience in case of network issues or outages.

## Key Objectives Achieved

- Successfully migrated data to Azure for enhanced accessibility and processing capabilities.
- Implemented Microsoft Entra ID for access control and enhanced database security.
- Automated regular backups to mitigate data loss risks and ensure recoverability.
- Validated the disaster recovery process through simulated scenarios.
- Configured geo-replication and failover for improved data availability and resilience.

## UML

![DB_UML](Azure%20Database%20Migration%20UML.jpeg)
