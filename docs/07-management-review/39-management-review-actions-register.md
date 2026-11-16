# Northstar Digital Solutions Ltd — Management Review Actions Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-039 |
| Version | 0.2 — Simulated examples |
| Procedure | [NSD-ISMS-036](36-management-review-procedure.md) §8 · Decisions recorded in [NSD-ISMS-038](38-management-review-minutes-template.md) §4 |
| Register owner | Information Security / GRC Analyst (tracks; verifies evidence for actions it does not own) |
| Reviewed | At every monthly Steering Group meeting; status is input (a) to the next management review |
| Classification | Confidential |

---

> **Hypothetical examples.** The actions in section 2 show how actions **would** be recorded **if** top management took the decisions expected at MR-2027-01 (NSD-ISMS-037 §D). They are not actual decisions or commitments.

## 1. What belongs in this register

| Belongs here | Does not belong here |
| --- | --- |
| Actions arising from a **management review decision** | Corrective actions for nonconformities: these go in **NSD-ISMS-034** |
| Changes to the ISMS, objectives, resources or scope that the review decides on | Risk treatment actions: these go in **NSD-ISMS-015** |
| | Inputs to the review, such as "review objectives progress" |

Where the review takes a decision about an item in another register (for example, "escalate CA-01 if not verified"), the decision is minuted. The item **stays in its own register** and is listed in section 3 for monitoring. **Each action lives in one register only,** so it has one status.

## 2. Action register (illustrative)

| Action | Decision | Action required | Expected outcome | Accountable owner | Raised | Due | Completion evidence | Verified by | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| MRA-2027-01 | DEC from D-05 (SoA v1.0 approved) | Enter SoA v1.0 and its date in the scope statement (NSD-ISMS-004 §3) and send both to the certification body | Certificate scope references the approved SoA | GRC Analyst | 22 Sep 2027 | 29 Sep 2027 | Updated NSD-ISMS-004; certification body acknowledgement | Internal auditor (GRC-owned action) | Proposed |
| MRA-2027-02 | DEC from D-06 | Write and approve the **legal, regulatory and contractual requirements register (NSD-ISMS-005)**, including decisions on NIS2 and Cyber Security and Resilience Bill applicability | The obligations in NSD-ISMS-003 §4 are recorded with owners and evidence | Data Protection lead | 22 Sep 2027 | 30 Nov 2027 | NSD-ISMS-005 approved by the MD | GRC Analyst; sampled at the next AUD-01 | Proposed |
| MRA-2027-03 | DEC from D-02 | Add R-21 (customer data sent to personal accounts by mistake) to the risk register; score it and assign a risk owner | The new risk is assessed and owned | GRC Analyst (coordinates); risk owner named by the MD | 22 Sep 2027 | 31 Oct 2027 | NSD-ISMS-014 and NSD-ISMS-017 updated | Internal auditor (GRC-owned action) | Proposed |
| MRA-2027-04 | DEC from D-07 | Raise security awareness training completion to the Obj 5 target | 95% or more of staff and contractors trained; phishing report rate improving | HR Manager | 22 Sep 2027 | 31 Dec 2027 | Training system completion report; phishing simulation results | GRC Analyst | Proposed |
| MRA-2027-05 | DEC from D-04 | Engage the external internal auditor for cycle 2 (about 12 days) within the 2028 budget | Audit programme cycle 2 resourced | Finance Manager | 22 Sep 2027 | 31 Oct 2027 | Signed engagement letter; budget line | GRC Analyst | Proposed |
| MRA-2027-06 | DEC from D-04 | Name a third person able to act on engineering and IT risks when the Head of Engineering and IT Manager are both unavailable (ARM-26) | Cover for 12 risks during major incidents | Managing Director | 22 Sep 2027 | 31 Dec 2027 | NSD-ISMS-017 §7 updated; the deputy has accepted | GRC Analyst | Proposed |

**Expected outcome** states what will be true when the action works. It is the basis for checking effectiveness, not just completion.

## 3. Items monitored by the review but tracked elsewhere

| Item | Register | Due | Review decision (illustrative) |
| --- | --- | --- | --- |
| CA-01: contractor leaver end dates (AUD03-F01) | NSD-ISMS-034 | Verify by 28 Sep 2027 | Monitor. Escalate to the MD if not verified effective by the due date |
| CA-02: access reviews in Entra ID (AUD03-F02) | NSD-ISMS-034 | Verify by 28 Sep 2027 | Monitor, as for CA-01 |
| CA-03: DLP for personal email (INC-2027-014) | NSD-ISMS-034 | 31 Aug 2027 | Confirm the effectiveness result at the review |
| Supplier assessments (Obj 9, T-16.2) | NSD-ISMS-026; NSD-ISMS-015 | Annual | Confirm 100% of Critical suppliers assessed |
| Target acceptances AR-01 and AR-02 | NSD-ISMS-016 | At the review | Decided at the review (D-01). The result is recorded in NSD-ISMS-016, not here |

## 4. Required fields (operational register)

The draft's field list is kept, with the following additions and clarifications:

| Field | Note |
| --- | --- |
| Action ID | MRA-YYYY-nn |
| Source review and **decision reference** | MR-YYYY-nn / DEC-YYYY-nn (NSD-ISMS-038 §4) |
| Description; reason; **expected outcome** | The outcome is what effectiveness is judged against |
| **One** accountable owner; supporting people | Supporting people can be several; the accountable owner is one |
| Priority; date raised; target date | |
| Status; progress update | Status values in section 5 |
| Completion evidence | An evidence reference, not a statement |
| **Verified by** | Not the owner. The internal auditor where the GRC Analyst owns the action |
| Effectiveness result | Whether the expected outcome was achieved |
| Closure date | |
| Escalation | Date escalated and to whom |
| Date changes | Old date, new date, reason, approved by the MD |

## 5. Status values

| Status | Meaning |
| --- | --- |
| Proposed | Example or draft. No decision taken yet |
| Open | Decision taken; owner and date assigned |
| In progress | Work under way |
| Blocked | Cannot proceed. The blocker is recorded and raised at the next Steering Group |
| Overdue | Past the due date. Reported to the Steering Group; **escalated to the MD after 30 days** (NSD-ISMS-036 §8) |
| Complete: evidence filed | The owner has filed evidence |
| Verified | The verifier has checked the evidence and the expected outcome |
| Closed | Verified and recorded |
| Cancelled | No longer needed. **Only with MD approval and a recorded reason** |

## 6. Lifecycle

1. Record the management decision (NSD-ISMS-038 §4).
2. Assign one accountable owner, a due date and the expected outcome.
3. Confirm the resources needed.
4. Track progress at each monthly Steering Group meeting.
5. Escalate overdue or blocked actions.
6. Obtain evidence of completion.
7. **Verify** the evidence and the expected outcome. The verifier is never the owner.
8. Close the action and keep the record. Its status is input (a) to the next review.

An action is **never marked complete only because the owner says it is done.**

## 7. What happened to the draft's example actions

| Draft action | Disposition | Reason |
| --- | --- | --- |
| MRA-001 Review and update the asset register | **Removed** | Already done by the quarterly attestation (NSD-ISMS-011). Raise an action only if the review finds a gap |
| MRA-002 Complete overdue access reviews | **Tracked as CA-02** (NSD-ISMS-034) | Duplicate of a corrective action |
| MRA-003 Improve leaver evidence retention | **Tracked as CA-01** (NSD-ISMS-034) | Duplicate of a corrective action |
| MRA-004 Review cloud supplier assurance | **Monitored** (section 3) | Already covered by T-16.2 and Obj 9 |
| MRA-005 Improve awareness training | **Replaced by MRA-2027-04** | Made measurable: 95% completion by a set date |
| MRA-006 Review progress against objectives | **Removed** | An input to the review (clause 9.3.2(d)(4)), not an action |

## 8. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-035) | Six example actions, tracking fields and lifecycle |
| 0.2 | Numbered NSD-ISMS-039. Added the rule that each action lives in one register: duplicates of CA-01 and CA-02 moved to monitoring, and the review input removed. Example actions now come from the decisions expected at MR-2027-01, each with a decision reference, expected outcome, one accountable owner, dates, completion evidence and an independent verifier. Includes the missing legal register (MRA-2027-02) and the ARM-26 deputy gap (MRA-2027-06). Added defined status values, 30-day escalation to the MD, date-change and cancellation rules, and the disposition of each draft action. The draft's field list, lifecycle and evidence principle are kept. |

---

*Portfolio note: All actions are hypothetical examples. They are not actual management decisions or assigned commitments.*
