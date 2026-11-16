# Northstar Digital Solutions Ltd — Internal Audit Report: AUD-03 Identity and Access Management

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-035 |
| Audit reference | AUD-03 (NSD-ISMS-030 §5) |
| Status | **Illustrative completed report.** It is built only from the simulated facts in NSD-ISMS-032 §7, 033 and 034. **No audit has been conducted** |
| Lead auditor | External auditor, ISO/IEC 27001 Lead Auditor. Independence confirmed in writing before fieldwork (NSD-ISMS-030 §3) |
| Fieldwork | 15–16 June 2027 |
| Period tested | 1 February to 31 May 2027 |
| Report date | 30 June 2027 |
| Recipients | Managing Director; ISMS Steering Group |
| Classification | Confidential |

---

## 1. Executive summary

**Conclusion: identity and access management conforms to ISO/IEC 27001:2022 and to NSD-ISMS-023, and is operating effectively, with two minor exceptions.**

The audit tested 24 questions across the full joiner, mover and leaver lifecycle, authentication, privileged access, third-party access and exceptions. Whole populations were tested wherever they had fewer than 25 items.

| Result | Count |
| --- | --- |
| Major nonconformities | **0** |
| Minor nonconformities | **2** |
| Observations | **1** |
| Questions conforming | 22 of 24 (C-06 and C-12 have nonconformities; the observation sits on rows that still conform) |

**Strengths**

- MFA covers every account, and legacy sign-in is blocked. The auditor confirmed this by attempting a legacy sign-in, which was blocked.
- Privileged access is just in time, with only the two break-glass accounts held standing.
- No orphaned accounts were found.
- Guest accounts expire within 90 days.

**Weaknesses needing management attention**

1. **Leaver timeliness depends on HR data entry.** One contractor was disabled 2 days late because their contract end date had not been recorded (AUD03-F01). The automated removal works; the data it depends on did not arrive in time.
2. **Access reviews rely on memory, not a recorded workflow.** One review of a Restricted asset could not be evidenced (AUD03-F02).

**Priorities**

- Record contract end dates at contractor onboarding (CA-01).
- Move access reviews into a recorded system workflow (CA-02).

Both are due by 31 August 2027 and are verified by the auditor by 28 September 2027.

## 2. Objective, scope and criteria

| Item | Summary |
| --- | --- |
| Objective | To determine whether identity and access management conforms to requirements, operates effectively, and has delivered its risk treatment actions (NSD-ISMS-031 §1) |
| Scope | Joiners, movers and leavers; access approval and least privilege; access reviews; authentication; privileged and break-glass access; production data access; guest accounts; exceptions. Systems: Entra ID, Microsoft 365, Azure, the production database, the HR system |
| Excluded | Source code access, logging and monitoring (AUD-04); supplier due diligence (AUD-06) |
| Criteria | ISO/IEC 27001:2022 clauses 6.1.3, 7.5, 8.1, 8.3 and 9.1. Annex A 5.15–5.18, 6.5, 8.2, 8.3 and 8.5 (SoA NSD-ISMS-019). Policy NSD-ISMS-023. Treatment actions T-01.1, T-10.1, T-11.1, T-12.1–12.3, T-13.1, T-13.2, T-16.1 |

## 3. Approach and evidence

- Methods: document review, interviews, walkthroughs, **re-performance**, and population testing (NSD-ISMS-031 §6).
- Populations were drawn from systems of record (the HR system for the employee lifecycle), with extraction observed by the auditor (NSD-ISMS-032 §3).
- Populations under 25 were tested in full: leavers (7), Restricted asset reviews (5) and privileged accounts (9), among others. Larger populations were sampled randomly to 25.
- All evidence is referenced as WP-AUD03-nn and held in the Confidential audit folder.

## 4. Results by area

| Area | Checklist rows | Result | Comment |
| --- | --- | --- | --- |
| Governance | C-01, C-02 | Conforming | Policy approved and acknowledged; measures reported to the Steering Group |
| Identity lifecycle | C-03 to C-09 | **1 Minor (F01)**; others conforming | All 7 leavers had no remaining access and returned devices (C-07). No orphaned accounts (C-08). All service accounts owned and protected (C-09) |
| Access approval and least privilege | C-10 to C-12 | **1 Minor (F02); 1 Observation (F03)**; others conforming | Grants approved by asset owners. No standing production data access |
| Authentication | C-13 to C-15 | Conforming | Legacy sign-in attempt blocked when re-performed |
| Privileged access | C-16 to C-19 | Conforming | Only 2 break-glass accounts standing; activations approved; break-glass tested quarterly |
| Third-party access | C-20 | Conforming | All guest accounts within 90-day expiry |
| Exceptions, incidents and treatment | C-21 to C-24 | Conforming | Treatment evidence matches the live configuration. No access-related incidents in the period |

Results other than the three findings are illustrative assumptions made to complete this example report.

## 5. Findings

Full records are in NSD-ISMS-033.

| Finding | Grade | Summary | Extent | Owner | Corrective action |
| --- | --- | --- | --- | --- | --- |
| AUD03-F01 | Minor nonconformity | A contractor's account was disabled 2 working days after their last day (NSD-ISMS-023 §9; A 6.5). No sign-ins in that time | 1 of 7 leavers | HR Manager | CA-01 |
| AUD03-F02 | Minor nonconformity | The Q1 access review of the HR SharePoint site (AST-002) was not recorded (NSD-ISMS-023 §8; A 5.18; clause 7.5) | 1 of 5 Restricted asset reviews | HR Manager | CA-02 |
| AUD03-F03 | Observation | The privileged account inventory lacks review dates for 3 accounts, although PIM records show all 9 were reviewed | 3 of 9 inventory entries | IT Manager | IMP-01 (optional) |

**Why F01 is Minor, not Major:** the lapse was isolated (1 of 7), there is no evidence the account was used, and the control worked for every employee leaver. A pattern of late removals, any use of a leaver's account, or an account left active for weeks would have made it Major (NSD-ISMS-033 §4).

## 6. Good practice

- **Reverse testing finds nothing missing.** Every enabled account matched a current person or an owned service account. This is the strongest evidence that the former-employee risk (R-12) is controlled.
- **Treatment evidence matches the live systems.** What was filed when actions closed still matched what the systems showed at the audit.
- **Break-glass accounts are well controlled:** alerts are working, quarterly tests are recorded, and there was no unapproved use.

## 7. Conclusion

| Audit objective | Conclusion |
| --- | --- |
| Conformity with ISO/IEC 27001 and NSD-ISMS-023 | **Conforms, with two minor exceptions** |
| Operating effectiveness, February–May 2027 | **Effective**, except for leaver timeliness for contractors and the recording of reviews |
| Delivery of risk treatment actions | **Delivered.** Evidence matches the live configuration |

This conclusion rests on tested evidence from the period, including re-performance and population testing. It does not rest on the existence of the policy.

## 8. Implications for the ISMS

For the risk owners and the GRC Analyst to act on. The auditor does not change these documents directly.

| Document | Recommendation |
| --- | --- |
| **SoA (NSD-ISMS-019)** | Controls 8.2, 8.3, 8.5, 5.16 and 5.17 now have passing effectiveness evidence (this audit) and may move to **Implemented** (NSD-ISMS-021 §3). Controls 5.18 and 6.5 stay **Partially implemented** until CA-01 and CA-02 are verified |
| **Risk register (NSD-ISMS-014)** | Re-score R-01, R-11 and R-13 at the next risk review, using this evidence for control credit. R-12 stays at its current credit until CA-01 is verified |
| **Acceptance record AR-02** (NSD-ISMS-016) | Its conditions (T-13.1 and T-13.2 verified) are supported by C-16 to C-18 |

## 9. Corrective actions and follow-up

- Both nonconformities are in the corrective action register (NSD-ISMS-034) as CA-01 and CA-02, owned by the HR Manager.
- Plans are due by **28 July 2027**; closure, with effectiveness verified by the auditor, by **28 September 2027**.
- The status of these actions is an input to management review (clause 9.3) in September 2027.

## 10. Limitations

- The audit covered 1 February to 31 May 2027. Conclusions do not extend beyond that period.
- Populations of 25 or more were sampled, so the conclusions for them carry sampling risk.
- The auditor had read-only access and relied on system-generated reports, with extraction observed.
- Logging, source code access and supplier due diligence were excluded, and are covered by AUD-04 and AUD-06.

## 11. Management response

| Finding | Response | Owner |
| --- | --- | --- |
| AUD03-F01 | Accepted. Root cause analysis and plan to be submitted by 28 July 2027 | HR Manager |
| AUD03-F02 | Accepted. The correcting review is to be completed and recorded by 16 July 2027 | HR Manager |
| AUD03-F03 | Noted. The owner will decide on a single source of review records | IT Manager |

## 12. Distribution

Managing Director; ISMS Steering Group; IT Manager; HR Manager; Head of Engineering; GRC Analyst (programme manager, for the records). **Not for distribution outside Northstar**, except to the certification body on request.

## 13. Sign-off

| Role | Name | Date |
| --- | --- | --- |
| Lead auditor | | 30 Jun 2027 (illustrative) |
| Managing Director: report received | | |

## 14. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-031) | Report template with illustrative findings |
| 0.2 | Numbered NSD-ISMS-035, with audit reference AUD-03. Completed as an illustrative report, consistent with NSD-ISMS-032, 033 and 034. F01 shown as Minor and F02 as a resolved Minor, replacing "Illustrative major" and "Pending investigation", which no final report can carry. Owners aligned. Added the independence statement, a results table by area, a conclusion for each audit objective, good practice, implications for the SoA and risk register, limitations, management responses and a restricted distribution. Recipient changed from "Senior Management" to the MD and Steering Group. The draft's rule that the conclusion must not rest on policies alone is kept and applied. |

---

*Portfolio note: Illustrative report only. It is not evidence that an internal audit has been conducted.*
