# Incident Resolution Report — NMG-0047

## 1. Incident Information

| Field | Details |
|---|---|
| Ticket Number | NMG-0047 |
| Organization | Northstar Medical Group |
| Reported By | Brian Foster, Operations Manager |
| Affected User | Jane Cooper |
| User Principal Name | jcooper@NMG.com |
| Job Title | HR Payroll Specialist |
| Incident Category | Identity and Access Management (IAM) |
| Date Resolved | November 24, 2026 |
| Status | Directory Configuration Remediated |

---

## 2. Issue Reported

The affected user was unable to access HR shared 
resources required to perform her assigned job 
responsibilities.

Additionally, her desktop policies and mapped drives 
were inconsistent with those of other HR employees.

The user was able to authenticate successfully, and 
restarting her workstation did not resolve the issue.

---

## 3. Investigation

The investigation focused on the affected user's 
Active Directory configuration, specifically her 
organizational unit placement and security group 
membership.

The following discrepancies were identified:

| Configuration | Observed State | Expected State |
|---|---|---|
| Organizational Unit (OU) | Operations | HR |
| Security Group | Operations-Users | HR-Users |
| Department | HR | HR |
| Authentication | Successful | Successful |

The findings indicated that the issue was related 
to identity provisioning and access configuration 
rather than an authentication failure.

---

## 4. Root Cause Analysis

The incident originated from incorrect identity 
provisioning during the employee onboarding process.

Two primary configuration issues were identified:

### Incorrect Organizational Unit Placement

Jane Cooper's account was located in the Operations 
OU rather than the HR OU. This created an incorrect 
scope for applicable departmental Group Policies.

### Incorrect Security Group Assignment

The user's security group membership was inconsistent 
with her assigned department and intended resource 
access requirements.

Both configuration issues required remediation to 
align the user's identity with the organization's 
role-based access control (RBAC) structure.

---

## 5. Remediation

The following corrective actions were performed 
using Active Directory Users and Computers (ADUC):

1. Located Jane Cooper's user account.
2. Reviewed the existing organizational unit placement.
3. Reviewed the user's security group memberships.
4. Moved the user account from the Operations OU 
   to the HR OU.
5. Corrected the user's security group assignment 
   to HR-Users.
6. Reviewed and verified the updated Active Directory 
   configuration.
7. Captured screenshots to document the remediation.

---

## 6. Verification

The following configuration checks were completed 
after remediation:

- [x] Verified the user account was located in the HR OU.
- [x] Verified membership in the HR-Users security group.
- [x] Confirmed alignment with the departmental RBAC model.
- [x] Captured supporting screenshot evidence.
- [x] Documented the investigation and corrective actions.

End-to-end testing of shared resource access and 
Group Policy application would be the next validation 
step in a production environment.

---

## 7. Security and Business Impact

The corrected configuration supports the following 
security and operational objectives:

- Improved identity and access management.
- Reduced risk of inappropriate access assignments.
- Alignment with the principle of least privilege.
- Consistent departmental access configurations.
- Improved employee onboarding procedures.
- Reduced identity-related compliance risks.

---

## 8. Preventive Recommendations

To reduce the likelihood of similar incidents, 
the following preventive measures are recommended:

| Recommendation | Objective |
|---|---|
| Standardized onboarding checklist | Reduce provisioning errors |
| OU placement verification | Ensure correct policy scope |
| Security group validation | Prevent incorrect access assignments |
| Periodic access reviews | Identify unauthorized or unnecessary access |
| PowerShell provisioning automation | Reduce manual configuration errors |
| Formal documentation procedures | Improve accountability and consistency |

---

## 9. Supporting Evidence

Supporting screenshots and configuration documentation 
are available within the project repository.

- [Screenshot Evidence](../Screenshots/)
- [Project Documentation](../Documentation/)
- [Project Overview](../README.md)

---

## 10. Incident Summary

The investigation identified and remediated two 
identity provisioning misconfigurations within the 
Active Directory environment.

Correcting the affected user's organizational unit 
placement and security group membership restored 
alignment with the organization's departmental 
identity management and RBAC structure.

The investigation, remediation, and configuration 
verification were documented to support future 
troubleshooting and improve onboarding procedures.

---

*This incident was completed within a simulated 
enterprise environment for professional development 
and cybersecurity portfolio purposes.*
