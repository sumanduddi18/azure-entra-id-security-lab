# Interview Preparation – Microsoft Entra ID Security Lab

## 1. What was implemented in this project?

I implemented a hands-on Microsoft Entra ID security lab covering identity management, access control, application identity, workload identity and identity monitoring.

## 2. Identity Management

### Q: What is Microsoft Entra ID?

Microsoft Entra ID is Microsoft's cloud-based identity and access management service used to authenticate users, applications and workloads and control access to resources.

### Q: Why use Administrative Units?

Administrative Units provide a logical administrative boundary within Microsoft Entra ID. They allow delegated administrators to manage specific users and groups without granting tenant-wide administrative permissions.

### Q: What is the purpose of security groups?

Security groups are used to organize users and control access to applications, resources and permissions through group-based assignment.

---

## 3. Azure RBAC

### Q: What is Azure RBAC?

Azure Role-Based Access Control provides fine-grained authorization to Azure resources by assigning roles to users, groups, service principals or managed identities.

### Q: What is least privilege?

Least privilege means providing only the permissions required to perform a specific task and no additional access.

### Q: What happens if a user receives multiple RBAC roles?

Azure evaluates all applicable role assignments. Effective permissions are based on the combined permissions from the applicable assignments.

---

## 4. Application Identity

### Q: What is an App Registration?

An App Registration represents an application in Microsoft Entra ID and defines how the application authenticates and interacts with Microsoft identity services.

### Q: What is a Service Principal?

A Service Principal is the security identity used by an application to access resources within a tenant.

### Q: What is the difference between App Registration and Service Principal?

The App Registration defines the application identity, while the Service Principal represents that application within a specific tenant and is used for authentication and authorization.

---

## 5. Managed Identity

### Q: What is Managed Identity?

Managed Identity provides an automatically managed identity for Azure resources so applications can authenticate to supported services without storing passwords or secrets in code.

### Q: System-assigned vs User-assigned Managed Identity?

A System-assigned identity is tied to the lifecycle of a single Azure resource.

A User-assigned identity is an independent Azure resource that can be associated with multiple resources.

### Q: What did you implement?

I enabled a System-Assigned Managed Identity on an Azure VM and assigned it the Storage Blob Data Reader role on the storage account.

---

## 6. Identity Monitoring

### Q: What are Sign-in Logs?

Sign-in Logs provide authentication information such as user, application, IP address, authentication result and other sign-in details.

### Q: What are Audit Logs?

Audit Logs record changes performed within Microsoft Entra ID, such as user, group, application and directory changes.

### Q: What are Service Principal Sign-in Logs?

They provide visibility into authentication activity performed by applications or service principals.

### Q: How would you investigate a suspicious sign-in?

I would review:

1. User and application
2. Sign-in status
3. Source IP address
4. Geographic location
5. Device information
6. Authentication details
7. Conditional Access result
8. Related sign-in and audit events

---

## 7. Production Scenario

### Scenario

A developer reports that an Azure VM cannot access a storage account.

### Troubleshooting Approach

1. Verify that Managed Identity is enabled on the VM.
2. Confirm the correct identity/object ID.
3. Check RBAC assignments on the storage account.
4. Verify the assigned role.
5. Confirm the role scope.
6. Check sign-in or identity activity logs.
7. Validate whether access is being denied by another security control.
8. Remove unnecessary permissions after resolving the issue.

### Expected Resolution

The VM's Managed Identity should have the required data-plane role, such as **Storage Blob Data Reader**, at the appropriate scope.

---

## 8. Key Interview Takeaways

**Identity → Authentication → Authorization → Least Privilege → Application Identity → Managed Identity → Monitoring**

This project demonstrates practical understanding of the complete Azure identity security lifecycle.
