# Microsoft Entra ID Security

## Overview

This section explores Microsoft Entra ID as a core component of identity and access security in Azure.

The focus is on understanding how identities are managed, how access is controlled, and how Microsoft Entra security capabilities support Zero Trust and identity protection.

---

## Identity & Access Management

Microsoft Entra ID provides the identity layer used to authenticate users, manage identities, and control access to cloud resources.

The practical exercise focused on managing users and security groups within a delegated **User Administrator** role.

### Practical Scenario — Users & Groups

The scenario involved managing identities for a simulated organisation.

The following activities were explored:

- Creating and managing Microsoft Entra ID users
- Creating security groups
- Managing group membership
- Assigning and removing group ownership
- Reviewing directory role assignment permissions
- Resetting user credentials
- Reviewing user sign-in activity
- Disabling compromised or suspicious accounts
- Restoring deleted users
- Cleaning up test identities and groups

The exercise demonstrated how identity lifecycle management and administrative permissions affect an organisation's security posture.

---

## Security Concepts Explored

The wider Microsoft Entra learning path was used to understand the role of several identity-security controls:

### Zero Trust

Identity is treated as a security boundary rather than assuming users or devices are trusted by default.

Key concepts include:

- Multi-factor authentication (MFA)
- Conditional Access
- Risk-based access decisions
- Continuous verification

### Identity Protection

Microsoft Entra ID can identify potentially risky users and sign-in activity.

Key concepts include:

- Risky sign-ins
- Risky users
- Identity-based threat detection
- Automated risk remediation

### Identity Governance

Governance controls help organisations manage access throughout the identity lifecycle.

Key concepts include:

- Privileged Identity Management (PIM)
- Just-in-time privileged access
- Access reviews
- Controlling and reviewing elevated permissions

---

## Security Perspective

The practical work and supporting concepts demonstrate how Microsoft Entra ID can be used to:

- Manage identities centrally
- Control access through groups and roles
- Reduce excessive privileges
- Detect potentially risky authentication activity
- Protect privileged identities
- Apply Zero Trust principles
- Govern access throughout the identity lifecycle

The practical implementation is intentionally focused on the core identity-management layer, while the supporting concepts provide context for how Entra ID fits into a broader cloud identity-security strategy.