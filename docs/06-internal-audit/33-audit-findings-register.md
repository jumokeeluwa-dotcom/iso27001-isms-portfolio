# Northstar Digital Solutions Ltd — Internal Audit Findings Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-033 |
| Version | 0.2 — Simulated example entries |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 9.2, 10.2) |
| Related documents | [NSD-ISMS-030 Programme](30-internal-audit-programme.md) · [NSD-ISMS-031 AUD-03 Plan](31-audit-plan-aud03-iam.md) · [NSD-ISMS-032 AUD-03 Checklist](32-audit-checklist-aud03-iam.md) · [NSD-ISMS-014 Risk Register](../03-risk-management/14-risk-register.md) · [NSD-ISMS-019 SoA](../04-controls-and-soa/19-statement-of-applicability.md) |
| Register owner | Information Security / GRC Analyst (maintains the register; **does not grade or verify findings**) |
| Grading and verification | Lead auditor (independent, NSD-ISMS-030 §3) |
| Classification | Confidential |

---

> **Every entry below is a fictional example.** No audit has taken place. The entries show how findings are recorded, graded and followed up. They follow on from the illustrative example in NSD-ISMS-032 §7, so the portfolio stays consistent.

## 1. Principles

1. **Objective evidence only.** Each finding states the requirement, the condition found, the evidence (working paper reference) and the extent (how many out of how many).
2. **Investigate before concluding** (NSD-ISMS-032 §1). An unanswered query is not a finding. It is resolved before the closing meeting, or reported as "Not tested", with the reason.
3. **Grade consistently,** using the definitions in NSD-ISMS-030 §8 and the questions in section 4.
4. **The auditee owns the fix.** The auditor describes the gap. The owner identifies the root cause and the corrective action. The auditor verifies that it worked. An auditor who designs the fix and then verifies it would be auditing their own work.
5. **One accountable owner per finding,** normally the risk owner (NSD-ISMS-017). Other people may own the individual actions.

## 2. Register

| Finding | Audit / row | Area | Requirement | Grade | Risk / control | Owner | Plan due | Closure due | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| AUD03-F01 | AUD-03 / C-06 | Leaver access | 023 §9; A 6.5; clause 8.1 | **Minor NC** | R-12; A 6.5 | HR Manager (R-12 risk owner) | 28 Jul 2027 | 28 Sep 2027 | Open: plan pending |
| AUD03-F02 | AUD-03 / C-12 | Access reviews | 023 §8; A 5.18; clause 7.5 | **Minor NC** | R-03; A 5.18 | HR Manager (AST-002 asset owner) | 28 Jul 2027 | 28 Sep 2027 | Open: plan pending |
| AUD03-F03 | AUD-03 / C-12, C-16 | Privileged access records | 023 §8 | **Observation** | R-13; A 8.2 | IT Manager | — | Reviewed at next audit | Open |

Report issued: 30 June 2027. Deadlines follow NSD-ISMS-030 §8: for a Minor, the plan is due within 20 working days and closure within 90 days.

## 3. Finding records

### AUD03-F01 — Leaver account disabled late

| Field | Entry |
| --- | --- |
| Requirement | NSD-ISMS-023 §9: leavers' accounts are disabled **by the end of the last working day**. Annex A 6.5; clause 8.1 |
| Condition | 1 of 7 leavers in the period (a contractor) was disabled **2 working days** after their last working day |
| Evidence | HR leaver report for 1 February to 31 May 2027, extracted under observation (WP-AUD03-03); Entra ID audit log of the disable events (WP-AUD03-04) |
| Extent | 1 of 7, the whole population. The other 6 were disabled on time |
| Investigation before grading | No manual disablement record exists. **Sign-in logs for the 2 days show no sign-ins** (WP-AUD03-05). HR confirmed the leaving date was entered in the HR system late |
| Impact | The account could have been used to reach company data for 2 days. No use was found |
| Grade and reasoning | **Minor nonconformity.** An isolated lapse (1 of 7), with no use of the account, while the control worked for all employee leavers. See section 4 |
| Contributing factor noted by the auditor | Automated removal (T-12.3) starts only when HR enters the leaving date, and contractor dates are entered late. **The owner confirms the root cause** |
| Immediate correction | Already complete: the account was disabled on day 2. The auditor verified this in the log |
| Corrective action | **To be proposed by the owner** by 28 July 2027 |
| Owner | HR Manager (risk owner for R-12). The IT Manager supports |
| Verification | The auditor re-tests **all** leavers in the following quarter. The finding closes only if all are disabled on time |
| Effect on other documents | R-12 control credit stays **Partial** (NSD-ISMS-014). SoA 6.5 stays **Partially implemented** (NSD-ISMS-019). Lessons learned go to the next risk review |

### AUD03-F02 — Access review not recorded

| Field | Entry |
| --- | --- |
| Requirement | NSD-ISMS-023 §8: Restricted assets are reviewed quarterly by the asset owner. Clause 7.5: documented information is retained as evidence |
| Condition | No record exists of the Q1 2027 access review for the HR SharePoint site (AST-002, Restricted) |
| Evidence | The quarterly review records provided (WP-AUD03-08) cover 4 of 5 Restricted assets in scope |
| Extent | 1 of 5 Restricted asset reviews unrecorded. The other 4 were complete, with removals done |
| Investigation before grading | It started as an open query. The auditor asked the HR Manager and the IT Manager, and searched the GRC evidence repository and email. The HR Manager says the review was discussed verbally, but **no record, approval or list of removals exists.** A verbal review cannot be evidenced, so the query became a finding |
| Impact | Unnecessary access to HR records may have gone undetected (R-03) |
| Grade and reasoning | **Minor nonconformity.** One isolated missed record; reviews worked for the other Restricted assets |
| Immediate correction | The HR Manager completes and records a review of the HR site now. The auditor checks it before closure |
| Corrective action | To be proposed by the owner |
| Owner | HR Manager (asset owner for AST-002) |
| Verification | The auditor inspects the next quarterly review record for all 5 Restricted assets |
| Effect on other documents | SoA 5.18 stays **Partially implemented** |

### AUD03-F03 — Privileged account inventory lacks review dates

| Field | Entry |
| --- | --- |
| Requirement | NSD-ISMS-023 §8: privileged roles are reviewed quarterly |
| Condition | The privileged account inventory has no "last reviewed" date for 3 of 9 accounts |
| Evidence | Privileged account inventory (WP-AUD03-10); PIM access review records (WP-AUD03-11) |
| Investigation before grading | The **PIM access review records show all 9 accounts were reviewed** in the quarter. The gap is only in the inventory spreadsheet |
| Grade and reasoning | **Observation.** The requirement (a quarterly review) was met, and the evidence exists. The inventory is incomplete, which could lead to a review being missed in future |
| Owner action | The IT Manager decides whether to fix the inventory or rely on PIM records alone. Either is acceptable |
| Follow-up | Reviewed at the next AUD-03 |

## 4. How grades are decided

The auditor answers these questions in order, using the definitions in NSD-ISMS-030 §8:

| Question | If yes |
| --- | --- |
| 1. Is a requirement met, with evidence? | No finding (Conforming). Note any improvement as an OFI |
| 2. Is the requirement met, but there is a weakness that could cause a future failure? | **Observation** |
| 3. Is the requirement not met, but the failure is isolated, contained and the control otherwise works? | **Minor nonconformity** |
| 4. Is there a systemic failure, a total absence of the control, or a failure with serious actual impact? | **Major nonconformity** |

**What would make AUD03-F01 a Major?** Any of these:

- several leavers disabled late, showing the automation is not working;
- the late account was **used** after the person left;
- an account still active at the time of the audit, weeks or months after leaving;
- no working leaver process at all.

The draft graded this finding Major "illustratively". Under these rules, with the facts in NSD-ISMS-032 §7, it is Minor. The grade follows the evidence, not how serious the scenario sounds.

## 5. Finding lifecycle

| Status | Meaning | Who moves it |
| --- | --- | --- |
| Open: plan pending | Finding issued; owner preparing the plan | Owner |
| Plan agreed | Root cause, correction and corrective action recorded; dates set | Owner, accepted by the auditor |
| Action complete | Owner has filed evidence | Owner |
| Verified effective | The auditor has tested the fix: for example, by re-testing the next quarter's population | Auditor |
| Closed | Verified, recorded in the corrective action register, reported to the Steering Group | Auditor and GRC Analyst |

Overdue plans or actions are reported to the Steering Group. Any Major open at Stage 2 would breach Obj 10.

## 6. Summary for management review

| Item | AUD-03 (illustrative) |
| --- | --- |
| Tests performed | 24 checklist rows |
| Major nonconformities | 0 |
| Minor nonconformities | 2 (F01, F02) |
| Observations | 1 (F03) |
| Overall conclusion | Identity and access management largely conforms and operates effectively. Weaknesses remain in how timely the leaver data is and in recording access reviews. These support keeping R-12 and the 5.18 and 6.5 statuses at their current levels |

## 7. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-029) | 3 illustrative findings for AUD-005 |
| 0.2 | Numbered NSD-ISMS-033, with references aligned: AUD-03; risks R-12, R-03 and R-13. **F01 regraded from Major to Minor,** to stay consistent with the NSD-ISMS-032 §7 example and the NSD-ISMS-030 definitions; section 4 shows what would make it Major. **F02's "potential nonconformity" resolved** through documented investigation into a Minor, because a provisional grade is not a valid register entry. F03 kept as an Observation, with the reason. Requirements made specific. Extent and working paper references added. Corrective actions are now proposed by the owner, not prescribed by the auditor. One accountable owner per finding. Added the lifecycle, verification approach, effect on the risk register and SoA, and a summary for management review. The draft's classification guidance is kept and applied. |

---

*Portfolio note: All findings are fictional examples. No audit has been performed.*
