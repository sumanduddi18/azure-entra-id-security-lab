# Azure RBAC

## Objective

Implement and validate Azure Role-Based Access Control (RBAC) for identity-based access management.

## Hands-on Implementation

The lab reviewed Azure RBAC assignments at subscription and resource scopes.

The following areas were validated:

- Subscription-level role assignments
- Privileged role assignments
- User role assignments
- Managed identity role assignments
- Resource-level access
- Inherited permissions

## Role Assignment Model

Azure RBAC follows four primary components:

`Security Principal → Role Definition → Scope → Assignment`

### Security Principal

The identity receiving access.

Examples:

- User
- Group
- Service Principal
- Managed Identity

### Role Definition

Defines what actions the principal can perform.

Examples:

- Owner
- Contributor
- Reader
- Storage Blob Data Reader
- User Access Administrator

### Scope

Defines where the permissions apply.

Possible scopes include:

- Management Group
- Subscription
- Resource Group
- Individual Resource

### Role Assignment

Connects the security principal, role definition, and scope.

## Hands-on Examples

### Subscription-Level Access

Subscription IAM was reviewed to identify existing role assignments and privileged access.

The environment showed multiple role assignments, including Owner and User Access Administrator.

### Managed Identity Access

The System-Assigned Managed Identity of:

`vm-sec-win-001`

was assigned:

`Storage Blob Data Reader`

on:

`stsecuritydefence`

This demonstrates resource-level least-privilege access.

## Inheritance

Azure RBAC permissions assigned at a higher scope can be inherited by child resources.

For example:

`Subscription`
↓
`Resource Group`
↓
`Resource`

The effective permissions of a principal should therefore be evaluated across all applicable scopes.

## Least Privilege

The lab demonstrates the importance of assigning the minimum role at the narrowest practical scope.

For example, if a workload only needs to read Blob data, assigning:

`Storage Blob Data Reader`

is preferable to granting:

`Owner`

## Privileged Roles

Privileged roles such as Owner and User Access Administrator require additional security controls because they can significantly affect access to Azure resources.

In an enterprise environment, privileged access should be protected using controls such as:

- Microsoft Entra Privileged Identity Management (PIM)
- Just-in-Time activation
- MFA
- Approval workflows
- Access reviews
- Audit logging

## Validation

RBAC assignments were validated through:

`Azure Portal → Subscription → Access control (IAM) → Role assignments`

and:

`Storage Account → Access Control (IAM) → Role assignments`

## Key Interview Point

Azure RBAC controls **authorization** to Azure resources.

Microsoft Entra ID primarily handles **authentication and identity management**, while Azure RBAC determines what an authenticated identity is authorized to do at a particular Azure scope.
