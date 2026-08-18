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
