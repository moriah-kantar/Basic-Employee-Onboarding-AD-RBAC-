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

## 2. Problem Statement

Northstar Medical Group lacked a standardized employee
onboarding and access provisioning process, resulting
in inconsistent identity configurations within its
Active Directory environment.

These inconsistencies introduced operational disruptions,
potential unauthorized access, and identity-related
compliance risks.

An investigation was required to identify and remediate
the affected user's configuration while ensuring alignment
with the organization's role-based access control
(RBAC) structure.

---

## 3. Issue Reported

Jane Cooper was unable to access HR shared resources
required to perform her assigned job responsibilities.

Additionally, her desktop policies and mapped drives
were inconsistent with those of her HR teammates.

The user was able to authenticate successfully, and
restarting her workstation did not resolve the issue.

---

## 4. Investigation

Since the affected user could successfully authenticate,
the investigation focused on identity configuration
rather than credential-related issues.

Using Active Directory Users and Computers (ADUC),
the user's organizational unit placement and security
group memberships were reviewed.

### Investigation Findings

| Configuration | Observed State | Expected State |
|---|---|---|
| Organizational Unit (OU) | Operations | HR |
| Security Group | Operations-Users | HR-Users |
| Authentication | Successful | Successful |

The identified discrepancies were documented before
any corrective actions were performed.

---

## 5. Root Cause Analysis

The incident originated from incorrect identity
provisioning during the employee onboarding process.

### Incorrect Organizational Unit Placement

The incorrect OU placement resulted in the user's
account being associated with an inappropriate scope
for departmental Group Policies.

### Incorrect Security Group Assignment

The user's security group assignment did not align
with her designated job responsibilities or intended
resource access requirements.

These were independent configuration issues requiring
separate corrective actions.

---

## 6. Remediation

The following corrective actions were performed using
Active Directory Users and Computers (ADUC):

1. Moved Jane Cooper's account from the Operations OU
   to the HR OU.
2. Corrected the user's security group assignment
   to HR-Users.
3. Reviewed the updated account configuration.
4. Captured screenshots to document the corrective actions.

---

## 7. Verification

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

## 8. Security and Business Impact

The corrected configuration supports the following
security and operational objectives:

- Reduced risk of inappropriate resource access.
- Alignment with the principle of least privilege.
- Improved departmental access consistency.
- Reduced employee onboarding disruptions.
- Improved administrative visibility and accountability.
- Reduced identity-related compliance risks.

---

## 9. Preventive Recommendations

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

## 10. Supporting Evidence

Supporting screenshots and configuration documentation
are available within the project repository.

- [Screenshot Evidence](../Screenshots/)
- [Project Documentation](../Documentation/)
- [Project Overview](../README.md)

---

## 11. Incident Conclusion

The affected user's Active Directory configuration
was successfully remediated and verified against
the organization's departmental RBAC structure.

This investigation demonstrated the importance of
systematic troubleshooting, accurate identity provisioning,
and post-remediation verification.

The incident also highlighted opportunities to improve
employee onboarding procedures through standardization,
automation, and preventative access reviews.

---

*This incident was completed within a simulated
enterprise environment for professional development
and cybersecurity portfolio purposes.*
