# Operational Concept: OHDSI Research Database

- **Responsible Person:** [Name]
- **Author:** [Name]
- **Date:** [DD.MM.YYYY]
- **Version:** [1.0]

## Contents

1. Overview
2. Operational Processes
   * 2.1 Installation
   * 2.2 Updates
   * 2.3 Release Changes
   * 2.4 Starting and Stopping Components
   * 2.5 User and Permission Management
   * 2.6 Backup
   * 2.7 Recovery Plan
   * 2.8 Availability
3. Continuous Improvement
4. References

## 1 Overview

This document describes all processes for the secure operation of the OHDSI Research Database. The database consists of various technical components and application software, which are detailed in the description of the processing activity [1]. Rights and roles are described in the authorization concept [2]. This document includes information on the installation environment, its operation, update processes, and maintenance.

## 2 Operational Processes

### 2.1 Installation

The database has been set up using the OHDSI Broadsea package [3] and *Docker Compose*. The server meets the system requirements described in [3]:

- **Server and operating system specifications, e.g., Ubuntu 22.04.3 LTS**
- **CPU specification, e.g., 8 cores**
- **Other specifications, e.g., 16 GB RAM**

[_Note: Adjust as needed._]

Appropriate certificates have been created and configured to support encrypted connections. Ports that allow unencrypted communication (e.g., HTTP) have been disabled.

[_Note: This text describes an installation using the OHDSI Broadsea package based on Docker. If a native installation is performed, the text should be changed accordingly._]

### 2.2 Updates

The operating system is configured to check for and, if necessary, install security patches every 24 hours. In addition, software updates are done manually as needed. The  status of the software installed on the server is checked manually once a quarter by the technical administrators.

[_Note: Adjust if needed._]

### 2.3 Release Changes

A release change of the OHDSI components and the database is only planned when maintenance expires. The same applies to the operating system. If a release change becomes necessary, the corresponding updates will be manually applied.

[_Note: Adjust if needed._]

### 2.4 Starting and Stopping Components

To start and stop components, Docker Compose must be executed using "docker compose up" or "docker compose down." This enables further operations, such as restarting the operating system.

[_Note: Adjust if needed._]

### 2.5 User and Permission Management

The processes for user and permission management are described in the authorization concept [2].

### 2.6 Backup

An automatic backup of the server is carried out every 24 hours by the central infrastructure. The created backups are retained for 30 days. For the medical data, the source systems have additional backup procedures set up. Therefore, an additional database backup is not necessary. For user accounts and study configurations, a 30-day backup is sufficient. Archiving of data used for research purposes is done separately by the researchers using other services of the organization.

[_Note: Adjust to local circumstances._]

### 2.7 Recovery Plan

In case of an unexpected system failure, the components must first be started with "docker compose up." The start process should be monitored, and log files checked. If errors occur, (1) a restoration of the backup can be considered, or (2) a restart of the ETL process. The former would be the case if the errors relate to user accounts or configuration files, the latter if the errors relate to medical data.

[_Note: Adjust to local circumstances._]

### 2.8 Availability

We aim to ensure that access to the research database is possible at least from Monday to Friday from 08:00 - 20:00. Planned deviations from this availability, for example for maintenance work, will be announced at least one week in advance to all registered users.

[_Note: Adjust to local procedures._]

## 3 Continuous Improvement

The OHDSI Research Database is continuously operated and kept up-to-date. Users and their permissions are documented accordingly in the annexes of the authorization concept. Further information can be found in the operational and information security documents. All documents are kept up-to-date and updated at least once a year.

## 4 References

[1] Processing Activity Description: OHDSI Research Database.

[2] Authorization Concept: OHDSI Research Database.

[3] OHDSI-Broadsea Documentation. https://github.com/OHDSI/Broadsea.
