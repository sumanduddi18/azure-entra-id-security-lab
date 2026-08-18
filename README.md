# Microsoft Entra ID Security Lab

## 📌 Project Overview

This project demonstrates a hands-on implementation of Microsoft Entra ID security and Identity & Access Management (IAM) capabilities in Microsoft Azure.

The lab focuses on practical enterprise identity and access scenarios including user and group management, Administrative Units, Azure RBAC, Enterprise Applications, App Registrations, Service Principals, Managed Identities, and identity monitoring.

The objective is to build practical experience with Azure identity security concepts commonly used in enterprise Azure Administration, IAM Support, Cloud Security, and Azure Security Engineer roles.

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

![Microsoft Entra ID Security Lab Architecture](Screenshots/00-Architecture-Diagram.png)

The architecture demonstrates the relationship between Microsoft Entra ID identities, applications, Azure RBAC, Azure resources, managed identities, and monitoring capabilities.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Microsoft Entra ID | Identity and access management |
| Administrative Units | Delegated administration |
| Security Groups | Identity organization and access control |
| Azure RBAC | Authorization to Azure resources |
| Enterprise Applications | Application access management |
| App Registrations | Application identity |
| Service Principals | Application and workload identity |
| Managed Identity | Passwordless Azure workload authentication |
| Sign-in Logs | Authentication monitoring |
| Audit Logs | Identity change monitoring |
| Azure Activity Logs | Azure resource activity monitoring |

---

# 🔐 Hands-on Implementations

## 1. Identity Management

The lab included practical Microsoft Entra ID identity administration.

### Activities Performed

- Reviewed Microsoft Entra ID users
- Reviewed security groups
- Created and reviewed Administrative Units
- Reviewed assigned Azure roles
- Reviewed privileged role assignments
- Validated subscription-level access

### Administrative Units

The following Administrative Units were configured:

- IN-AZAdmin
- IN-AzAuditor
- IN-Developer

Administrative Units provide a logical boundary that can be used to support delegated administration.

### Security Groups

The lab included security groups such as:

- SG-Azure-Admins
- SG-Auditors
- SG-Developers
- IT Lab Admin

### Documentation

[View Identity Management Documentation](Implementation/Identity-Management.md)

---

## 2. Application Identity

The lab included application identity and Enterprise Application management.

### Enterprise Application

The DocuSign Enterprise Application was reviewed to understand application access management.

A user was assigned to the application to demonstrate controlled application access.

### App Registration

The following application was created:

**IT-Helpdesk-Portal**

The App Registration demonstrated:

- Application identity
- Application / Client ID
- Directory / Tenant ID
- Application object
- Authentication configuration
- Credential management

### Single Sign-On

The Enterprise Application configuration was reviewed to understand available SSO options including:

- SAML
- Password-based
- Linked
- Disabled

### Client Secret

A client secret was configured to demonstrate application authentication using a confidential credential.

Sensitive client-secret values are intentionally excluded from this public repository.

### Documentation

[View Application Identity Documentation](Implementation/Application-Identity.md)

---

## 3. Managed Identity

A System-Assigned Managed Identity was enabled on the Azure Virtual Machine:

**vm-sec-win-001**

The managed identity was assigned the Azure RBAC role:

**Storage Blob Data Reader**

at the Storage Account:

**stsecuritydefence**

### Implementation Flow

```text
Azure Virtual Machine
        |
        ↓
System-Assigned Managed Identity
        |
        ↓
Microsoft Entra ID
        |
        ↓
Azure RBAC
        |
        ↓
Storage Blob Data Reader
        |
        ↓
Storage Account
