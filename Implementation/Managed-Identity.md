# Managed Identity

## Objective

Implement and validate a System-Assigned Managed Identity for an Azure Virtual Machine and use Azure RBAC to grant the identity access to an Azure Storage Account.

## Hands-on Implementation

### 1. Enable System-Assigned Managed Identity

Enabled a System-Assigned Managed Identity on:

`vm-sec-win-001`

The VM was registered with Microsoft Entra ID and received a unique Object (principal) ID.

### 2. Validate Managed Identity

Verified the managed identity configuration from:

`Virtual Machine → Security → Identity`

The identity status was confirmed as:

`On`

The Object (principal) ID was also validated.

### 3. Assign Azure RBAC Permission

The VM's managed identity was granted:

`Storage Blob Data Reader`

at the Storage Account scope.

Target Storage Account:

`stsecuritydefence`

This allows the VM identity to access Blob Storage data without requiring a username, password, or application secret.

### 4. Validate Role Assignment

The Storage Account IAM configuration was reviewed and the following assignment was verified:

| Principal | Type | Role | Scope |
|---|---|---|---|
| vm-sec-win-001 | Managed Identity | Storage Blob Data Reader | Storage Account |

### 5. Validate Identity Sign-in Activity

Microsoft Entra Sign-in Logs were reviewed under:

`Sign-in logs → Managed identity sign-ins`

Successful managed identity activity was observed.

This confirms that Azure managed identities can authenticate to Microsoft Entra-protected resources without storing credentials in application code.

## Security Benefits

Managed Identity provides:

- Elimination of stored application credentials
- Microsoft Entra-based authentication
- Integration with Azure RBAC
- Reduced credential exposure
- Easier credential lifecycle management
- Support for least-privilege access

## System-Assigned vs User-Assigned

### System-Assigned

- Created directly on an Azure resource
- Lifecycle is tied to the resource
- Identity is automatically removed when the resource is deleted
- Suitable when the identity is required by only one resource

### User-Assigned

- Created as a separate Azure resource
- Can be assigned to multiple Azure resources
- Lifecycle is independent of the resources using it
- Useful when the same identity must be reused

## Validation Evidence

Relevant screenshots are stored in the `Screenshots` directory:

- Managed Identity enabled on VM
- Managed Identity configuration
- Managed Identity RBAC assignment
- Managed Identity sign-in logs

## Key Interview Point

A managed identity is **not a role**. It provides an identity that Azure resources can use to authenticate. Permissions are then granted to that identity through Azure RBAC.
