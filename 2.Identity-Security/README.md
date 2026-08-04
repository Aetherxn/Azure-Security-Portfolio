# Securing Azure Identity with RBAC

### Objective

Implement identity and access management controls in Azure using Microsoft Entra ID groups and Azure Role-Based Access Control (RBAC) to enforce least privilege access, improve administrative separation, and reduce the risk of unauthorised privilege escalation.

---

## RBAC Architecture Diagram

![RBAC architecture](screenshots/rbac-architecture-diagram.png)

---

## Implementation (Security Controls)

- Create role-aligned Microsoft Entra ID groups to enforce administrative separation and reduce excessive privilege exposure.
- Implement group-based RBAC instead of direct user role assignments to simplify identity governance and improve access management scalability.
- Assign the Virtual Machine Contributor role to the Service Desk group to provide VM management capabilities without broader administrative permissions.
- Use Azure Portal, PowerShell, and Azure CLI workflows to demonstrate operational flexibility across multiple administration interfaces.

![Group Configuration](screenshots/group-config.png)

![PowerShell Administration](screenshots/powershell-admin.png)

![PowerShell Administration2](screenshots/powershell-admin2.png)

![Azure CLI Administration](screenshots/azure-cli.png)

![Azure CLI Administration2](screenshots/azure-cli2.png)

![RBAC Assignment](screenshots/rbac-assignment.png)

![RBAC Assignment2](screenshots/rbac-assignment2.png)

---

## Architecture Decisions

- Use security groups as the main RBAC boundary to keep things scalable, easier to audit, and simpler to manage over time.
- Split administrative roles into separate groups to support Zero Trust principles and limit the risk of lateral movement.
- Assign the Virtual Machine Contributor role to keep permissions at least-privilege while still allowing day-to-day support tasks.
- Avoid assigning roles directly to users to reduce long-term maintenance overhead and prevent permission drift.

---

## Validation

- Verify group membership inheritance through Azure RBAC assignments.
- Confirm Service Desk users can manage virtual machines without elevated subscription-level permissions.
- Review effective permissions to validate least privilege enforcement and administrative segmentation.

---

## Key Learnings

- Group-based RBAC provides a more scalable and secure access control model than direct user role assignments.
- Administrative segmentation reduces identity attack surface and limits privilege escalation opportunities.
- Azure Powershell and Azure CLI support repeatable and automatable identity management workflows.
- Least privilege enforcement is more effective when permissions align to operational responsibilties rather than individual users. 
