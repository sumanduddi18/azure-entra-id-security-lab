# Microsoft Entra ID Security Lab

![Azure](https://img.shields.io/badge/Microsoft-Azure-0078D4?logo=microsoftazure&logoColor=white)
![Entra ID](https://img.shields.io/badge/Microsoft-Entra%20ID-5E5E5E?logo=microsoft)
![IAM](https://img.shields.io/badge/Focus-IAM%20%7C%20RBAC%20%7C%20Identity%20Security-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)

A hands-on Microsoft Entra ID security and Identity & Access Management (IAM) lab focused on enterprise identity administration, application identity, Azure RBAC, managed identities, and identity monitoring.

---

## 📌 Project Overview

This project demonstrates practical implementation of Microsoft Entra ID and Azure identity security capabilities using the Azure Portal.

The lab was designed around common enterprise IAM and Azure Security Engineer scenarios, including:

- User and group administration
- Administrative Units
- Azure RBAC
- Enterprise Applications
- App Registrations
- Application credentials
- Managed Identities
- Service Principals
- Sign-in monitoring
- Audit logging
- Azure Activity Logs

---

## 🎯 Objectives

- Implement Microsoft Entra ID identity management
- Organize users and groups using Administrative Units
- Review and manage Azure RBAC assignments
- Configure Enterprise Application access
- Register applications in Microsoft Entra ID
- Understand application authentication using client credentials
- Configure System-Assigned Managed Identity
- Assign Azure RBAC permissions to a managed identity
- Monitor user, service principal, and managed identity sign-ins
- Investigate Microsoft Entra Audit Logs
- Review Azure Activity Logs for resource-level changes
- Apply least-privilege access principles

---

## 🏗️ Lab Architecture

```text
                         Microsoft Entra ID
                                │
              ┌─────────────────┼─────────────────┐
              │                 │                 │
            Users             Groups       Administrative Units
              │                 │                 │
              └─────────────────┼─────────────────┘
                                │
                         Identity & Access
                                │
              ┌─────────────────┼─────────────────┐
              │                 │                 │
        Enterprise Apps    App Registrations    RBAC
              │                 │                 │
          DocuSign        IT-Helpdesk-Portal      │
                                                  │
                                      ┌───────────┴───────────┐
                                      │                       │
                               Virtual Machine          Storage Account
                               vm-sec-win-001           stsecuritydefence
                                      │                       │
                                      └──── Managed Identity ──┘


-----
🛠️ Technologies Used
| Technology              | Purpose                              |
| ----------------------- | ------------------------------------ |
| Microsoft Entra ID      | Identity and access management       |
| Azure RBAC              | Authorization and resource access    |
| Administrative Units    | Delegated administration             |
| Security Groups         | Identity organization                |
| Enterprise Applications | Application access management        |
| App Registrations       | Application identity                 |
| Client Secrets          | Application authentication           |
| Managed Identity        | Passwordless workload authentication |
| Sign-in Logs            | Authentication monitoring            |
| Audit Logs              | Identity change monitoring           |
| Azure Activity Logs     | Azure resource activity monitoring   |

-------
📂 Project Structure
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
│   ├── 18-Managed-Identity-Sign-In-Logs.jpg
│   ├── 19-Service-Principal-Sign-In-Logs.jpg
│   ├── 20-Sign-In-Log-Details.jpg
│   ├── 21-Storage-Account-Activity-Logs.jpg
│   └── 22-VM-Activity-Logs.jpg
│
├── LICENSE
└── README.md
------
🔐 Key Implementations
1. Identity Management

Implemented and reviewed:

Microsoft Entra ID users
Security groups
Administrative Units
Privileged role assignments
Subscription-level RBAC

View Identity Management →

2. Application Identity

Implemented:

Enterprise Application review
User assignment to application
App Registration
Application identity
Client secret configuration
SSO configuration review

View Application Identity →

3. Managed Identity

Configured a System-Assigned Managed Identity for:

vm-sec-win-001

The managed identity was granted:

Storage Blob Data Reader

on:

stsecuritydefence

This demonstrates passwordless workload authentication using Microsoft Entra ID and Azure RBAC.

View Managed Identity Implementation →

4. Azure RBAC

Reviewed and validated:

Subscription-level role assignments
Privileged roles
Resource-level permissions
Managed identity permissions
Role inheritance
Least-privilege access

View RBAC Implementation →

5. Identity Monitoring

Reviewed:

Interactive user sign-ins
Service principal sign-ins
Managed identity sign-ins
Microsoft Entra Audit Logs
Azure Activity Logs
Individual sign-in event details

View Identity Monitoring →
----
🔎 Monitoring & Investigation

The lab demonstrates a practical identity investigation workflow:
Authentication Event
        ↓
Microsoft Entra Sign-in Logs
        ↓
Authentication / Location / IP Analysis
        ↓
Conditional Access Review
        ↓
Audit Logs
        ↓
Azure Activity Logs
        ↓
Correlation & Investigation
        ↓
Remediation

🛡️ Security Principles Demonstrated
Least Privilege

Permissions are assigned according to the minimum access required.

Identity-Based Access

Users, applications, service principals, and managed identities are treated as security principals.

Passwordless Workload Authentication

Managed Identity eliminates the need to store application credentials for supported Azure workloads.

Centralized Monitoring

Identity and resource activity is monitored through Microsoft Entra and Azure logging capabilities.

Privileged Access Control

Privileged roles require stronger controls such as PIM, MFA, approval workflows, and access reviews in production environments.

📸 Hands-on Evidence

All implementation screenshots are available in the Screenshots directory.

The screenshots demonstrate:

Administrative Units
Users and Groups
RBAC assignments
Enterprise Applications
App Registration
SSO configuration
Managed Identity
Managed Identity RBAC
Service Principal sign-ins
Managed Identity sign-ins
Audit Logs
Azure Activity Logs
💼 Enterprise Use Cases
IAM Administration

Managing users, groups, administrative boundaries, and permissions.

Application Access Management

Controlling which users and groups can access enterprise applications.

Workload Identity

Allowing Azure workloads to authenticate without storing credentials.

Access Governance

Applying RBAC and least-privilege principles to Azure resources.

Identity Monitoring

Investigating authentication and administrative activity through centralized logs.

📚 Documentation
Project Overview
Identity Management
Application Identity
Managed Identity
Azure RBAC
Identity Monitoring
🎓 Skills Demonstrated

Microsoft Entra ID
IAM
Azure RBAC
Administrative Units
Enterprise Applications
App Registrations
Service Principals
Managed Identity
Identity Monitoring
Audit Logs
Sign-in Logs
Azure Activity Logs
Least Privilege

⚠️ Security Note

No passwords, tokens, private keys, or active credentials should be committed to this repository.

Client-secret values and other sensitive authentication material are intentionally excluded from the public repository.

📌 Project Status

Completed

Hands-on implementation, validation, documentation, and evidence collection completed.
