# Northstar Digital Solutions Ltd — Information Classification and Handling Policy

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-025 |
| Version | 1.0 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (Annex A 5.12, 5.13, 5.14, 5.33, 8.10) |
| Parent policy | [NSD-ISMS-022 Information Security Policy](22-information-security-policy.md) |
| Supporting standard | [NSD-ISMS-008 Information Classification and Handling Standard](../02-asset-management/08-information-classification-scheme.md): definitions, decision steps and the full handling matrix |
| Policy owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually, with NSD-ISMS-008 |
| Classification | Internal |

---

## 1. Purpose

All information at Northstar is classified by how much harm its disclosure would cause, and handled accordingly.

This policy sets the **rules**. The standard NSD-ISMS-008 holds the **detail**. Keeping the detail in one place stops the two documents drifting apart.

## 2. Scope

All information created, received or held by Northstar in any form, including customer data in the platform. It applies to everyone covered by NSD-ISMS-022.

## 3. Policy statements

1. **Four levels.** Information is classified as **Restricted**, **Confidential**, **Internal** or **Public**, as defined in NSD-ISMS-008 §2.
2. **Owners classify.** The asset owner (NSD-ISMS-007) classifies information, using the decision steps in NSD-ISMS-008 §3. The Data Protection lead confirms the classification of personal data.
3. **Defaults.** Unlabelled information is treated as **Internal**. If it contains personal or customer data, it is treated as **Confidential** at minimum.
4. **Customer data.** Data that customers put into the platform is **always Restricted.**
5. **Security reports.** Full vulnerability scan and penetration test reports are **Restricted.** A customer-facing summary with findings removed is Confidential.
6. **Mandatory handling.** Everyone must follow the handling matrix in NSD-ISMS-008 §4 for access, storage, sharing, transmission, AI tools, test environments, removable media, printing, suppliers and disposal. The rules are mandatory. They do not apply only "where appropriate".
7. **Labelling.** Documents and email in Microsoft 365 carry a Microsoft Purview sensitivity label. **The default label is Internal**, and the Restricted label applies encryption automatically. Systems that cannot be labelled record their classification in the asset register (NSD-ISMS-006).
8. **Never to personal or unapproved services.** Restricted and Confidential information must never be sent to personal email, personal or unapproved cloud storage, or unapproved removable media.
9. **Public release** needs approval from the asset owner and the Marketing or Sales lead, after a check for sensitive content.
10. **Retention and disposal.** Information is kept according to the retention schedule agreed with the Data Protection lead. It is then destroyed using the method for its classification. Destruction of Restricted information is recorded (NSD-ISMS-011 §8).
11. **Reclassification.** Anyone may handle information at a higher level straight away. Only the owner may downgrade it, with the Data Protection lead for personal data (NSD-ISMS-008 §7).

## 4. Roles

| Role | Responsibility |
| --- | --- |
| Asset owners | Classify; approve downgrades and external sharing |
| Data Protection lead | Confirms personal data classification; owns the retention schedule |
| IT Manager | Configures Purview labels and DLP |
| GRC Analyst | Maintains the policy and standard; runs quarterly spot checks |
| All users | Apply labels and follow the handling rules |

## 5. Exceptions and compliance

Exceptions follow NSD-ISMS-008 §8: approved by the owner for Confidential information, or by the MD for Restricted, for at most 12 months. Breaches are handled as security incidents.

| Measure | Target |
| --- | --- |
| Correct labels in a sample of 25 documents from Restricted sites (NSD-ISMS-021, 5.12) | 100% |
| Files on the HR site with the Restricted label and encryption (5.13) | 100% |
| Retired Restricted assets with a destruction record | 100% |

## 6. Related controls and risks

Annex A 5.12, 5.13, 5.14, 5.33, 8.10 · Risks R-03, R-19 · Actions T-03.2, T-19.2

## 7. Approval

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

---

*Portfolio note: Draft only. This is not an approved or implemented policy.*
