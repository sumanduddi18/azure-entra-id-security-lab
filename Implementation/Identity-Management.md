# 01 — Identity Management

## Objective

Implement and validate core Microsoft Entra ID identity management capabilities.

## Hands-on Activities

- Reviewed Microsoft Entra ID users
- Reviewed security groups
- Created and reviewed Administrative Units
- Reviewed Azure RBAC role assignments
- Validated subscription-level access
- Reviewed privileged role assignments

## Administrative Units

Administrative Units were used to logically organize users and support delegated administration.

Configured Administrative Units:

- IN-AZAdmin — Azure Admin
- IN-AzAuditor — Azure Auditor
- IN-Developer — DevOps Department

## Security Groups

The following security groups were configured:

- SG-Azure-Admins
- SG-Auditors
- SG-Developers
- IT Lab Admin

## RBAC

Reviewed Azure RBAC assignments at subscription scope and validated existing privileged assignments.

The lab demonstrates the relationship between:

`Microsoft Entra Identity → Role Assignment → Scope → Resource Access`

## Validation

The configuration was validated through the Azure Portal by reviewing:

- Users
- Groups
- Administrative Units
- Role Assignments
- Privileged administrator roles

## Security Principle

Access should follow the principle of least privilege. Users and administrators should receive only the permissions required for their responsibilities.
