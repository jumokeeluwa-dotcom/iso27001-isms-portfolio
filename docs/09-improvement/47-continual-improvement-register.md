# Northstar Digital Solutions Ltd — Continual Improvement Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-047 |
| Version | 0.2 — Simulated records |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 6.3, 9.3.2(g), 10.1) |
| Status | **Simulated. All entries are fictional training examples, not actual findings or approved management actions** |
| Position as at | 30 September 2027 |
| Procedure | [NSD-ISMS-045 Continual Improvement Procedure](45-continual-improvement-procedure.md): triage, prioritisation, approval, verification |
| Related registers | [NSD-ISMS-034 Corrective Action Register](../06-internal-audit/34-corrective-action-register.md) (nonconformities) · [NSD-ISMS-015 Risk Treatment Plan](../03-risk-management/15-risk-treatment-plan.md) (risk treatment) · [NSD-ISMS-039 Management Review Actions](../07-management-review/39-management-review-actions-register.md) (review decisions) |
| Register owner | Information Security / GRC Analyst |
| Classification | Confidential (records showing weaknesses, NSD-ISMS-045 §10) |

---

## 1. What belongs in this register

This register tracks **improvements only:** ways to do better where every requirement is already met. Each item is triaged first (NSD-ISMS-045 §2), so it is tracked in one register only:

| Triage result | Where it is tracked |
| --- | --- |
| A requirement is not met (ISO/IEC 27001, a policy, a contract, the law) | Nonconformity: NSD-ISMS-034 |
| A risk is above its target and a treatment action is planned | Risk treatment: NSD-ISMS-015 |
| Already decided at management review | NSD-ISMS-039 |
| None of these: a way to do better | **Improvement: this register** |

An improvement register that lists unresolved nonconformities makes them look optional. That is the main thing triage prevents.

## 2. Improvement register

| ID | Opportunity | Source | Raised | Owner | Mandatory / Benefit / Effort | Priority | Approver | Success measure | Target | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| IMP-01 | Use PIM access review records as the single source for privileged account review dates, and remove the "last reviewed" column from the spreadsheet inventory, so the two records cannot disagree | AUD03-F03 (Observation, NSD-ISMS-033) | 16 Jun 2027 | IT Manager | No / Medium (R-13; KPI-04 already Green) / Low | P2 | IT Manager (within one team, no spend) | At the next AUD-03, every privileged account has a review date in PIM, and no second inventory holds review dates | Next AUD-03 (cycle 2) | Approved; implementation to be evidenced |
| IMP-02 | Add more detail to risk treatment progress reporting | GRC Analyst proposal, linked to KPI-17 Red (NSD-ISMS-044) | 30 Sep 2027 | GRC Analyst | No / Low / Low | — | Steering Group | — | — | **Declined:** KPI-17 already reports progress monthly, and it shows the cause: lack of DevOps and IT capacity. More reporting would not move the KPI. The capacity gap is the subject of decision D-04, **proposed** for management review (NSD-ISMS-037; actions MRA-2027-05, 06 in 039 are proposals) |
| IMP-03 | Quarterly incident trend summary (by category, root cause and affected risk) as an input to management review 9.3.2(c) | GRC Analyst proposal (NSD-ISMS-027 §10, lessons learned) | 30 Sep 2027 | GRC Analyst | No / Low / Low | P3 | Steering Group (changes an ISMS input) | Summary presented at MR-2028-01, with each recurring cause linked to a risk or corrective action | MR-2028-01 | Proposed: for Steering Group decision |

**Verification:** IMP-01 is verified by the internal auditor at the next AUD-03. IMP-03 is owned by the GRC Analyst, so the internal auditor verifies it as well (NSD-ISMS-045 §4, step 8).

## 3. Items raised but tracked elsewhere

These were proposed as improvements during register set-up on 30 September 2027. Triage shows each is a nonconformity, a possible nonconformity, or already decided. **They are not tracked here,** so no owner, priority or status is recorded in this register.

| Proposed item | Triage result | Tracked in |
| --- | --- | --- |
| Leaver access removal evidence and reconciliation | **Nonconformity:** AUD03-F01. A second late contractor in August (KPI-01) is under root cause analysis | NSD-ISMS-034 CA-01; NSD-ISMS-048 RCA-01; NSD-ISMS-015 T-12.x |
| Scheduled access reviews for critical systems | **Nonconformity:** AUD03-F02. KPI-02 Red for a second period shows the fix is not yet working | NSD-ISMS-034 CA-02 |
| Backup restore testing documentation | **Possible nonconformity:** KPI-09 Red, one restore test with no record (NSD-ISMS-028 requires the test). Assessment by the IT Manager was due 14 Sep 2027; **the outcome is not yet recorded**, so the item stays open in the dashboard | NSD-ISMS-044 §5; NSD-ISMS-034 if confirmed |
| Supplier security review frequency | **Possible nonconformity:** KPI-14 Red, one Critical supplier not assessed within 12 months (NSD-ISMS-026 §7). Changing the frequency is not an improvement while the current frequency is not met | NSD-ISMS-044 §5 (Finance Manager); NSD-ISMS-034 if confirmed |
| Security awareness training and assessment | **Proposed for management review:** D-07 | NSD-ISMS-039 MRA-2027-04 (HR Manager), proposed |
| Vulnerability remediation reporting | **Pending:** KPI-05 Amber, one critical fixed in 17 days against the 14-day deadline (NSD-ISMS-029 §4). If no exception was documented and risk-assessed, it is a nonconformity; if one was, the policy was followed | NSD-ISMS-044 (Head of Engineering); NSD-ISMS-034 if confirmed |

## 4. Fields for each entry

The table in section 2 shows the summary. The full record for each IMP holds:

| Field | Notes |
| --- | --- |
| ID, date raised, raised by | The person who raised it is told the outcome (NSD-ISMS-045 §3) |
| Source | A specific record: a finding, KPI, incident, review decision or named proposal. **No entry without a traceable source** |
| Description and expected benefit | Which risk, control, KPI or objective it improves |
| Triage result | Confirms that no requirement is unmet |
| Mandatory, benefit, effort | Rated using NSD-ISMS-045 §5 |
| Priority | P1, P2, P3 or Declined, from the §5 table, not chosen freely |
| Owner | **One** accountable owner. Contributors are named separately |
| Approver and approval date | At the level in NSD-ISMS-045 §6 |
| Resources | Person-days and spend |
| ISMS change? | If yes, the clause 6.3 change record (NSD-ISMS-045 §7) and the documents updated |
| Success measure and target date | The result expected, not the task |
| Implementation status and evidence | |
| Effectiveness result | The success measure met or not, with evidence; verifier and date |
| Closure date, or Declined with the reason | |

## 5. Status values

| Status | Meaning |
| --- | --- |
| Proposed | Recorded and triaged; awaiting approval |
| Approved | Owner, success measure and date agreed |
| In progress | Work started |
| Implemented | Work done; verification not yet passed |
| Closed: effective | Success measure met and verified |
| Reopened | Success measure not met; see NSD-ISMS-045 §8 |
| Declined | Not taken forward, with the reason recorded |

"Implemented" is never reported as "Closed".

## 6. Review and reporting

| Activity | Who | When |
| --- | --- | --- |
| Triage and record new items | GRC Analyst | Within 5 working days of being raised |
| Review the register: overdue items, missing evidence, items whose triage has changed | GRC Analyst | Monthly, before the Steering Group |
| Report open items by priority; overdue P1 items; implemented vs verified | GRC Analyst | Steering Group, monthly |
| Escalate overdue P1 items | GRC Analyst | Steering Group; MD after 30 days |
| Summary of improvements and their effect on risks and KPIs | GRC Analyst | Management review, input 9.3.2(g) |

If an improvement turns out to involve an unmet requirement, it is moved to NSD-ISMS-034 and the IMP entry is closed with a cross-reference.

## 7. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| ISMS Steering Group | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-043) | First draft: eight proposed improvements |
| 0.2 | Numbered NSD-ISMS-047; IDs aligned with NSD-ISMS-045 (IMP-nn). **IMP-01 moved here from NSD-ISMS-034 §5.** The draft's eight items triaged: **six belong elsewhere** (two open nonconformities, three possible nonconformities, one management review decision) and are listed in section 3 with pointers, not tracked twice; one (risk treatment reporting) recorded as **Declined** with the reason; one (incident trends) kept as IMP-03, P3. Roles changed to charter roles: "Procurement Manager" and "Security Lead" removed; joint owners replaced by one owner. High/Medium/Low replaced by the NSD-ISMS-045 §5 priority method. Added a success measure per item, status values, and a monthly review in place of "periodically". |

---

*Portfolio disclaimer: Simulated register only. The entries are fictional training examples, not actual findings or approved management actions.*
