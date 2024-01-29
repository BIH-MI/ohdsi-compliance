# Authorization Concept: OHDSI Research Database

- **Responsible Person:** [Name]
- **Author:** [Name]
- **Date:** [DD.MM.YYYY]
- **Version:** [1.0]

## Contents

1. Objectives
2. Overview of Roles and Rights
3. Application Process
4. Deletion, Restriction, or Revocation of Authorizations
5. Password Process and Policies
6. Control of Authorizations
7. References
8. Annex: List of Technical and Domain Administrators
9. Annex: Application for Access to the OHDSI Research Database

## 1 Objectives

This document describes the roles and permissions for the use of the OHDSI Research Database. It defines access rules for individual groups and users to the database. It also describes the processes that concern the implementation of the authorization concept, such as deleting and creating users, and password management. This includes (1) an overview of roles and rights, (2) a description of the processes for applying for access, and (3) further regulations and processes for their implementation.

In the OHDSI Research Database, different types of data are available, for which different departments are responsible:
- *Department 1*: Data type 1, 2, and 3.
- *Department 2*: Data type 3, 4, and 5.

[_Note: The OHDSI Research Database can operate in a multi-tenancy mode, where different datasets can be made accessible to different groups. If this is not the case, the listing of responsible departments can be omitted, and a single group of domain administrators can be named._]

## 2 Overview of Roles and Rights

The following table contains an overview of different rights for the components and groups of people described in the description of the processing activity.

*A = Administrative rights, W = Write permission, R = Read permission*

| Components          | Technical Administrators | Domain Administrators         | Researchers |
|---------------------|--------------------------|-------------------------------|-------------|
| Virtual Machine     | A                        |                               |             |
| Operating System    | A                        |                               |             |
| ETL Tool            | A                        |                               |             |
| PostgreSQL Database | A                        |                               |             |
| Apache SOLR         | A                        |                               |             |
| OpenLDAP            | A                        | A                             |             |
| WebAPI              | A                        | A                             | W/R         |
| ATLAS               | A                        | A                             | W/R         |
| ARES                | A                        | A                             | W/R         |
| RStudio             | A                        | A                             | W/R         |

[_Note: The table must be adapted according to the information in your description of the processing activity._]

## 3 Application Process

To conduct a study using the OHDSI Research Database, researchers first need to obtain the approval of the department responsible for the relevant dataset. Subsequently, the usual conditions for conducting a retrospective study must be met.

The following process has been defined for granting access to the database:

1. The researcher submits an application for the use of the research database to the head of the responsible department (see [1]) using the appropriate form (see annex).
2. The head of the department approves the application.
3. The researcher forwards the approved application to the domain administrators.
4. The administrators grant the researcher access to the database.

[_Note: The OHDSI Research Database can operate in a multi-tenancy mode, where different datasets can be made accessible to different groups. If this is not the case for your installation, the listing of responsible departments can be omitted, and a single group of domain administrators can be named._]

Approval can be granted only up to a defined expiration date, which is limited to a maximum of 6 months but can be extended.

## 4 Deletion, Restriction, or Revocation of Authorizations

At the conclusion of a study, the researcher informs the administrator. The administrator then revokes the respective authorization.

## 5 Password Process and Policies

The administrators assign an initial password for each account. This password must be changed by the researcher at the first use. During the change, users are informed of the organization's password policies.

[_Note: Alternatively, integration of OHDSI into the organization-wide AAI can be considered. See the relevant documentation [2]._]

## 6 Control of Authorizations

In addition to the active deactivation of expired accounts, the domain administrators and technical administrators check the active accounts twice a year and deactivate no longer needed or expired accounts accordingly.

## 7 References

[1] Operational Concept OHDSI Research Database

[2] Security Configuration of OHDSI WebAPI. https://github.com/OHDSI/webapi-wiki/blob/master/Security-Configuration.md

## 8 Annex: List of Technical and Domain Administrators

The following list contains the contact details of all technical and domain administrators:

- *Name and Contact Details 1:* Roles
- *Name and Contact Details 2:* Roles
- *Name and Contact Details 3:* Roles

## 9 Annex: Application for Access to the OHDSI Research Database

### Personal Data
- *First Name:* 
- *Last Name:*
- *Department:*
- *Account:*
- *Email Address:*

## Dataset and Signature 

Hereby, I apply for access to the following dataset of the OHDSI Research Database:

I am aware of the relevant rules and regulations in the fields of research and data protection.  

Date, Signature

## Approval by the Responsible Department

As the head of the responsible department, I hereby approve access to the respective dataset for the named person.

Date, Signature
