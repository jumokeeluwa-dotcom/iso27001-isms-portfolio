# Northstar Digital Solutions Ltd — Internal Audit Plan: AUD-03 Identity and Access Management

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-031 |
| Audit reference | AUD-03 (NSD-ISMS-030 §5) |
| Version | 1.0 — Plan for issue to auditees |
| Status | Planned (simulated) |
| Lead auditor | External auditor, ISO/IEC 27001 Lead Auditor. Independence confirmation required before fieldwork (NSD-ISMS-030 §3) |
| Programme manager | Information Security / GRC Analyst: logistics only, attends as observer, does not audit |
| Audit dates | **15 June 2027** (full day) and **16 June 2027** (morning): 1.5 auditor days |
| Plan issued | 1 June 2027, 2 weeks before fieldwork (NSD-ISMS-030 §9) |
| Report due | 30 June 2027, within 10 working days |
| Period tested | **1 February to 31 May 2027.** This starts after automated leaver removal went live (T-12.3, due 29 January 2027) and gives about 4 months of operation |
| Classification | Confidential |

---

## 1. Objective

To determine whether identity and access management at Northstar:

1. **conforms** to ISO/IEC 27001:2022, to the applicable SoA controls and to the Access Control and Identity Management Policy (NSD-ISMS-023);
2. is **operating effectively** across the period tested;
3. has delivered the risk treatment actions for the access risks, so that the risk register scores are supported by evidence.

## 2. Scope

**Included**

- Joiner, mover and leaver processing (employees and contractors, UK and EU).
- Access requests and approvals; least privilege; segregation of duties in provisioning.
- Periodic access reviews.
- Authentication: MFA, legacy authentication, service accounts.
- Privileged access: just-in-time roles, separate admin accounts, break-glass accounts.
- Access to production customer data.
- Supplier and guest accounts.
- Access-related exceptions.

**Systems:** Microsoft Entra ID (including Privileged Identity Management and Conditional Access), Microsoft 365, Azure subscriptions, the production database, and the HR system.

**Excluded, and covered in other audits:**

- Source code repository access (8.4): AUD-04.
- Log integrity and retention (8.15): AUD-04.
- Supplier due diligence (5.19–5.22): AUD-06.

## 3. Audit criteria

| Criterion | Reference |
| --- | --- |
| ISO/IEC 27001:2022 clauses | 6.1.3 (SoA accuracy), 7.5 (documented information), 8.1 (operational control), 8.3 (treatment implemented), 9.1 (measures) |
| Annex A controls, applicable in the SoA (NSD-ISMS-019) | 5.15, 5.16, 5.17, 5.18, 6.5, 8.2, 8.3, 8.5 |
| Policy | **NSD-ISMS-023** Access Control and Identity Management Policy |
| Ownership | NSD-ISMS-007: asset owner approval of access |
| Risk treatment | NSD-ISMS-015 actions T-01.1, T-10.1, T-11.1, T-12.1–12.3, T-13.1, T-13.2, T-16.1 |
| Exceptions | NSD-ISMS-008 §8 |

## 4. Risk context: where the auditor focuses

| Risk | Current score (NSD-ISMS-014) | Why it matters here |
| --- | --- | --- |
| R-12 Leavers keep access | **16 Very High** | The former-employee scenario. The risk owner is the HR Manager (NSD-ISMS-017) |
| R-13 Privileged credential misuse | 15 High | Impact 5; target acceptance record AR-02 depends on T-13.1 and T-13.2 working |
| R-01 Customer data exfiltration | 15 High | Depends on just-in-time database access (T-01.1) |
| R-11 Password spraying and service accounts | 12 High | Service accounts were excluded from MFA |

SoA weak points to test: 6.5, 5.16, 5.17, 5.18, 8.2 and 8.5 are all **Partially implemented**. Control 8.5 treats 6 risks (NSD-ISMS-020).

## 5. Roles

| Role | Person | Responsibility |
| --- | --- | --- |
| Lead auditor | External auditor | Plans, tests, grades findings, reports |
| Process owner | IT Manager (owner of NSD-ISMS-023) | Provides system walkthroughs and records; arranges read-only access |
| Risk owner for R-12 | HR Manager | Provides joiner, mover and leaver records from the HR system |
| Platform owner | Head of Engineering | Production data access (8.3, T-01.1) |
| Asset owners | Sampled owners | Confirm the approvals they gave |
| Observer | GRC Analyst | Logistics only. Does not test, interpret evidence or grade findings |
| Recipient | Managing Director and Steering Group | Receive the report and approve corrective actions |

## 6. Tests

**Sampling rule** (NSD-ISMS-021 §4.3): where a population has **fewer than 25 items, the whole population is tested.** Populations are drawn from the **source system of record**, not from the process being tested. For example, leavers come from the HR system, never from IT's own list.

| Test | Control | Criterion | Population and source | Sample | Procedure | Pass criterion |
| --- | --- | --- | --- | --- | --- | --- |
| IAM-01 Leavers | 6.5, 5.18 | 023 §9 | Leavers in the period, **from the HR system** | **All** (expected under 25) | Compare HR last working day with the Entra ID disable time and session revocation. Check database users, guest accounts and tokens. Confirm device returned | Disabled by the end of the last working day; no remaining access; device returned |
| IAM-02 Orphan accounts | 5.16 | 023 §4 | All enabled Entra ID user accounts | **All** | Match every enabled account to a current HR record or to an owned service account (the reverse direction of IAM-01) | No account without a current person or owner |
| IAM-03 Joiners | 5.16, 5.18 | 023 §5, §9 | Joiners in the period, from the HR system | **All** | Check the access request, asset owner approval and provisioner; compare provisioning date with start date | Approved before provisioning; provisioner is not the requester; no access before start date |
| IAM-04 Movers | 5.18 | 023 §9 | Role changes in the period, from the HR system | **All** | Compare access before and after the move | Access for the old role removed within 5 working days |
| IAM-05 Access grants | 5.18 | 023 §5; NSD-ISMS-007 | Access grants to Restricted assets, from the access request log | 25 | Trace each grant to its approval | Approved by the asset owner or deputy named in NSD-ISMS-007 |
| IAM-06 Access reviews | 5.18 | 023 §8 | Quarterly reviews of Restricted assets and privileged roles in the period | 2 (quarterly control) | Inspect review records, then trace removals to the system | Review completed on time; removals done within 5 working days |
| IAM-07 MFA and legacy authentication | 8.5 | 023 §6 | All accounts: MFA registration report, Conditional Access export, 30 days of sign-in logs | **All** (system report) | Check MFA coverage and legacy sign-ins. **Re-perform:** attempt a legacy sign-in with an authorised test account | 100% coverage; zero legacy sign-ins; the test attempt is blocked; administrators use phishing-resistant MFA |
| IAM-08 Service accounts | 5.17, 8.5 | 023 §4, §6 | Service account inventory, compared with Entra ID | **All** | Check owner, purpose and protection (managed identity or Conditional Access) | Every account has an owner and purpose, and is protected |
| IAM-09 Privileged roles | 8.2 | 023 §7 | All privileged role assignments; PIM activation log | All assignments; 25 activations | Check standing assignments and separate admin accounts. Check each sampled activation's approval, justification and time limit | No standing Global Administrators apart from 2 break-glass; every activation approved |
| IAM-10 Break-glass accounts | 5.17, 8.2 | 023 §7.3 | Break-glass accounts and their use in the period | **All** | Inspect the vault record, alert rule, quarterly test and any use | Alert works; tested quarterly; any use was MD-approved and reviewed |
| IAM-11 Production data access | 8.3 | 023 §7.4 (T-01.1) | Database role assignments; just-in-time access requests | All assignments; 25 requests (or all, if fewer) | Check for standing read access; check each request's approval and expiry | No standing access; every request approved and time-limited |
| IAM-12 Guest and supplier accounts | 5.18 | 023 §10 (T-16.1) | All guest accounts in Entra ID | **All** | Check sponsor, MFA and expiry; compare with ended contracts | Sponsor named; MFA on; expiry within 90 days; none left after contract end |
| IAM-13 Exceptions | 5.15 | NSD-ISMS-008 §8 | Access-related entries in the exceptions log | **All** | Check approver, duration and compensating controls | Approved by the right authority (MD for Restricted or privileged); 12 months or less |
| IAM-14 Treatment actions and SoA | Clauses 6.1.3, 8.3 | NSD-ISMS-015, 019 | The access-related treatment actions listed in section 3 | **All** | Compare the closure evidence on file with what the system shows today; compare SoA statuses with the test results | Evidence matches reality; SoA statuses supported |
| IAM-15 Policy and measures | Clauses 7.5, 9.1 | 023 §12 | Policy approval and acknowledgement records; access measures | — | Inspect | Policy approved; acknowledged by 95% or more of staff; measures reported to the Steering Group |

## 7. Evidence requested in advance

Requested from the IT Manager and HR Manager by **8 June 2027**:

1. HR system reports for the period: leavers, joiners and movers, with dates.
2. Read-only auditor access to Entra ID reports and Azure role assignments.
3. The access request log and quarterly access review records.
4. The service account inventory and the break-glass vault record.
5. The exceptions log (access entries).
6. Closure evidence for the treatment actions in section 3.

**Evidence integrity**

- System reports are **extracted in front of the auditor** on 15 June, or exported with the system's timestamp, so that populations are complete and unaltered.
- Employee IDs are used instead of names where possible (NSD-ISMS-021 §7).
- The auditor has **read-only** access. The IAM-07 legacy sign-in test uses an authorised test account under an approved change record.

## 8. Timetable

| Date and time | Activity | Attendees |
| --- | --- | --- |
| 15 Jun, 09:00–09:30 | Opening meeting: scope, criteria, logistics, independence confirmation | Lead auditor; IT Manager; HR Manager; Head of Engineering; GRC Analyst (observer) |
| 15 Jun, 09:30–12:30 | Walkthrough of Entra ID, PIM and Conditional Access; populations extracted. Tests IAM-02, 07, 08, 09, 10 | Lead auditor; IT Manager |
| 15 Jun, 13:30–15:00 | HR interview and leaver, joiner and mover records. Tests IAM-01, 03, 04 | Lead auditor; HR Manager |
| 15 Jun, 15:00–17:00 | Tests IAM-05, 06, 11, 12. Short interviews with sampled asset owners | Lead auditor; Head of Engineering; asset owners |
| 16 Jun, 09:00–11:00 | Tests IAM-13, 14, 15; follow-up of open questions | Lead auditor; IT Manager |
| 16 Jun, 11:30–12:30 | Closing meeting: findings and grades presented, disagreements recorded | Lead auditor; IT Manager; HR Manager; Head of Engineering; MD (invited); GRC Analyst (observer) |

## 9. Reporting and follow-up

- Findings are graded as major, minor, observation or opportunity for improvement (NSD-ISMS-030 §8). Each states the requirement, the evidence and the gap.
- The report covers every test, its population and sample, the result and an overall conclusion on conformity and effectiveness.
- It is issued by **30 June 2027** to the auditees, the MD and the Steering Group.
- Findings go into the corrective action register. The **auditor** verifies closure.
- Results feed into NSD-ISMS-014 (re-scoring R-01, R-11, R-12 and R-13) and NSD-ISMS-019 (statuses of 5.15–5.18, 6.5, 8.2, 8.3 and 8.5).

## 10. Risks to the audit

| Risk | Mitigation |
| --- | --- |
| Key auditees on leave in June | Dates confirmed with the IT Manager and HR Manager when the plan is issued; deputies named (NSD-ISMS-017 §7) |
| Incomplete or edited populations | Extraction observed by the auditor; record counts compared between HR and Entra ID |
| Auditor sees personal data | Read-only access; employee IDs; working papers classified Confidential |
| The live test (IAM-07) affects service | Test account only, under an approved change record |

## 11. Approval

| Role | Decision | Date |
| --- | --- | --- |
| Lead auditor | Plan prepared | |
| Managing Director | Plan noted | |

---

*Portfolio note: Simulated audit plan for a fictional organisation.*
