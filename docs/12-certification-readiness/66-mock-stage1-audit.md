# Northstar Digital Solutions Ltd — Mock Stage 1 Audit: Plan and Report

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-066 (mock audit MS1-01) |
| Version | 1.0 — Simulated audit |
| Standard | ISO/IEC 27001:2022 incl. Amendment 1:2024, clauses 4–10 and the SoA |
| Status | **Training exercise. No certification audit took place. Findings rest only on portfolio records; no finding is invented** |
| Type | **Baseline** mock Stage 1, to test the readiness report (065) independently. A second mock Stage 1 follows in Feb 2028, before any external audit is booked |
| Dates | Thursday 14 and Friday 15 October 2027 (records as at 30 Sep 2027) |
| Lead auditor | External internal auditor (SUP-13; NSD-ISMS-030): ISO/IEC 27001 Lead Auditor qualification |
| Audit sponsor | Managing Director |
| Classification | Confidential |

---

## 1. Why a mock Stage 1, and why now

At Stage 1, a certification body checks that the documented ISMS exists and decides whether the organisation is ready for Stage 2. It reviews the scope, the understanding of the organisation and its requirements, the risk assessment, the SoA, the objectives, and the internal audit and management review arrangements. The certification body sets its own programme; this mock follows the same pattern.

Holding it **now** gives an independent check of the GRC Analyst's own conclusions (061–065). The GRC Analyst built the ISMS, so they cannot be the one to confirm it is ready.

**Independence statement.** The lead auditor confirms they did not design or operate any part of the ISMS. They conducted AUD-03 (identity and access management) in June 2027 as the external internal auditor. That was an audit, not design work, so it does not affect their independence here. They report to the MD, not to the GRC Analyst (030).

## 2. Objectives and criteria

**Objectives:**

1. Confirm the scope, boundaries and locations.
2. Review the context, interested parties and legal and contractual requirements.
3. Examine the risk criteria, risk assessment and treatment.
4. Review the SoA, **re-performing a sample of the 063 validation checks.**
5. Review the objectives, internal audit and management review arrangements.
6. Decide whether the ISMS is ready for Stage 2.
7. Test whether the readiness report (065) is accurate.

**Criteria:** ISO/IEC 27001:2022 clauses 4–10 and the SoA; Northstar's own policies and procedures; its risk methodology (012, 013, 016).

**Not in scope:** testing whether controls operate effectively. That is Stage 2 (NSD-ISMS-067). Control evidence is looked at here only to judge whether Stage 2 can be planned.

## 3. Plan

| Time | Activity | Auditees | Records examined |
| --- | --- | --- | --- |
| **Day 1** 09:00 | Opening meeting: scope, method, confidentiality | MD; GRC Analyst | — |
| 09:30 | Context, interested parties, legal requirements | GRC Analyst; Data Protection lead | 002, 003, 005 (requested) |
| 10:30 | Scope and boundaries; head office visit (A 7.4) | MD; IT Manager | 004; office walk-round |
| 11:30 | Leadership, policy, roles, objectives | MD | Charter; 022; 007; 042 |
| 13:30 | Risk criteria, assessment and treatment | GRC Analyst; two risk owners (HR Manager, Head of Engineering) | 012–017 |
| 15:00 | SoA: re-perform 063 checks 2, 7 and 8 on a sample | GRC Analyst; IT Manager | 018, 019, 020, 063 |
| **Day 2** 09:00 | Support: competence, awareness, communication, document control | HR Manager; GRC Analyst | 7.2–7.5 records; KPI-10, KPI-20 sources |
| 10:00 | Performance: KPIs, internal audit programme, management review | GRC Analyst; MD | 041–044; 030–035; 036–040 |
| 11:00 | Improvement and corrective action | GRC Analyst; HR Manager | 034, 046–048 |
| 11:45 | Auditor review of findings | Lead auditor alone | — |
| 12:30 | Closing meeting | MD; all owners | Findings |

## 4. Strengths

Recorded so that management knows what to keep doing, not as padding.

- **The AUD-03 audit** tested whole populations, used a reverse test for orphan accounts, and graded findings with evidence.
- **Management review is well prepared:** the agenda maps every 9.3.2 input to a source (037), and decisions needed are identified in advance.
- **The KPI dashboard does not count "no events" as success** and investigates Red results.
- **Corrective action finds root causes** beyond "human error", and RCA-01 was opened on a **repeat**, as the procedure requires.
- **The SoA method is sound:** controls are derived from risk treatment and compared with Annex A; applicability is Yes or No only; statuses rest on evidence.
- **Honest reporting:** the supplier KPI was reset from 80% to 0 of 7 when records could not be found (060), rather than kept.

## 5. Findings

Stage 1 findings are not graded as nonconformities. They are classed by what they would mean at Stage 2:

| Class | Meaning |
| --- | --- |
| **Blocker** | Stage 2 cannot be planned until resolved; **likely a Major nonconformity** if found at Stage 2 |
| **Concern** | Must be addressed before Stage 2; **likely a Minor nonconformity** if found then |
| **OFI** | Opportunity for improvement |

| Ref | Class | Clause | Finding | Evidence |
| --- | --- | --- | --- | --- |
| MS1-01 | **Blocker** | 4.3, 5.2, 6.1.2(a), 6.2 | Scope, policy, objectives and risk acceptance criteria are **not approved.** Charter Obj 1 required approval by month 2 | 004 v1.0; 022; 016 Part A; charter §2 |
| MS1-02 | **Blocker** | 6.1.3(b)–(d) | The SoA covers **48 of 93 controls,** is unapproved, and its statuses date from Dec 2026. **Re-performed:** 063 checks 2 and 7 confirmed; 4 of the 7 status differences confirmed by sampling AUD-03, KPI-07 and CA-03 | 019 v1.0; 063 |
| MS1-03 | **Blocker** | 9.2(b) | The programme planned **9 audits** for June–August 2027; **only AUD-03 has records.** There is no record of a decision to postpone the others, and the programme has not been rescheduled | 030; 031–035 |
| MS1-04 | Concern | 5.2, 7.5 | **93% of staff acknowledged a policy that has no approval record** (KPI-20). No record shows which version was acknowledged | 044; 022 |
| MS1-05 | Concern | 9.1 | **KPI validation did not detect unsupported results.** Three examples: KPI-14 (Q2) is marked "validated against the supplier register", but no assessment records exist and the register was built in Q3; KPI-20 counts acknowledgement of an unapproved policy; KPI-18 reports "0 Very High risks beyond tolerance", but the interim tolerances it measures against are **not approved** (016 §8). The Stage 2 auditor will re-test KPI sources rather than rely on the dashboard. *(Not found by 061–065)* | 044; 058; 016 |
| MS1-06 | Concern | 4.2, 6.1.3, A 5.31 | **No legal register.** Contractual requirements such as SLAs and DORA terms cannot be confirmed, so the SoA cannot be shown to cover them | 005 missing; MRA-2027-02 |
| MS1-07 | Concern | 7.2 | No competence requirements or records for ISMS roles | 064 EVD-015 |
| MS1-08 | Concern | 6.1.3(f), 8.3 | **No residual risk accepted or tolerated with approval,** including the 4 Very High risks (R-06, R-12, R-14, R-19) | 016 §8 |
| MS1-09 | Concern | 8.1; A 5.30, 8.13 | Recovery for Very High risk R-14 untested: restore test report missing, failover not tested, KPI-09 Red. **Flagged for Stage 2 sampling** | 054; 064 EVD-034 |
| MS1-10 | OFI | 7.4 | No ISMS communication statement; communication defined only for incidents and continuity | 027; 050 |
| MS1-11 | OFI | 5.3 | Five SoA controls have two owners. **Re-performed:** 063 check 8 confirmed | 019 |
| MS1-12 | OFI | 6.2, 7.1 | The 065 timeline puts **8 internal audits** in Jan–Apr 2028 with no contingency, although KPI-17 (Red) shows capacity already limits delivery | 065 §5; KPI-17 |
| MS1-13 | **Blocker** | 5.1, 9.3 | **No management review recorded.** MR-2027-01 was planned for 22 Sep 2027 with a full agenda (037), but the minutes and summary are blank (038, 040) and the actions are hypothetical (039). Top management's review of the ISMS cannot be shown | 037–040 |

**Re-performance result.** All three 063 checks sampled (2, 7, 8) were confirmed. The GRC Analyst's validation is reliable. One weakness was missed: KPI data validity (MS1-05).

## 6. Conclusion

**Not ready for Stage 2.** Four blockers (MS1-01 to MS1-03 and MS1-13) would each stop a certification body from planning Stage 2. The lead auditor **agrees with the readiness report (065),** with two additions: the KPI validation weakness (MS1-05), and the risk to the timeline (MS1-12).

A real certification body makes its own decision under its own programme. The mock indicates that if Northstar booked an external Stage 1 now, it would very likely end with Stage 2 not being scheduled.

## 7. Management response

| Step | Who | When |
| --- | --- | --- |
| Response to each finding: accepted, with owner and date, or disputed with evidence | MD, with finding owners | Within 10 working days (29 Oct 2027) |
| Findings entered in the remediation tracker, pointing to existing actions where they exist | GRC Analyst | With the response |
| Second mock Stage 1, to confirm the blockers are closed | Lead auditor | Feb 2028 (065 §5) |

| Finding | Response | Owner | Date |
| --- | --- | --- | --- |
| MS1-01 to MS1-13 | Pending | | |

---

*Portfolio disclaimer: Simulated training exercise. No certification audit occurred, and no certification body decision is represented.*
