# Microsoft Entra ID Security Lab – Project Overview

## 1. Project Summary

This project demonstrates a hands-on implementation of Microsoft Entra ID security and Identity & Access Management (IAM) using Microsoft Azure.

The lab focuses on identity lifecycle management, access control, application identity, workload identity and identity monitoring.

## 2. Objectives

- Manage users, groups and Administrative Units
- Implement Azure RBAC and least-privilege access
- Configure Enterprise Applications
- Configure App Registrations and Service Principals
- Implement System-Assigned Managed Identity
- Monitor authentication and identity activity
- Analyze Sign-in, Audit and Activity Logs

## 3. Architecture

![Microsoft Entra ID Security Lab Architecture](../Screenshots/Lab%20Architecture.png)

## 4. Key Components

| Component | Purpose |
|---|---|
| Microsoft Entra ID | Identity and access management |
| Administrative Units | Delegated identity administration |
| Security Groups | Access and permission management |
| Azure RBAC | Resource-level authorization |
| Enterprise Applications | Application access management |
| App Registration | Application identity |
| Service Principal | Application/workload authentication |
| Managed Identity | Passwordless Azure resource authentication |
| Sign-in Logs | Authentication monitoring |
| Audit Logs | Identity change tracking |
| Activity Logs | Azure resource activity monitoring |

## 5. Hands-on Implementation

### Identity Management
- Created users and security groups
- Created Administrative Units
- Assigned users to appropriate groups and administrative scopes

### Access Control
- Reviewed Azure RBAC role assignments
- Validated privileged and inherited permissions
- Applied least-privilege access concepts

### Application Identity
- Added an Enterprise Application
- Assigned users to the application
- Created an App Registration
- Configured a Service Principal
- Created and reviewed a client secret

### Managed Identity
- Enabled System-Assigned Managed Identity on an Azure VM
- Assigned Storage Blob Data Reader permission
- Validated resource access through managed identity
- Reviewed Managed Identity sign-in activity

### Monitoring
- Reviewed interactive sign-in logs
- Reviewed Service Principal sign-in logs
- Reviewed Managed Identity sign-in logs
- Reviewed Entra ID Audit Logs
- Reviewed Azure Activity Logs

## 6. Security Concepts Demonstrated

- Least Privilege
- Role-Based Access Control
- Delegated Administration
- Application Identity
- Workload Identity
- Passwordless Authentication
- Identity Monitoring
- Privileged Access Management Concepts

## 7. Technologies Used

**Microsoft Azure • Microsoft Entra ID • Azure RBAC • Enterprise Applications • App Registrations • Service Principals • Managed Identity • Azure Activity Logs**

## 8. Project Outcome

Successfully implemented and validated a practical Microsoft Entra ID security environment covering identity management, authorization, application identity, workload identity and monitoring.

## 9. Repository

Detailed implementation steps and hands-on evidence are available in:

- `Implementation/`
- `Screenshots/`
- `README.md`
