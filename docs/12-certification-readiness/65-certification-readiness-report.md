# Northstar Digital Solutions Ltd — ISO/IEC 27001 Certification Readiness Report

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-065 |
| Version | 0.3 — Simulated report for MD decision |
| Standard | ISO/IEC 27001:2022 incl. Amendment 1:2024 |
| Status | **Simulated internal readiness report, not an external audit report. Every finding is drawn from portfolio records** |
| Evidence as at | 30 September 2027 |
| Based on | [061 Clause gap assessment](61-clause-gap-assessment.md) · [062 Annex A readiness](62-annex-a-control-readiness-review.md) · [063 SoA validation](63-soa-validation.md) · [064 Evidence index](64-audit-evidence-index.md) |
| Prepared by | Information Security / GRC Analyst |
| Independent check | Mock Stage 1 audit (NSD-ISMS-066) |
| For decision by | Managing Director |
| Classification | Confidential |

---

## 1. Summary

**Decision recommended: Northstar is not ready for a Stage 1 audit. It should not book one until the six Stage 1 entry criteria in section 4 are met.**

The draft concluded that Northstar is "at the documentation design stage". That understates it. The portfolio shows parts of the ISMS **operating**:

- an internal audit (AUD-03) with graded findings;
- a validated monthly KPI dashboard;
- corrective actions with root cause analysis, including a repeat-nonconformity investigation (RCA-01).

The ISMS is **designed, partly operating, and almost entirely unapproved.** Top management has **not yet held a recorded management review.** The blockers are mainly approvals and incomplete core documents, which are within management's control. The Stage 2 blockers (audits not done, controls not tested) need time and people.

| Measure | Result | Source |
| --- | --- | --- |
| Clauses 4–10 ready | **0 of 25** (16 partly ready, 9 not ready) | 061 |
| Annex A controls ready | **0 of 93** (29 partly ready, 64 not ready) | 062 |
| SoA validation checks passed | **2 of 12** (4 partial, 5 failed, 1 not yet testable) | 063 |
| Evidence items available | **13 of 38** (4 draft, 12 partial, 9 missing) | 064 |

## 2. Position by area

| Area | Position | Evidence | Rating |
| --- | --- | --- | --- |
| Scope and governance | Scope, policy and objectives drafted; **none approved;** charter Obj 1 (approval by month 2) missed. Policy acknowledgement (KPI-20) conflicts with the missing approval | 061: 4.3, 5.2 | 🟥 |
| Risk assessment and treatment | 20 risks assessed and treated; **criteria unapproved, so scores are provisional;** R-21 not added; no residual risk accepted; KPI-17 70% on time | 061: 6.1.2, 6.1.3, 8.3 | 🟥 |
| Statement of Applicability | Risk-driven method sound; **45 of 93 controls unassessed** (overdue since Jan 2027); statuses not revalidated; unapproved | 063 | 🟥 |
| Control operation | Strong evidence for change approval, privileged access and IAM testing; **none for recovery, failover, incident exercise or supplier assurance** | 062 | 🟧 |
| Competence and awareness | Training 91.8% and phishing reports measured; **no competence records** for ISMS roles | 061: 7.2, 7.3 | 🟧 |
| Suppliers | Process designed (055–059); **no assessment records** for any of 7 Critical suppliers | 058, 060 | 🟥 |
| Internal audit | AUD-03 completed and reported; **8 of 9 planned audits have no records** | 064: EVD-020 | 🟧 |
| Management review | Agenda and inputs prepared for MR-2027-01 (037); **no minutes, decisions or actions recorded** (038, 040 blank; 039 hypothetical) | 064: EVD-021 | 🟥 |
| Performance evaluation | 21 KPIs measured and validated; "no events" not counted as success | 044 | 🟩 |
| Corrective action | Root cause analysis and effectiveness checks working; **CA-02 not effective; RCA-01 open** | 034, 048 | 🟧 |
| Business continuity | BIA, plans and recovery objectives drafted; **no recovery test passed; backups held in the same region** | 049–054 | 🟥 |
| Legal requirements | **Legal register not written** | 061: 4.2; 062: 5.31 | 🟥 |

The draft rated internal audit, management review and performance evaluation as "not demonstrated". Records exist for internal audit (AUD-03) and performance evaluation, so they are credited; performance evaluation is the strongest area. **The draft was right about management review:** no review is recorded.

## 3. Findings

The draft listed risks as possibilities ("may not have been formally authorised"). The assessments have now tested them, so they are stated as findings.

| # | Finding | Effect at audit | Source |
| --- | --- | --- | --- |
| F1 | Scope, policy, risk criteria, objectives and SoA are not approved | Stage 1 cannot proceed: the auditor has no approved ISMS to examine | 061 |
| F2 | Staff acknowledged a policy that has no approval record (KPI-20: 93%) | Auditor will ask what was acknowledged; damages confidence in document control | 061 gap 2 |
| F3 | 45 Annex A controls not assessed | SoA incomplete; likely **Major** nonconformity against 6.1.3 | 063 |
| F4 | No legal register | Requirements in 4.2 and control 5.31 cannot be shown | 061, 062 |
| F5 | 8 of 9 planned internal audits have no records | 9.2 not met across the scope; likely **Major** at Stage 2 | 064 |
| F6 | No competence records for ISMS roles | 7.2 not met | 061 |
| F7 | No recovery capability demonstrated: no failover test, restore test report missing, KPI-09 Red | Very High risk R-14 untreated in practice; 5.30 and 8.14 not evidenced | 062, 064 |
| F8 | No supplier assessment records; earlier KPI not traceable | 5.19–5.22 not evidenced; 8.1 outsourced processes not controlled | 058 |
| F9 | Corrective actions not yet effective (CA-02; RCA-01 on a repeat) | 10.2(d) effectiveness not shown | 034, 048 |
| F10 | Capacity: risk actions running late (KPI-17), two people carry most ownership | Every other finding depends on this being solved | KPI-17; D-04 proposed |
| F11 | **No management review recorded.** MR-2027-01 has an agenda but no minutes or decisions | 5.1 and 9.3 cannot be shown; likely **Major** at Stage 2 | 061; 064 EVD-021 |

## 4. Readiness criteria

Certification bodies use Stage 1 to check that the documented ISMS exists and is ready, and Stage 2 to check that it works. Northstar sets these entry criteria for itself. The chosen certification body's own requirements must also be checked.

**Stage 1 entry criteria**

| # | Criterion | Met? | Linked finding |
| --- | --- | --- | --- |
| S1-1 | Scope, policy, objectives and risk criteria approved by the MD | No | F1 |
| S1-2 | Risk assessment final (approved criteria; R-21 added) and treatment plan approved | No | F1 |
| S1-3 | SoA complete for all 93 controls, validated and approved | No | F3 |
| S1-4 | Legal register approved | No | F4 |
| S1-5 | KPI-20 conflict resolved; document control applied to all ISMS documents | No | F2 |
| S1-6 | Internal audit programme rescheduled with dates; at least one management review held and minuted | No | F5, F11 |

**Stage 2 entry criteria**

| # | Criterion | Met? | Linked finding |
| --- | --- | --- | --- |
| S2-1 | Full internal audit cycle complete across the scope, with findings graded | No (1 of 9) | F5 |
| S2-2 | A management review held **after** that cycle, using its results | No | — |
| S2-3 | No open Major nonconformity; Minors with accepted action plans | Partly: none open, but F3 and F5 would likely be Major | F3, F5 |
| S2-4 | Key controls for Very High risks evidenced: restore test passed (BRT-01), incident exercise held (EX-01), leaver controls effective (RCA-01 closed) | No | F7, F9 |
| S2-5 | Critical supplier assessments recorded | No | F8 |
| S2-6 | Competence records for ISMS roles | No | F6 |
| S2-7 | Evidence index complete for every applicable control, with records from the last 12 months | No (16 of 38 available) | All |

## 5. Indicative timeline

For the MD's decision. **Achievable only if the capacity gap (F10) is resolved;** the dates assume the resourcing **proposed** under D-04 is decided and in place.

| Step | Target |
| --- | --- |
| **First management review** (MR-2027-01, rescheduled), including MD approvals of scope, policy, objectives and risk criteria (S1-1, S1-6) and decisions D-01 to D-08 | 30 Nov 2027 |
| Recovery test BRT-01; incident exercise EX-01; Critical supplier assessments | Oct–Dec 2027 (already planned) |
| Legal register; SoA Wave 2 complete and approved (S1-2 to S1-5) | 31 Jan 2028 |
| **Mock Stage 1 (NSD-ISMS-066)** to confirm Stage 1 readiness | Feb 2028 |
| **External Stage 1** | March 2028, at the earliest |
| Internal audit cycle completed (AUD-01, 02, 04–09) | Jan–Apr 2028 |
| Management review after the audit cycle | May 2028 |
| **Mock Stage 2 (NSD-ISMS-067)** | May 2028 |
| **External Stage 2** | June 2028, at the earliest |

## 6. Decisions requested

| # | Decision | Recommendation |
| --- | --- | --- |
| 1 | Accept the conclusion: not ready for Stage 1 | Accept |
| 2 | Do not book external Stage 1 until all six Stage 1 criteria are met, confirmed by the mock Stage 1 | Agree |
| 3 | Approve the timeline in section 5 as the target | Approve, **with the resources it needs** (proposed decision D-04) |
| 4 | Hold the first management review, with approval of the core documents (S1-1, S1-6) | Before 30 Nov 2027 |
| 5 | Commission the external internal auditor for the remaining 8 audits | Approve |

## 7. Actions

The draft listed ten actions (CR-001 to CR-010) with their own IDs. Most already exist in other registers: SoA Wave 2, the legal register (MRA-2027-02), CA-02, RCA-01, BRT-01, EX-01, supplier assessments. Giving them new IDs here would put the same work in two places. **All actions are tracked in the remediation tracker, NSD-ISMS-068,** which points to the register where each one lives and adds only the actions that are genuinely new (for example, the competence records and the KPI-20 investigation).

## 8. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-061) | Summary, eleven areas, seven possible risks, ten actions, readiness decision pending |
| 0.3 | **Correction:** v0.2 treated management review MR-2027-01 as held. It is planned but unrecorded (037; 038 and 040 blank; 039 hypothetical). Headline measures updated; management review rated Red; finding F11 added; S1-6 not met; the first management review added to the timeline. |
| 0.2 | Numbered NSD-ISMS-065. **Conclusion made definite:** not ready for Stage 1, with reasons, rather than "pending". Positions credit the operating evidence in the portfolio (internal audit, management review, KPIs, corrective action), which the draft called "not demonstrated". Headline measures from 061–064. Possible risks replaced with ten tested findings, including the KPI-20 conflict, the 8 audits without records, and capacity. **Stage 1 and Stage 2 entry criteria** added, with an indicative timeline conditional on resourcing, and five decisions for the MD. Actions moved to NSD-ISMS-068 instead of being given new IDs here. Roles changed to charter roles ("Senior Management", "Procurement", "Internal Audit Lead" removed). |

---

*Portfolio disclaimer: Simulated readiness report. It is not an external audit report, and no real management decision is represented.*
