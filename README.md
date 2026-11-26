# Basic Employee Onboarding (AD)(RBAC)

## Problem Statement

Northstar Medical Group is a fictional healthcare organization whose previous managed service provider (MSP) left its Active Directory environment without a consistent departmental structure. IT provisioned employee accounts manually, with inconsistent naming conventions and security group assignments. This made it harder to verify who had access to sensitive systems and created HIPAA-related risks around inappropriate access to protected health information. The onboarding problem surfaced in ticket NMG-0047 when Jane Cooper, a new HR Payroll Specialist, could sign in but still could not access HR shared resources four days into her first week.

## Solution Overview

I built the NMG.com domain from scratch in VirtualBox by installing Active Directory Domain Services on Windows Server 2022 and promoting the server to a domain controller. I created four top-level organizational units (OUs) for Finance, HR, IT, and Operations, with a matching security group for each department. I used a flat role-based access control (RBAC) model and assigned users directly to their departmental security groups. I standardized account names and attributes, placed users in their departmental OUs, and used security group membership to manage access by role. For ticket NMG-0047, I corrected Jane Cooper’s OU placement by moving her from Operations to HR and added her to the HR-Users security group.

## Video Walkthrough

[Video walkthrough coming soon](#)

## Tools Used

- Windows Server 2022
- Active Directory Domain Services (AD DS)
- Active Directory Users and Computers (ADUC)
- Oracle VirtualBox
- Group Policy
- `dcdiag` for domain controller diagnostics
- Role-based access control (RBAC)
- GitHub

## Project Timeline

- **Day 1 — Domain setup.** Created NMG.com, promoted the Windows Server VM to a domain controller, and ran `dcdiag`.
- **Day 2 — Directory structure.** Created four departmental OUs and their corresponding security groups.
- **Day 3 — User provisioning.** Created 15 test accounts with consistent naming and account attributes across four departments.
- **Day 4 — Incident response (NMG-0047).** Investigated why Jane Cooper could sign in but received “Access Denied” on HR shared resources and saw different desktop policies, mapped drives, and restrictions from her teammates. The original ticket confirmed that her password worked, two restarts had failed to resolve the issue, and other HR employees were unaffected. I corrected her OU placement and added the missing HR-Users membership.
- **Day 5 — Portfolio documentation.** Prepared the README, directory documentation, screenshots, and incident report for GitHub.

## Key Accomplishments

- Built the NMG.com Active Directory domain from scratch in a Windows Server 2022 lab.
- Designed four departmental OUs and implemented a flat RBAC model using matching security groups for 15 test accounts.
- Diagnosed and corrected two onboarding errors in NMG-0047 involving OU placement and departmental security group membership.

## Repository Structure

| Folder | Contents |
| --- | --- |
| `Documentation/` | Domain setup notes, OU and security group design, user provisioning records, and the RBAC mapping. |
| `Screenshots/` | Lab evidence covering domain setup, directory structure, user provisioning, and incident troubleshooting. |
| `Incident-Reports/` | The NMG-0047 resolution report, including the root causes and corrective actions. |
