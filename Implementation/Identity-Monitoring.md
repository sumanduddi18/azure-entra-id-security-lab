# Identity Monitoring

## Objective

Monitor Microsoft Entra ID authentication and administrative activities using Sign-in Logs, Audit Logs, and Azure Activity Logs.

## Sign-in Logs

Microsoft Entra Sign-in Logs were reviewed to monitor authentication activity.

The lab reviewed:

- Interactive user sign-ins
- Non-interactive user sign-ins
- Service principal sign-ins
- Managed identity sign-ins

Successful sign-in activity was observed for the configured identities.

## Sign-in Investigation

Individual sign-in events were opened to review detailed information such as:

- Date and time
- Request ID
- Correlation ID
- User principal
- Application
- IP address
- Location
- Authentication requirement
- Authentication result
- Conditional Access information

This provides the information required to investigate authentication issues and suspicious sign-in activity.

## Service Principal Sign-ins

Service principal sign-in activity was reviewed for:

`IT-Helpdesk-Portal`

A successful service principal sign-in event was observed.

Service principal sign-in logs are useful for monitoring application identities and detecting unexpected application authentication.

## Managed Identity Sign-ins

Managed identity sign-ins were reviewed to validate workload authentication.

Successful activity was observed for Azure-managed identities including identities associated with Azure security services and the configured workload.

This provides visibility into workload-to-resource authentication without relying on user credentials.

## Audit Logs

Microsoft Entra Audit Logs were reviewed to monitor directory-level changes.

Examples of activities visible in the audit logs include:

- User updates
- Group management
- Authentication-related operations
- Directory changes
- Application-related operations

Audit Logs are particularly useful for determining **who changed what and when**.

## Azure Activity Logs

Azure Activity Logs were reviewed for resource-level administrative activity.

For example, the Storage Account activity log showed a successful:

`Create role assignment`

operation.

The Virtual Machine Activity Log also showed resource operations such as:

- Start Virtual Machine
- Create or Update Virtual Machine Extension
- Health Event Updated
- Policy-related activity

## Monitoring Investigation Flow

A practical identity investigation can follow this sequence:

1. Identify the affected user, application, or workload.
2. Review Sign-in Logs.
3. Check authentication result and failure reason.
4. Review IP address and location.
5. Review Conditional Access information.
6. Check Audit Logs for recent identity changes.
7. Check Azure Activity Logs for resource-level changes.
8. Correlate Request ID or Correlation ID where applicable.
9. Determine whether the activity is expected or suspicious.
10. Apply remediation based on the findings.

## Security Value

Identity monitoring helps detect:

- Failed authentication attempts
- Unusual sign-in locations
- Unexpected application authentication
- Unauthorized role assignments
- Suspicious administrative changes
- Unexpected managed identity activity
- Privilege escalation

## Key Interview Point

**Sign-in Logs answer:**  
"Who attempted to authenticate, from where, to which application, and was authentication successful?"

**Audit Logs answer:**  
"Who changed something in Microsoft Entra ID, what was changed, and when?"

**Azure Activity Logs answer:**  
"Who performed an administrative operation against an Azure resource?"
