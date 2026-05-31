# Microsoft Entra ID — Role-Based Access Control (RBAC) Implementation

> **Domain:** Identity & Access Management | **Platform:** Microsoft Azure | **Level:** Foundational

---

## Executive Summary

This project documents the end-to-end configuration of Role-Based Access Control (RBAC) within Microsoft Entra ID as part of a structured Azure cloud training program. The exercise involved provisioning user accounts and assigning role permissions scoped to each user's departmental function, demonstrating practical application of the **Principle of Least Privilege (PoLP)** in a cloud identity environment.

---

## Objectives

- Provision and configure user identities within Microsoft Entra ID
- Map role assignments to departmental responsibilities and access requirements
- Validate that each user's permissions are restricted to their designated scope
- Demonstrate adherence to the Principle of Least Privilege as a core IAM security control

---

## Environment & Technologies

| Component | Description |
|---|---|
| **Microsoft Azure** | Cloud hosting and administration platform |
| **Microsoft Entra ID** | Cloud-based Identity & Access Management (IAM) service |
| **Azure RBAC** | Permission model for controlling access to Azure resources |

---

## Implementation

### Phase 1 — User Provisioning

Three user accounts were created in Microsoft Entra ID, each representing a distinct organizational department:

| User | Department | Scope of Access |
|---|---|---|
| Kay | Security | Security monitoring & reporting |
| Rose | Development | AI agent identity management |
| Rosy | Human Resources | Read-only organizational oversight |

**Screenshot — All Users Created in Microsoft Entra ID:**

![Users Overview](assets/users-overview.png)

---

### Phase 2 — Role Assignment

#### Kay — Security Department

| Field | Detail |
|---|---|
| **Role** | Security Reader |
| **Access Level** | Read-only |
| **Permissions** | View security alerts, reports, and configurations across Microsoft Entra ID and Microsoft 365 |
| **Restriction** | Cannot modify security policies, rules, or configurations |
| **Justification** | Provides the Security team with sufficient visibility to monitor threats without exposing administrative controls |

**Screenshot — Security Reader Role Selection:**

![Kay Security Reader Selection](assets/kay-security-reader-selection.png)

**Screenshot — Security Reader Role Confirmed:**

![Kay Security Reader Assigned](assets/kay-security-reader-assigned.png)

---

#### Rose — Development Department

| Field | Detail |
|---|---|
| **Role** | Agent ID Developer |
| **Access Level** | Scoped |
| **Permissions** | Define and deploy automated AI agent identities within Microsoft Entra ID |
| **Restriction** | No access to HR data, security configurations, or broader administrative functions |
| **Justification** | Scoped precisely to development workflow requirements, preventing privilege creep across unrelated systems |

**Screenshot — Agent ID Developer Role Selection:**

![Rose Agent Developer Selection](assets/rose-agent-developer-selection.png)

**Screenshot — Agent ID Developer Role Confirmed:**

![Rose Agent Developer Assigned](assets/rose-agent-developer-assigned.png)

---

#### Rosy — Human Resources Department

| Field | Detail |
|---|---|
| **Role** | Global Reader |
| **Access Level** | Read-only |
| **Permissions** | View all configurations, users, and settings visible to a Global Administrator across Microsoft 365 services |
| **Restriction** | Cannot create, modify, or delete any resource, user, or configuration |
| **Justification** | Enables HR oversight and auditing capabilities while enforcing a strict no-modification boundary |

**Screenshot — Global Reader Role Selection:**

![Rosy Global Reader Selection](assets/rosy-global-reader-selection.png)

---

## Security Principle: Least Privilege

The **Principle of Least Privilege** is a foundational security control that limits user access rights to only what is explicitly required to perform their designated function. This project operationalizes PoLP across three distinct personas:

| User | Can Do | Cannot Do |
|---|---|---|
| Kay | Monitor and review security data | Modify security policies or settings |
| Rose | Manage AI agent identities | Access HR, security, or admin functions |
| Rosy | View organizational configurations | Make changes to any resource or user |

**Security Impact:**
- Reduces the organizational attack surface by limiting unnecessary access
- Minimizes the blast radius of a compromised account
- Supports auditability and accountability across departments
- Aligns with compliance frameworks including **NIST 800-53**, **ISO 27001**, and **PCI-DSS**

---

## Key Takeaways

- Effective IAM governance begins with aligning role assignments to business function, not convenience
- Microsoft Entra ID's built-in roles provide granular, auditable access control at scale
- Enforcing least privilege at the identity layer is a critical defense-in-depth strategy
- Role-based segmentation reduces lateral movement risk in the event of an account compromise

---

## Skills Demonstrated

`Microsoft Entra ID` `Azure RBAC` `Identity & Access Management (IAM)` `User Provisioning`
`Least Privilege` `Cloud Security` `Access Control` `NIST 800-53` `ISO 27001`

---
