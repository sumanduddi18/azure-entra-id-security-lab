# 02 — Application Identity

## Objective

Implement application identity and access management using Microsoft Entra ID.

## Hands-on Activities

- Reviewed an Enterprise Application
- Assigned a user to the application
- Reviewed application properties
- Reviewed available SSO methods
- Created an App Registration
- Reviewed Application ID and Tenant ID
- Configured a client secret

## Enterprise Application

The DocuSign Enterprise Application was reviewed to understand application access management.

A user was assigned to the application to demonstrate controlled application access.

## App Registration

Created:

`IT-Helpdesk-Portal`

The application registration demonstrated:

- Application identity
- Application/client ID
- Directory/tenant ID
- Application object
- Authentication configuration
- Credential management

## Client Secret

A client secret was configured for the application to demonstrate application authentication using a confidential credential.

> Security Note: Client secret values must never be committed to source control. Only non-sensitive metadata should be documented.

## Single Sign-On

Reviewed the available SSO options including:

- SAML
- Password-based
- Linked
- Disabled

The lab demonstrates how Enterprise Applications can provide centralized application access through Microsoft Entra ID.

## Security Principle

Application credentials should be protected, rotated before expiration, and stored securely. Secrets should never be exposed in GitHub repositories.
