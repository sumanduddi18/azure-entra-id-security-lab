# Microsoft Entra ID Security Lab


## 📌 Project Overview


This project demonstrates a hands-on implementation of Microsoft Entra ID security and Identity & Access Management (IAM) capabilities in Microsoft Azure.


The lab focuses on practical enterprise identity and access scenarios including user and group management, Administrative Units, Azure RBAC, Enterprise Applications, App Registrations, Service Principals, Managed Identities, and identity monitoring.


The objective is to build practical experience with Azure identity security concepts that are commonly used in enterprise Azure Administration, IAM Support, Cloud Security, and Azure Security Engineer roles.


---


## 🎯 Project Objectives


- Manage Microsoft Entra ID users and groups
- Implement Administrative Units
- Review and manage Azure RBAC role assignments
- Configure Enterprise Applications
- Assign users to Enterprise Applications
- Review Single Sign-On configuration
- Create and configure App Registrations
- Understand application identity and authentication
- Configure application client credentials
- Enable System-Assigned Managed Identity
- Assign Azure RBAC permissions to Managed Identity
- Review Service Principal sign-in activity
- Review Managed Identity sign-in activity
- Analyze Microsoft Entra Sign-in Logs
- Analyze Microsoft Entra Audit Logs
- Review Azure Activity Logs
- Apply least-privilege access principles
- Understand identity monitoring and investigation workflows


---


## 🏗️ Lab Architecture


```text
                         Microsoft Entra ID
                                |
        ------------------------------------------------
        |                    |                         |
      Users                Groups              Administrative
                                                  Units
        |                    |                         |
        --------------------|-------------------------
                             |
                      Identity & Access
                             |
        ------------------------------------------------
        |                    |                         |
 Enterprise Applications  App Registrations          RBAC
        |                    |                         |
    DocuSign          IT-Helpdesk-Portal              |
                             |                         |
                       Service Principal               |
                                                       |
                                          -------------------------
                                          |                       |
                                     Azure VM              Storage Account
                                  vm-sec-win-001         stsecuritydefence
                                          |
                                  System-Assigned
                                  Managed Identity
                                          |
                                  Storage Blob Data
                                      Reader
🛠️ Technologies Used
Technology	Purpose
Microsoft Entra ID	Identity and access management
Administrative Units	Delegated administration
Security Groups	Identity organization and access control
Azure RBAC	Authorization to Azure resources
Enterprise Applications	Application access management
App Registrations	Application identity
Service Principals	Application/workload identity
Managed Identity	Passwordless Azure workload authentication
Sign-in Logs	Authentication monitoring
Audit Logs	Identity change monitoring
Azure Activity Logs	Azure resource activity monitoring
🔐 Hands-on Implementations
1. Identity Management

The lab included practical Microsoft Entra ID identity administration.

Activities Performed
Reviewed Microsoft Entra ID users
Reviewed security groups
Created and reviewed Administrative Units
Reviewed assigned Azure roles
Reviewed privileged role assignments
Validated subscription-level access
Administrative Units

The following Administrative Units were configured:

IN-AZAdmin
IN-AzAuditor
IN-Developer

Administrative Units provide a logical boundary that can be used to support delegated administration.

Security Groups

The lab included security groups such as:

SG-Azure-Admins
SG-Auditors
SG-Developers
IT Lab Admin
Documentation

View Identity Management Documentation

2. Application Identity

The lab included application identity and Enterprise Application management.

Enterprise Application

The DocuSign Enterprise Application was reviewed to understand application access management.

A user was assigned to the application to demonstrate controlled application access.

App Registration

The following application was created:

IT-Helpdesk-Portal

The App Registration demonstrated:

Application identity
Application / Client ID
Directory / Tenant ID
Application object
Authentication configuration
Credential management
Single Sign-On

The Enterprise Application configuration was reviewed to understand available SSO options including:

SAML
Password-based
Linked
Disabled
Client Secret

A client secret was configured to demonstrate application authentication using a confidential credential.

Sensitive client-secret values are intentionally excluded from this public repository.

Documentation

View Application Identity Documentation

3. Managed Identity

A System-Assigned Managed Identity was enabled on the Azure Virtual Machine:

vm-sec-win-001

The managed identity was assigned the Azure RBAC role:

Storage Blob Data Reader

at the Storage Account:

stsecuritydefence

Implementation Flow
Azure Virtual Machine
        |
        ↓
System-Assigned Managed Identity
        |
        ↓
Microsoft Entra Identity
        |
        ↓
Azure RBAC
        |
        ↓
Storage Blob Data Reader
        |
        ↓
Storage Account

This demonstrates passwordless workload authentication without storing usernames, passwords, or application secrets on the virtual machine.

Validation

The following were validated:

Managed Identity enabled on VM
Object / Principal ID
Role assignment
Storage Account access
Managed Identity sign-in activity
Documentation

View Managed Identity Documentation

4. Azure RBAC

Azure Role-Based Access Control was reviewed and validated for identity-based authorization.

RBAC Model
Security Principal
        +
Role Definition
        +
Scope
        =
Role Assignment
Security Principals

Azure RBAC can assign permissions to:

Users
Groups
Service Principals
Managed Identities
Role Assignments

The lab reviewed:

Subscription-level role assignments
Privileged roles
Resource-level permissions
Managed Identity permissions
Role inheritance
Managed Identity Example

The System-Assigned Managed Identity of:

vm-sec-win-001

was assigned:

Storage Blob Data Reader

on:

stsecuritydefence

This demonstrates least-privilege access because the workload receives only the permissions required to read Blob data.

Documentation

View RBAC Documentation

5. Identity Monitoring

Identity and resource activity was monitored using Microsoft Entra and Azure logging capabilities.

Sign-in Logs

The lab reviewed:

User sign-ins
Interactive sign-ins
Service Principal sign-ins
Managed Identity sign-ins
Individual sign-in event details

Sign-in event details were reviewed for information such as:

Date and time
Request ID
Correlation ID
User or workload identity
Application
IP address
Location
Authentication result
Conditional Access information
Service Principal Sign-ins

Service Principal authentication activity was reviewed to understand application/workload authentication.

Managed Identity Sign-ins

Managed Identity sign-in activity was reviewed to validate workload authentication.

Audit Logs

Microsoft Entra Audit Logs were reviewed to monitor directory-level administrative changes.

Audit Logs help answer:

"Who changed what and when?"

Azure Activity Logs

Azure Activity Logs were reviewed for Azure resource-level administrative operations.

Examples included:

Role assignment operations
Virtual Machine operations
Virtual Machine extension operations
Resource configuration changes
Policy-related activity
Documentation

View Identity Monitoring Documentation

🔎 Identity Investigation Workflow

A practical identity investigation can follow this workflow:

Authentication Event
        |
        ↓
Microsoft Entra Sign-in Logs
        |
        ↓
Authentication Result
        |
        ↓
IP / Location / Application Analysis
        |
        ↓
Conditional Access Review
        |
        ↓
Microsoft Entra Audit Logs
        |
        ↓
Azure Activity Logs
        |
        ↓
Correlation & Investigation
        |
        ↓
Remediation
🛡️ Security Principles Demonstrated
Least Privilege

Access should be granted according to the minimum permissions required to perform a task.

For example:

Storage Blob Data Reader

is preferred over:

Owner

when a workload only needs to read Blob data.

Identity-Based Access

Users, groups, applications, service principals, and managed identities can act as security principals.

Passwordless Workload Authentication

Managed Identity allows supported Azure resources to authenticate without storing credentials in application code or configuration.

Centralized Identity Monitoring

Sign-in Logs, Audit Logs, and Azure Activity Logs provide visibility into identity and resource activity.

Privileged Access Management

Production environments should protect privileged roles using controls such as:

Microsoft Entra Privileged Identity Management
Just-In-Time activation
MFA
Approval workflows
Access Reviews
Audit logging
📊 Monitoring Sources
Log Source	Primary Purpose
Microsoft Entra Sign-in Logs	Authentication activity
Service Principal Sign-in Logs	Application authentication
Managed Identity Sign-in Logs	Workload authentication
Microsoft Entra Audit Logs	Directory and identity changes
Azure Activity Logs	Azure resource administrative activity
Quick Interview Reference

Sign-in Logs

Who attempted to authenticate, from where, to which application, and what was the authentication result?

Audit Logs

Who changed something in Microsoft Entra ID, what changed, and when?

Azure Activity Logs

Who performed an administrative operation against an Azure resource?

📸 Hands-on Evidence

All implementation screenshots are stored in the Screenshots directory.

The screenshots cover:

Administrative Units
Users
Groups
Assigned Roles
Audit Logs
Sign-in Logs
Enterprise Application
Application User Assignment
Application Creation
SSO Configuration
App Registration
App Registration Overview
System-Assigned Managed Identity
Managed Identity Configuration
Managed Identity Role Assignment
Managed Identity Sign-in Logs
Service Principal Sign-in Logs
Sign-in Log Details
Storage Account Activity Logs
Virtual Machine Activity Logs
📂 Repository Structure
azure-entra-id-security-lab/
│
├── docs/
│   └── Project-Overview.md
│
├── Implementation/
│   ├── Identity-Management.md
│   ├── Application-Identity.md
│   ├── Managed-Identity.md
│   ├── RBAC.md
│   └── Identity-Monitoring.md
│
├── Screenshots/
│   ├── 01-Administrative-Units.jpg
│   ├── 02-Assigned-Roles-Overview.jpg
│   ├── 03-Assigned-Roles.jpg
│   ├── 04-Groups.jpg
│   ├── 05-Users.jpg
│   ├── 06-Audit-Logs.jpg
│   ├── 07-Sign-In-Logs.jpg
│   ├── 08-App-Property-Overview.jpg
│   ├── 09-App-User-Assignment.jpg
│   ├── 10-Application-Created.jpg
│   ├── 11-SSO-Overview.jpg
│   ├── 12-App-Registration.jpg
│   ├── 13-App-Registration-Overview.jpg
│   ├── 14-Enable-System-Assigned-Identity.jpg
│   ├── 15-Managed-Identity-Enabled.jpg
│   ├── 16-Managed-Identity-Role-Assignment.jpg
│   ├── 17-Client-Secret.jpg
│   ├── 18-Managed-Identity-Sign-In-Logs.jpg
│   ├── 19-Service-Principal-Sign-In-Logs.jpg
│   ├── 20-Sign-In-Log-Details.jpg
│   ├── 21-Storage-Account-Activity-Logs.jpg
│   └── 22-VM-Activity-Logs.jpg
│
├── LICENSE
└── README.md
💼 Enterprise Use Cases
IAM Administration

Managing users, groups, Administrative Units, and access permissions.

Application Access Management

Controlling which users and groups can access enterprise applications.

Workload Identity

Allowing Azure workloads to authenticate to supported services without storing credentials.

Access Governance

Applying Azure RBAC and least-privilege principles to Azure resources.

Identity Monitoring

Investigating authentication and administrative activity using centralized identity and resource logs.

Security Operations

Using identity telemetry to investigate suspicious authentication, privilege changes, application activity, and workload authentication.

🎓 Skills Demonstrated
Microsoft Entra ID
Identity and Access Management
Azure RBAC
Administrative Units
User and Group Management
Enterprise Applications
App Registrations
Service Principals
Managed Identities
Single Sign-On
Application Authentication
Client Credentials
Sign-in Logs
Audit Logs
Azure Activity Logs
Least Privilege
Identity Monitoring
Cloud Security
🔐 Security Considerations

No passwords, tokens, private keys, or active credentials should be committed to this repository.

Client-secret values and other sensitive authentication material are intentionally excluded from the public repository.

For production environments:

Store secrets in Azure Key Vault
Rotate application credentials regularly
Apply least-privilege RBAC
Use Managed Identity wherever supported
Protect privileged roles with PIM
Enable MFA and Conditional Access where licensing permits
Monitor identity activity
Review privileged access regularly
📚 Documentation
Project Overview
Identity Management
Application Identity
Managed Identity
Azure RBAC
Identity Monitoring
Hands-on Screenshots
📌 Project Status

Completed

Hands-on implementation, validation, documentation, and evidence collection completed.

This project demonstrates practical Microsoft Entra ID security and IAM capabilities relevant to Azure Administrator, Azure IAM, Cloud Security, and Azure Security Engineer roles.
