# Northstar Digital Solutions Ltd — Asset Ownership and Accountability Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-007 |
| Version | 0.1 — Draft for owner acceptance |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (Annex A 5.2, 5.3, 5.9, 5.18) |
| Related documents | [NSD-ISMS-001 Charter](../01-initiation-and-context/01-isms-project-charter.md) · [NSD-ISMS-006 Information Asset Register](06-information-asset-register.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Quarterly for Restricted assets; six-monthly for all others; and on the triggers in section 9 |
| Classification | Internal — Simulated portfolio document |

---

## 1. Purpose

This register records who is accountable for each asset in NSD-ISMS-006, who covers in their absence, and whether they have formally accepted ownership. It also records the segregation-of-duties checks applied to those assignments.

The two registers have different jobs:

- **NSD-ISMS-006** is the master record of the assets themselves: location, classification and security requirements.
- **This register** is the master record of accountability: owners, deputies, custodians, acceptance and ownership changes.

Owner coverage, with acceptance recorded, is the measure for charter objective **Obj 2**.

## 2. Roles

| Role | Accountable or responsible for | Can delegate? |
| --- | --- | --- |
| Asset owner | Classification, acceptable use, access approval, access reviews, retention, accepting residual risk within appetite | Tasks only. Accountability stays with the owner |
| Deputy owner | Acting for the owner during absence or conflict of interest, using the owner's existing decisions | No |
| Custodian | Day-to-day operation, maintenance and technical protection, as the owner requires | Tasks within the custodian team |
| Information Security / GRC Analyst | Maintaining this register, running attestations, reporting coverage, escalating gaps | No |
| ISMS Steering Group | Resolving disputes, approving transfers, assigning owners to unowned assets | No |
| Managing Director | Interim owner of any asset without an owner; final escalation point | No |

**Role catalogue.** Owners and deputies are drawn only from charter §6 and NSD-ISMS-003. Custodians are teams, not individual job titles: Northstar's IT and security function is small (INT-01), and a list of 13 specialist administrator roles would describe staff it doesn't have. Named individuals are recorded in the operational version of this register, not in the portfolio copy.

| Custodian team | Led by | Covers |
| --- | --- | --- |
| DevOps team | Head of Engineering | Platform, code, pipelines, keys, technical documentation |
| IT Operations | IT Manager | Microsoft 365, identity, privileged access, backups, endpoints, monitoring tools |
| Customer Support team | Customer Support Manager | Ticketing system and support records |
| Sales team | Sales lead | Customer contract repository |
| Finance team | Finance Manager | Finance and billing systems |

## 3. Ownership allocation

| ID | Asset | Class. | Owner | Deputy owner | Custodian | Acceptance |
| --- | --- | --- | --- | --- | --- | --- |
| AST-001 | Customer platform data | Restricted | Head of Engineering | IT Manager | DevOps team | Pending |
| AST-002 | Employee and contractor HR records | Restricted | HR Manager | Managing Director | IT Operations (HR system) | Pending |
| AST-003 | Financial and billing records | Confidential | Finance Manager | Managing Director | Finance team | Pending |
| AST-004 | Source code repositories | Confidential | Head of Engineering | IT Manager | DevOps team | Pending |
| AST-005 | CI/CD pipelines and build configuration | Confidential | Head of Engineering | IT Manager | DevOps team | Pending |
| AST-006 | Encryption keys and application secrets | Restricted | Head of Engineering | IT Manager | DevOps team | Pending |
| AST-007 | SaaS production environment | Restricted | Head of Engineering | IT Manager | DevOps team / IT Operations | Pending |
| AST-008 | Microsoft 365 tenant | Restricted | IT Manager | Head of Engineering | IT Operations | Pending |
| AST-009 | Identity directory (Entra ID) | Restricted | IT Manager | Head of Engineering | IT Operations | Pending |
| AST-010 | Privileged administrator and break-glass credentials | Restricted | IT Manager | Managing Director | IT Operations | Pending |
| AST-011 | Backups of platform and corporate data | Restricted | IT Manager | Head of Engineering | IT Operations | Pending |
| AST-012 | Security event logs | Confidential | GRC Analyst | Managing Director | IT Operations | Pending |
| AST-013 | Customer support records | Confidential | Customer Support Manager | Sales lead | Customer Support team | Pending |
| AST-014 | Customer contracts and DPAs | Confidential | Sales lead | Finance Manager | Sales team | Pending |
| AST-015 | Supplier and sub-processor contracts | Confidential | Finance Manager | Managing Director | GRC Analyst | Pending |
| AST-016 | Vulnerability scan and penetration test reports | Restricted | GRC Analyst | Managing Director | IT Operations | Pending |
| AST-017 | Incident and personal data breach records | Restricted | GRC Analyst | Managing Director | Data Protection lead | Pending |
| AST-018 | Technical and architecture documentation | Confidential | Head of Engineering | IT Manager | DevOps team | Pending |
| AST-019 | Business continuity and DR plans | Confidential | Managing Director | GRC Analyst | IT Operations | Pending |
| AST-020 | Company endpoints (laptops and mobile devices) | Confidential | IT Manager | Head of Engineering | Assigned user, supported by IT Operations | Pending |

**Data Protection lead review.** The Data Protection lead must confirm the owner for AST-001. Northstar is the processor and customers are the controllers, so the owner's decisions are bounded by customer contracts and DPAs (AST-014).

## 4. Owner workload and concentration

| Role | Assets owned | Restricted owned | Deputy for |
| --- | --- | --- | --- |
| Head of Engineering | 6 | 3 | 4 |
| IT Manager | 5 | 4 | 6 |
| GRC Analyst | 3 | 2 | 1 |
| Finance Manager | 2 | 0 | 1 |
| Managing Director | 1 | 0 | 7 |
| HR Manager | 1 | 1 | 0 |
| Customer Support Manager | 1 | 0 | 0 |
| Sales lead | 1 | 0 | 1 |

**Findings**

1. **The Head of Engineering and IT Manager deputise for each other on 10 assets.** If both are unavailable at once, for example during a major incident, those assets have no cover. Escalation then goes straight to the MD, and this is recorded as a risk in the asset risk mapping (NSD-ISMS-010).
2. **The MD is deputy for 7 assets.** A deputy acts only during an absence, so this is workable, but it relies on the MD having time. The Steering Group reviews this at the first quarterly attestation.
3. **The IT Manager owns 4 of the 10 Restricted assets.** Owner time for access reviews must be part of the resource commitment in charter §8.1.

## 5. Segregation-of-duties checks (Annex A 5.3)

| Potential conflict | Assets | How it is managed |
| --- | --- | --- |
| Administrators controlling the record of their own actions | AST-012 | Logs owned by the GRC Analyst with the MD as deputy, not IT. Administrators cannot delete or change logs |
| The owner of privileged credentials is also a user of them | AST-010 | Break-glass use approved by the MD (deputy owner); every use reviewed by the GRC Analyst |
| The GRC Analyst owns security records and also runs the ISMS | AST-016, AST-017 | Internal audit is independent and outsourced (charter §6) |
| One team writes and deploys code | AST-004, AST-005 | Code approval and production deployment are separate steps by different people (NSD-ISMS-006 §4) |
| Owner, deputy and custodian are the same person | All | Checked: no role is both owner and deputy, and no owner is personally the custodian |
| The custodian team reports to the owner | Engineering and IT assets | Independent oversight comes from the deputy in the other team and from access reviews checked by the GRC Analyst |

## 6. Ownership acceptance

Ownership is effective only when the owner and deputy have formally accepted it. Acceptance is recorded with:

- Asset IDs accepted.
- Owner's and deputy's names and roles.
- Date accepted.
- Confirmation that they have read their responsibilities in section 2 and NSD-ISMS-006 §8.
- How it was recorded: signed form, email or GRC tool entry.

All 20 assets are currently **Pending**. The target is 100% accepted by month 3 (Obj 2).

## 7. Ownership principles

1. Every asset has an accountable owner within **10 working days** of being identified.
2. Ownership is assigned to a business role, not to a named person. The role holder at the time is accountable.
3. Every associated asset (system, service, credential or device) has an identified custodian.
4. Access to an asset is authorised only by its owner or, in the owner's absence, the deputy.
5. Owners can delegate tasks, but not accountability.
6. An ownership transfer is documented and accepted by the new owner **before** the current owner leaves the role. The HR leaver and mover process triggers this check.
7. An asset with no owner is escalated to the Steering Group within 10 working days. The MD is the interim owner until one is assigned.

## 8. Ownership change log

| Date | Asset | From | To | Reason | Approved by |
| --- | --- | --- | --- | --- | --- |
| — | — | — | — | No changes since first allocation | — |

## 9. Review and attestation

| Activity | Frequency | Output |
| --- | --- | --- |
| Owners confirm ownership, classification and access for Restricted assets | Quarterly | Attestation record |
| Owners confirm the same for all other assets | Six-monthly | Attestation record |
| GRC Analyst reports coverage, acceptance and overdue attestations | Each Steering Group meeting | Obj 2 status |
| Out-of-cycle review | When an owner changes role or leaves, the organisation changes, or an asset is added or retired | Updated register and change log |

Attestations follow the Asset Review and Approval Process (NSD-ISMS-011).

## 10. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves ownership assignments | Pending | |
| Data Protection lead | Confirms owners of personal data assets | Pending | |
| IT Manager | Validates custodian assignments | Pending | |
| Information Security / GRC Analyst | Maintains register | Prepared | |

## 11. Change log

| Version | Change |
| --- | --- |
| 1.0 (portfolio draft) | First draft: 20 owner and custodian assignments |
| 0.1 | Renumbered from NSD-ISMS-006 to NSD-ISMS-007, since 006 is the asset register. Asset IDs and names aligned with NSD-ISMS-006 v0.1. Owners aligned with charter roles: removed Head of Customer Operations, Commercial Director, Operations Director, Security Lead and Procurement Manager. Replaced 13 individual administrator titles with five custodian teams, to fit the small IT function (INT-01). Added deputy owners, classification and acceptance status. Added owner workload analysis, segregation-of-duties checks, the acceptance record, time limits in the principles and an ownership change log. Set the review frequency to match NSD-ISMS-006. |

---

*Portfolio note: Role assignments are simulated and require management validation.*
