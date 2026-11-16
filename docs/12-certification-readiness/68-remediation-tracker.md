# Northstar Digital Solutions Ltd — Certification Gap and Remediation Tracker

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-068 |
| Version | 0.2 — Simulated tracker |
| Status | **Simulated planning items. No action is shown as complete unless a record exists; where a due date has passed with no record, the item is Overdue** |
| Position as at | 15 October 2027 (after the baseline mock Stage 1, NSD-ISMS-066) |
| Sources | [061](61-clause-gap-assessment.md) · [062](62-annex-a-control-readiness-review.md) · [063](63-soa-validation.md) · [064](64-audit-evidence-index.md) · [065](65-certification-readiness-report.md) · [066](66-mock-stage1-audit.md) · [067](67-mock-stage2-audit.md) |
| Owner | Information Security / GRC Analyst (maintains and reports; **does not accept risk or verify its own actions**) |
| Approver | Managing Director |
| Classification | Confidential |

---

## 1. How the tracker works

**One register per item.** Most certification gaps are already actions in another register: a corrective action (034), a risk treatment action (015), a proposed management review action (039), a supplier assessment (058) or a scheduled test. This tracker **points to** that record and does not copy it, so each action has one owner, one date and one status.

Only gaps with **no other home** become new remediation actions here (**RA-nn**). The draft gave every gap a new CR number, including work already tracked elsewhere and two items (internal audit and management review) described as not yet started.

| Field | Meaning |
| --- | --- |
| Blocks | **S1:** must be closed before external Stage 1. **S2:** before Stage 2 |
| Home | The register and ID where the action is tracked |
| Owner | One accountable charter role |
| Closure evidence | The evidence index item (064) that will prove it |
| Verifier | Independent of the owner |

**Status values:** Open · In progress · **Overdue** (due date passed, no record) · Done, awaiting verification · **Closed** (verified). "Done" is never reported as "Closed".

## 2. Tracker

### Stage 1 blockers

| # | Gap | Source | Home | Owner | Due | Status | Closure evidence | Verifier |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| G01 | Approve scope, policy, objectives and risk acceptance criteria | MS1-01; 061 gap 1; S1-1 | **RA-01** | MD | 30 Nov 2027 | Open | EVD-003, 005, 007, 012 | Second mock Stage 1 |
| G02 | **Hold and minute the first management review,** with decisions D-01 to D-08 | MS1-13; F11; S1-6 | **RA-02** (decisions then recorded as MRA actions in 039) | MD | 30 Nov 2027 | **Overdue** (planned 22 Sep 2027; no record) | EVD-004, 021 | Second mock Stage 1 |
| G03 | Complete SoA Wave 2 (45 controls); owners confirm the 063 §4 changes; one owner per control; approve the SoA | MS1-02; MS1-11; 063 | **RA-03** | GRC Analyst (MD approves the SoA) | 31 Jan 2028 | **Overdue** (Wave 2 due 29 Jan 2027) | EVD-010 | Second mock Stage 1 |
| G04 | Legal, regulatory and contractual register | MS1-06; F4 | 039 **MRA-2027-02** (proposed: needs G02 decision) | Data Protection lead | 30 Nov 2027 | Open | EVD-036 | GRC Analyst |
| G05 | Resolve the policy acknowledgement conflict (KPI-20) | MS1-04; F2 | **RA-04** | HR Manager (KPI-20 owner) | 15 Nov 2027 | Open | EVD-005 | Internal auditor |
| G06 | Add R-21 to the risk register; confirm scores once criteria are approved | 061: 6.1.2, 8.2 | 039 **MRA-2027-03** (proposed: needs G02 decision) | GRC Analyst; risk owner named by MD | 31 Oct 2027 | Open | EVD-008 | Internal auditor |
| G07 | Reschedule the internal audit programme; record the decision to postpone 8 audits | MS1-03 | **RA-05** | MD (audit sponsor) | 15 Nov 2027 | Open | EVD-020 | Second mock Stage 1 |

### Stage 2 blockers

| # | Gap | Source | Home | Owner | Due | Status | Closure evidence | Verifier |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| G08 | Complete internal audits AUD-01, 02, 04 to 09 | MS1-03; F5 | 030 (rescheduled under G07); auditor engagement: 039 **MRA-2027-05** (proposed) | MD (sponsor); external auditor | Jan–Apr 2028 | Open | EVD-020 | Mock Stage 2 (T14) |
| G09 | Management review **after** the audit cycle | S2-2 | 036 schedule | MD | May 2028 | Open | EVD-021 | Mock Stage 2 (T15) |
| G10 | Risk acceptance and interim tolerances, including the 4 Very High risks | MS1-08 | 016 Part B | Risk owners; MD for Very High | 15 Dec 2027 (after G01) | Open | EVD-011 | Internal auditor |
| G11 | Competence requirements and records for ISMS roles | MS1-07; F6 | **RA-06** | HR Manager | 31 Jan 2028 | Open | EVD-015 | Internal auditor |
| G12 | Fix KPI validation; re-calculate KPI-14, 18 and 20 from source | MS1-05 | **RA-07** | GRC Analyst (owner of 041) | 31 Dec 2027 | Open | EVD-019 | **Internal auditor** (the GRC Analyst owns the process being fixed) |
| G13 | Annual full restore test | MS1-09; F7 | 015 **T-14.3**; test **BRT-01** (054) | IT Manager | BRT-01 held 12 Oct 2027; report due 19 Oct 2027 | In progress: **report not yet received** | EVD-034 | GRC Analyst (evidence review); Head of Engineering (sign-off) |
| G14 | Regional failover test | F7 | 015 **T-09.2** | Head of Engineering | Was 1 Mar 2027; **new date needed** | **Overdue** | EVD-035 | Internal auditor |
| G15 | Backups held in the same region as the source | BIA G2 | 014 risk review of **R-09, R-14** | Head of Engineering | Decision by 30 Nov 2027 | Open | EVD-033, 035 | Steering Group |
| G16 | Incident response exercise | 5.24; F7 | 015 **T-18.1**; exercise **EX-01** (053), 8 Dec 2027 | GRC Analyst | Was 1 Mar 2027 | **Overdue** (EX-01 scheduled) | EVD-035, 037 | Internal auditor or MD |
| G17 | Critical supplier assessments | F8 | 058 §2 | GRC Analyst | 17 Dec 2027 | Open | EVD-038 | Internal auditor |
| G18 | Confirm sub-processors; notify customers if any are unlisted | 060 §4 | 060 §4 (NSD-ISMS-034 if confirmed) | Data Protection lead | 29 Oct 2027 | Open | EVD-038 | GRC Analyst |
| G19 | Restrict MSP administrator access until assessed | 060 §4 | 015, under R-16 | IT Manager | 15 Oct 2027 | **Overdue** (no record) | EVD-027 | GRC Analyst |
| G20 | Leaver controls: RCA-01 result and CA-01 effectiveness | 066; 067 T05 | 034 **CA-01**; 048 **RCA-01** | HR Manager | RCA analysis was due 5 Oct 2027 | **Overdue** (no result recorded) | EVD-026 | Lead auditor |
| G21 | Access reviews effective | KPI-02 Red twice | 034 **CA-02** | HR Manager | As in 034 | Open | EVD-025 | Lead auditor |
| G22 | Overdue risk treatment actions generally | KPI-17 Red (70%) | 015 | Risk owners | As in 015 | Open | EVD-009 | GRC Analyst, monthly |
| G23 | Capacity: a named third person; auditor engagement | F10; MS1-12 | 039 **MRA-2027-05, 06** (proposed: need G02 decisions) | MD | 31 Dec 2027 | Open | EVD-014 | Steering Group |
| G24 | CRM missing from the asset register | 055 gap 3 | 006 | Sales lead | 29 Oct 2027 | Open | EVD-024 | GRC Analyst |

### Opportunities for improvement

| # | Gap | Source | Home | Owner | Due | Status |
| --- | --- | --- | --- | --- | --- | --- |
| G25 | ISMS communication statement | MS1-10 | **RA-08** | GRC Analyst | 31 Jan 2028 | Open |
| G26 | Contingency in the readiness timeline | MS1-12 | 065 §5 revision | GRC Analyst | 15 Nov 2027 | Open |

### Readiness milestones

| # | Milestone | Owner | Target | Depends on |
| --- | --- | --- | --- | --- |
| M1 | Second mock Stage 1 | Lead auditor | Feb 2028 | G01–G07 |
| M2 | External Stage 1 booked | MD | After M1 passes | M1 |
| M3 | Mock Stage 2 (067) | Lead auditor | May 2028 | G08–G24 |
| M4 | External Stage 2 booked | MD | After M3 | M3; no open Major |

## 3. New remediation actions (homed here)

| ID | Action | Why it has no other home |
| --- | --- | --- |
| RA-01 | MD approval of scope, policy, objectives and risk criteria | An approval decision, not a corrective or treatment action |
| RA-02 | Hold and minute the first management review | The review itself; its decisions then become MRA actions in 039 |
| RA-03 | SoA Wave 2, owner confirmations, single owners, approval | Completion of an ISMS document |
| RA-04 | Investigate KPI-20: what did staff acknowledge? | If it shows a requirement was not met, it moves to 034 as a nonconformity |
| RA-05 | Reschedule the audit programme | A programme decision by the audit sponsor |
| RA-06 | Competence requirements and records | No existing action covers 7.2 |
| RA-07 | KPI validation fix and re-calculation | Found by the mock Stage 1; may become a 034 nonconformity if confirmed at audit |
| RA-08 | Communication statement | Improvement |

If investigation shows that an RA item is a nonconformity, it moves to NSD-ISMS-034 and the RA entry closes with a cross-reference. The same rule as the improvement register (047 §6).

## 4. Closure

The draft's five closure criteria are kept:

1. The action is complete.
2. Evidence has been obtained and reviewed.
3. The evidence meets the requirement.
4. Any effectiveness check is complete.
5. An authorised reviewer has accepted closure.

Two rules are added. **The verifier is never the owner,** and where the GRC Analyst owns the action, the internal auditor or the MD verifies (G12, G16). **An item closes in its home register first;** this tracker then reflects that status and never closes an item on its own authority.

## 5. Escalation and reporting

| Report | To | When |
| --- | --- | --- |
| Status of all items; Overdue items; items blocked by another | Steering Group | Monthly |
| Overdue Stage 1 blockers | MD | Immediately, and at every Steering Group |
| Overdue more than 30 days | MD | As NSD-ISMS-046 §9 |
| Summary of readiness and progress | Management review, input 9.3.2(c) | Each review |

The GRC Analyst co-ordinates and reports. **It does not accept risk on behalf of management:** a gap that cannot be closed in time is decided by the MD, under NSD-ISMS-016 where it involves accepting risk.

**Position at 15 Oct 2027:** 26 gaps, 8 new remediation actions. **6 overdue:** the management review, SoA Wave 2, the failover test, the incident exercise, the MSP access restriction and the RCA-01 result. **One in progress:** the restore test, with its report due 19 Oct. **None closed.**

## 6. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-064) | 18 CR actions, all "Open" with targets "to agree"; closure criteria; escalation; reporting |
| 0.2 | Numbered NSD-ISMS-068. **Points to existing registers** instead of creating duplicate actions; only 8 gaps with no other home become new actions (RA-01 to RA-08). Gaps taken from 061–067, grouped by whether they block Stage 1 or Stage 2. Owners changed to charter roles ("Senior Management", "Security Lead", "Procurement", "Internal Audit Lead" and "Mock Audit Lead" removed). Dates set, with **Overdue** shown where a due date has passed with no record. The draft's "conduct internal audit" and "conduct management review" replaced: one audit exists, so the gap is the other eight; no review is recorded, so the first review is now an overdue Stage 1 blocker. Mock Stage 1 shown as held (baseline), with a second mock as a milestone. Verifier and closure evidence for every gap. |

---

*Portfolio disclaimer: Simulated tracker. All entries are planning items for a fictional organisation; no action is represented as complete.*
