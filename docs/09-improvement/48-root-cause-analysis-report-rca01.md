# Northstar Digital Solutions Ltd — Root Cause Analysis and Corrective Action Report RCA-01

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-048 (report RCA-01) |
| Version | 0.2 — Simulated training example |
| Status | **Simulated. The investigation has not actually been performed. Facts come from earlier portfolio records; results not yet in those records are shown as "to be recorded", not assumed** |
| Nonconformity | AUD03-F01 (Minor), corrective action CA-01 |
| Trigger | August 2027 KPI-01: a **second** contractor disabled 2 days late (NSD-ISMS-044 §3). A possible **repeat nonconformity**, which requires this report (NSD-ISMS-046 §5) |
| Opened | 7 Sep 2027, at the Steering Group's review of the August dashboard |
| Analysis due | 5 Oct 2027 (20 working days, Minor grade) |
| Owner | HR Manager (owner of CA-01 and risk owner of R-12). Contributor: IT Manager |
| Facilitator | Information Security / GRC Analyst |
| Verifier | Lead auditor (audit nonconformity) |
| Related documents | [NSD-ISMS-033](../06-internal-audit/33-audit-findings-register.md) · [NSD-ISMS-034 CA-01](../06-internal-audit/34-corrective-action-register.md) · [NSD-ISMS-046 procedure](46-nonconformity-corrective-action-procedure.md) · [NSD-ISMS-023 §9](../05-policies/23-access-control-policy.md) · [NSD-ISMS-015 T-12.x](../03-risk-management/15-risk-treatment-plan.md) |
| Classification | Confidential |

---

## 1. The nonconformity, stated precisely

| | Case 1: AUD03-F01 | Case 2: August 2027 |
| --- | --- | --- |
| Source | Internal audit AUD-03, 15–16 Jun 2027; **all 7 leavers** tested | KPI-01, August 2027; 9 of 10 leavers on time |
| What happened | A contractor's account disabled **2 working days** after their last day | A contractor's account disabled **2 days** after their last day |
| Use after leaving | None: sign-in logs checked (WP-AUD03-05) | None: validated with sign-in logs |
| Other leavers | 6 of 7 disabled on time | 9 of 10 disabled on time |

The finding is **not** "the organisation cannot show that leavers are checked", and the account did **not** "remain enabled" indefinitely. The whole population was tested, and the failures are specific: contractors, 2 days late, with no use. Overstating a finding damages the audit's credibility as much as understating it.

## 2. Requirement

| Requirement | Source |
| --- | --- |
| Accounts disabled, and all sessions, tokens, keys and remote access revoked, **by the end of the last working day.** A leaver record in the HR system starts this automatically | NSD-ISMS-023 §9 |
| Annex A 5.16 Identity management; 5.18 Access rights; 6.5 Responsibilities after termination | SoA (NSD-ISMS-019): all applicable, all **Partially implemented** |
| Risk | R-12, leavers keep access: rated **Very High (16)** in NSD-ISMS-014 |

Because R-12 is rated Very High, this is a **significant nonconformity** under NSD-ISMS-046 §9. The MD is informed within 2 working days of the report opening.

## 3. Correction and containment

| Step | Case 2 result |
| --- | --- |
| Disable the account; revoke sessions, tokens and keys | Done on day 2 (Entra ID log) |
| Check other access paths: Azure roles, database users, repository tokens, guest accounts | **To be recorded** by the IT Manager |
| Preserve logs | Sign-in and audit logs for the leaver exported and kept with the report |
| Check for use after the last day | No sign-ins (validated) |
| Personal or customer data affected? | No, because no use was found. **If** any use is found, the incident process starts (NSD-ISMS-027), and the Data Protection lead assesses whether it is a breach |

## 4. Root cause analysis

### 4.1 Is / is not analysis

The first question is not "why was it late?" but **"what is different about the cases that failed?"**

| | Is | Is not |
| --- | --- | --- |
| Who | Contractors | Employees: every employee leaver in both periods was on time |
| How late | 2 days | Weeks or months |
| Which control | The automated removal (T-12.3), which starts from the HR leaving date | The removal itself: once triggered, it worked |

So the cause is in the **contractor data path into the HR system**, not in the leaver process as a whole. This rules out the general explanations "no controlled workflow" and "unclear HR and IT responsibilities". The workflow exists (T-12.3, live since January 2027) and works for employees.

### 4.2 Case 1: 5 Whys (from CA-01, owner's analysis)

| Why? | Answer | Evidence |
| --- | --- | --- |
| 1. Why was the account disabled late? | The automated removal started 2 days late | Entra ID log |
| 2. Why did it start late? | The leaving date reached the HR system 2 days after the last day | HR system audit trail |
| 3. Why? | Contractor end dates are agreed by email between the hiring manager and HR | Interviews; email trail |
| 4. Why? | Contractor onboarding does not record a contract end date in the HR system | HR system field configuration |
| **Root cause** | **Onboarding does not capture the one data item the automation depends on** | |

**A contributing cause, found from the documents:** the interim daily reconciliation (T-12.1) ran only "until T-12.3 is live". Once the automation went live in January 2027, no detective control remained to catch a missed trigger. A single missing date could therefore defeat the whole control. CA-01.3, a weekly report of contractors past their end date, restores a detective check.

### 4.3 Case 2: is it a repeat? Hypotheses to test

CA-01's actions were due in August: the backfill of end dates (CA-01.2) by 13 Aug, and the mandatory field (CA-01.1) by 31 Aug. Case 2 happened in August. **What it means depends on facts not yet recorded,** so they are tested rather than assumed:

| Hypothesis | Test | If confirmed |
| --- | --- | --- |
| **H1:** Case 2 left before the backfill was complete | Compare the leaving date with the backfill completion date | **Not a repeat.** The action was not yet in place. Recorded against CA-01; no new root cause |
| **H2:** The backfill missed this contractor | Compare the backfill report with every contractor active on 13 Aug | **The extent check failed.** CA-01.2 reopened; backfill re-run against an independent list |
| **H3:** The end date was in the system, but the contract **ended early** and the change came by email | Compare the end date held in the HR system with the actual last day | **Root cause incomplete.** CA-01 fixes the start of the contract, not changes to it. A repeat nonconformity |

**H3 matters most,** because it would also defeat the new detective control. The weekly report CA-01.3 looks for contractors **past** their recorded end date. An early termination leaves the recorded date in the future, so the report would not flag it.

**Result:** to be recorded by the owner by 5 Oct 2027, with evidence for each test.

### 4.4 What "human error" would hide

"The hiring manager forgot to tell HR" may be true, but it is not a root cause. It does not explain why the process **depended** on someone remembering to send an email. The question is what allowed it: here, a process with a manual step and no independent check.

## 5. Extent check

| What is checked | Result |
| --- | --- |
| Every active contractor record has an end date (CA-01 extent check) | **To be recorded** |
| Every guest account has an expiry (KPI-15 Amber: 3 guest accounts without expiry, none for an ended contract) | Partly done: the 3 accounts were found; expiries to be set by the IT Manager |
| Other systems that rely on the HR leaving date: database users, repository tokens, device return | **To be recorded** |
| Other people outside the employee path: agency workers, suppliers' staff with accounts | **To be recorded** |

Each result is recorded even when nothing is found, together with what was checked.

## 6. Corrective actions

Existing actions are tracked in NSD-ISMS-034 and are **not repeated as new actions here.** The additional actions apply **only if H3 is confirmed**; once approved, they are added to NSD-ISMS-034 as CA-01.4 and CA-01.5.

| Action | Status | Owner | Due |
| --- | --- | --- | --- |
| CA-01.1 Mandatory contract end date at onboarding | In NSD-ISMS-034 | HR Manager | 31 Aug 2027 |
| CA-01.2 Backfill end dates for current contractors | In NSD-ISMS-034. Reopened if H2 is confirmed | HR Manager | 13 Aug 2027 |
| CA-01.3 Weekly report of contractors past their end date | In NSD-ISMS-034 | IT Manager | 31 Aug 2027 |
| **CA-01.4 (if H3):** Hiring managers record early terminations and extensions **in the HR system**, not by email. The leaver workflow starts from that record. Briefing for hiring managers | Proposed | HR Manager | 20 working days after approval |
| **CA-01.5 (if H3):** Monthly reconciliation of active contractor accounts against **Finance's** list of contractors invoiced in the month. This independent source would catch an early termination that never reached HR | Proposed | IT Manager (Finance Manager provides the list) | First run in the month after approval |

The draft's six generic actions (a leaver workflow, defined responsibilities, completion evidence, reconciliation, monitoring and training) were checked against what exists. The workflow (T-12.3), responsibilities (NSD-ISMS-023 §9) and monitoring (KPI-01) are already in place. Reconciliation and training remain, as CA-01.5 and CA-01.4, aimed at the contractor gap.

**ISMS changes (clause 10.2(e)), if H3 is confirmed:** NSD-ISMS-023 §9 gains "changes to a contractor's end date are made in the HR system"; the HR contractor procedure is updated.

## 7. Effectiveness verification

The lead auditor verifies, never the owner.

| Check | Method |
| --- | --- |
| Population | **All** leavers in the window, from the HR system (the system of record), not a sample. The population is small enough to test in full |
| Contractor coverage | The window must include **at least one contractor leaver,** and ideally one early termination. Ten employee leavers on time prove nothing about the contractor path. If none occurs, the record shows "action verified; effectiveness pending", and the window extends to the next AUD-03 |
| Timing | The HR last working day compared with the Entra ID disable and session revocation times |
| Reverse test | Active accounts compared with current HR and Finance records, to find accounts with no current owner. This catches failures that a leaver list cannot show |
| Exceptions | Every exception has an approval and a resolution date |
| No recurrence | KPI-01 at 100% for every month in the window |

Testing the whole population shows that the control worked in the window. It does not prove it will keep working, which is why KPI-01 continues monthly.

**Effect on CA-01:** its re-test (1–24 Sep 2027) and planned closure on 28 Sep 2027 are **on hold** until this report decides between H1, H2 and H3.

## 8. Closure criteria (NSD-ISMS-046 §8)

| Criterion | Status |
| --- | --- |
| 1. Actions implemented, with evidence | Pending |
| 2. Root cause addressed, with the hypothesis confirmed by evidence | Pending: H1, H2 or H3 |
| 3. Extent check completed and similar cases dealt with | Pending (section 5) |
| 4. Success measure met: 100% on time, including at least one contractor | Pending |
| 5. No recurrence in the observation period | Pending |
| ISMS documents updated (if needed) | Pending |

**Grade review:** if H3 is confirmed, the Steering Group reconsiders the grade. NSD-ISMS-033 §4 lists "several leavers disabled late, showing the automation is not working" as a Major trigger. Two cases with the same cause in three months comes close to that.

**Risk update (good practice):** R-12 control credit stays Partial until verification passes.

## 9. Sign-off

| Role | Name | Decision | Date |
| --- | --- | --- | --- |
| Owner | HR Manager | Root cause and actions: pending | |
| Facilitator | GRC Analyst | Analysis complete: pending | |
| Verifier | Lead auditor | Effectiveness: pending | |
| Informed (significant nonconformity) | Managing Director | | |

## 10. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-044) | Generic report: "former employee", FIND-001, joint owners, 30- and 45-day targets |
| 0.2 | Numbered NSD-ISMS-048 (RCA-01), linked to AUD03-F01 and CA-01. **Trigger stated:** the August repeat case, as required by NSD-ISMS-046 §5. Facts aligned with the records: a contractor, 2 days late, whole population tested, no use, not "cannot demonstrate". Requirement made specific (023 §9; SoA status). Added is / is not analysis, which shows the cause is specific to contractors and rules out the draft's general "no workflow" chain; the 5 Whys taken from CA-01, plus a contributing cause (detective control removed when T-12.3 went live). Case 2 handled as **three hypotheses with tests,** not an assumed answer. Existing actions referenced rather than duplicated; two conditional actions added. Verification uses the whole population, requires a contractor in the window, and adds a reverse test. One owner; the lead auditor verifies; MD informed because R-12 is Very High. |

---

*Portfolio disclaimer: Simulated training example. It is not evidence of an actual Northstar incident, investigation or completed corrective action.*
