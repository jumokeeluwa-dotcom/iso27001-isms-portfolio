# Northstar Digital Solutions Ltd — Access Control and Identity Management Policy

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-023 |
| Version | 0.2 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (Annex A 5.15, 5.16, 5.17, 5.18, 8.2, 8.3, 8.4, 8.5) |
| Parent policy | [NSD-ISMS-022 Information Security Policy](22-information-security-policy.md) |
| Policy owner | IT Manager |
| Approver | Managing Director |
| Review frequency | Annually, and after material change to systems, risks or requirements |
| Classification | Internal |

---

## 1. Purpose

Access to Northstar's information, applications, systems and infrastructure is limited to authorised people, based on business need and least privilege. Access is removed when the need ends.

## 2. Scope

This policy applies to:

- **people:** employees, contractors, administrators, suppliers and other authorised users;
- **systems:** Microsoft Entra ID, Microsoft 365, Azure subscriptions, the production platform and databases, code repositories, CI/CD pipelines and finance and HR systems;
- **accounts:** user, administrator, service, guest and break-glass accounts.

## 3. Principles

All access follows these principles:

- **Least privilege:** only the permissions the role needs.
- **Need-to-know:** access to information only when the role requires it.
- **Role-based access:** permissions granted through roles, with direct grants only by exception.
- **Individual accountability:** every account is linked to one named person or one named service.
- **Segregation of duties:** incompatible duties held by different people (Annex A 5.3).
- **Authentication matched to risk:** stronger authentication for privileged and Restricted access.

## 4. Identity management

1. Every person has **one unique identity** in Microsoft Entra ID. The HR system is the authoritative source for employees and contractors.
2. **Shared accounts are prohibited.** The only exceptions are approved under section 11, with a named owner and logging.
3. Every **service account** has a named owner and a documented purpose. Managed identities are used wherever the platform supports them.

## 5. Granting access

Access must:

1. be requested through the access request process;
2. be **approved by the asset owner or their deputy** (NSD-ISMS-007), and also by the line manager;
3. be provisioned by IT Operations or the DevOps team, never by the requester;
4. be limited to the permissions the role requires;
5. be recorded, with the request, the approval and the date.

## 6. Authentication

1. **MFA is required for every account,** including service accounts. Where a service account cannot use MFA, a managed identity or Conditional Access restrictions are used instead.
2. **Administrators use phishing-resistant MFA.**
3. **Legacy authentication methods that cannot enforce MFA are blocked.**
4. Passwords, tokens and recovery codes must never be shared, written down or stored outside approved tools.
5. **Application secrets and keys are stored only in Azure Key Vault**, never in code or pipeline variables.

## 7. Privileged access

1. Administrators use a **separate administrative account**, not their everyday account.
2. Privileged roles are granted **just in time** through Entra Privileged Identity Management, with approval and a time limit.
3. There are **no standing Global Administrators** apart from **two break-glass accounts.** These are stored in the privileged access vault, raise an alert when used, need MD approval for each use, are reviewed after every use, and are tested quarterly.
4. Engineers' access to **production customer data** is just in time, approved and time-limited. There is no standing read access.
5. All privileged activity is logged, and administrators cannot delete the logs.

## 8. Access reviews

| Access | Reviewer | Frequency |
| --- | --- | --- |
| Restricted assets (NSD-ISMS-006) | Asset owner | Quarterly |
| Privileged roles and break-glass accounts | IT Manager, checked by the GRC Analyst | Quarterly |
| All other assets | Asset owner | Every six months |
| Guest and supplier accounts | Internal sponsor | Every 90 days, when the account expires |

Each review confirms that every user still needs their access, that the level is right for their role, and that inactive accounts are removed. **Removals are completed within 5 working days** of the review.

## 9. Joiners, movers and leavers

| Event | Requirement |
| --- | --- |
| **Joiner** | Access is approved before it is provisioned, and starts no earlier than the start date |
| **Mover** | Access no longer needed for the new role is removed **within 5 working days** of the move |
| **Leaver** | Accounts are disabled and all sessions, tokens, keys and remote access revoked **by the end of the last working day.** A leaver record in the HR system starts this automatically. Devices are returned before the last day |

Every joiner, mover and leaver action is recorded and kept as evidence.

## 10. Supplier and third-party access

Third-party access requires:

- a documented business reason and an **internal sponsor**;
- approval by the asset owner;
- a guest account with **MFA**, limited to the systems needed;
- **expiry after 90 days**, renewed only by the sponsor;
- monitoring proportionate to the risk;
- removal at contract end, or sooner if no longer needed.

## 11. Exceptions

Exceptions follow the single exceptions process (NSD-ISMS-008 §8):

- requested to the GRC Analyst, with the business reason and compensating controls;
- risk-assessed;
- approved by the asset owner, or by the **MD** for Restricted assets or privileged access;
- limited to 12 months, with an owner and a review date, and recorded in the exceptions log.

## 12. Compliance and measures

Compliance is measured using the effectiveness tests in NSD-ISMS-021:

| Measure | Target | Control |
| --- | --- | --- |
| Accounts covered by MFA or a managed identity | 100% | 8.5 |
| Legacy authentication sign-ins | 0 | 8.5 |
| Leavers disabled by the end of their last working day | 100% | 6.5 |
| Access grants with asset owner approval | 100% | 5.18 |
| Standing Global Administrators, apart from break-glass | 0 | 8.2 |
| Access reviews completed on schedule | 100% | 5.18 |

Breaches of this policy are handled as security incidents.

## 13. Related controls and risks

| Annex A controls | Risks treated (NSD-ISMS-014) | Treatment actions (NSD-ISMS-015) |
| --- | --- | --- |
| 5.15, 5.16, 5.17, 5.18, 8.2, 8.3, 8.4, 8.5 | R-01, R-03, R-06, R-10, R-11, R-12, R-13, R-16 | T-01.1, T-03.1, T-06.1, T-10.1, T-11.1, T-12.1–12.3, T-13.1, T-13.2, T-16.1 |

## 14. Approval

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |
| IT Manager (policy owner) | Prepared | |

## 15. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-019) | First draft |
| 0.2 | Numbered NSD-ISMS-023; 019 is the SoA. Retitled to include identity management. Approver changed to the MD. Vague terms replaced with the commitments already approved elsewhere in the portfolio: MFA for **every** account; phishing-resistant MFA for administrators; legacy authentication blocked; secrets only in Key Vault; just-in-time privileged access; two break-glass accounts only; no standing production data access; leavers disabled by the end of their last working day; movers within 5 working days; review frequencies by classification; 90-day supplier account expiry. Added the identity management section, measures with targets, and links to controls, risks and treatment actions. |

---

*Portfolio note: Draft only. This is not an approved or implemented policy.*
