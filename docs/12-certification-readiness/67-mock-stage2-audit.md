# Northstar Digital Solutions Ltd — Mock Stage 2 Audit: Plan and Test Programme

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-067 (mock audit MS2-01) |
| Version | 0.3 — Plan and test programme |
| Standard | ISO/IEC 27001:2022 incl. Amendment 1:2024, clauses 4–10 and applicable Annex A controls |
| Status | **Training exercise. The audit has not been held. No result in this document is an audit result.** Section 6 shows only how **existing** portfolio records would be judged, to illustrate the grading |
| Planned | May 2028 (NSD-ISMS-065 §5), **only if the entry conditions in section 2 are met** |
| Lead auditor | External internal auditor (SUP-13): the same independence as the mock Stage 1 (066 §1) |
| Audit sponsor | Managing Director |
| Classification | Confidential |

---

## 1. Objective

To find out whether the ISMS is **implemented and operating effectively** across the approved scope, and conforms to ISO/IEC 27001:2022. Stage 1 asked whether the ISMS is designed and ready. Stage 2 asks whether it works, using interviews, observation, sampled records and re-performed tests.

A mock auditor does not declare Northstar certified and does not speak for a certification body. The certification decision belongs to the certification body alone.

## 2. Entry conditions

Holding a Stage 2 mock before these are met would only confirm what is already known.

| # | Condition | Source |
| --- | --- | --- |
| 1 | Second mock Stage 1 (Feb 2028) closes blockers MS1-01 to MS1-03 and MS1-13 | 066 §7 |
| 2 | Stage 2 entry criteria S2-1 to S2-7 met, or any exception recorded and accepted by the MD | 065 §4 |
| 3 | Approved SoA version identified; the audit tests **that** version | 063 §5 |
| 4 | Evidence index (064) updated, with records from the last 12 months | 064 |
| 5 | Audit plan sent **2 weeks before** the audit, with the samples requested | 030 §9 |

If a condition is not met, the MD decides whether to postpone. The decision is recorded.

## 3. How the auditor tests

| Rule | Detail | Source |
| --- | --- | --- |
| **Populations from the system of record** | Leavers from the HR system, accounts from Entra ID, deployments from the CI/CD platform. Never a list prepared by the auditee | 064 §5 |
| **Sample sizes** | By how often the control runs: annual 1; quarterly 2; monthly 2–3; weekly 5; daily 20–25; per event 25, **or all if the population is under 25.** The method is recorded | 021 §4.3 |
| **Reverse test** | Start from what exists and look for its authorisation: active accounts with no current HR record, guest accounts with no registered supplier | AUD-03 test IAM-02 (031) |
| **Re-perform, don't just inspect** | Re-calculate KPIs from source; re-run a reconciliation | 030 §7 |
| **Trace end to end** | Risk → control → evidence → residual risk decision | — |
| **12-month window** | Evidence older than 12 months gets no credit | 062 §6 |
| **"No events" is not evidence** | Readiness is tested through exercises and tests | 062 §6 |

**Grading** (030 §8): **Major:** a requirement not met at all, or a systemic failure putting ISMS outcomes at risk. **Minor:** a single or isolated lapse. **Observation**, and **OFI** (opportunity for improvement). Each finding records the requirement, the objective evidence, the condition, the sample and its limits, and the grade.

## 4. Test programme

Areas are chosen by risk: every Very High risk (R-06, R-12, R-14, R-19) is traced, and every mock Stage 1 concern is followed up.

| # | Area | Test | Population and sample | Evidence (064) | Follow-up of |
| --- | --- | --- | --- | --- | --- |
| T01 | Leadership | Interview the MD: trace objectives and resource decisions to results | Management review minutes and decisions | EVD-004, 012, 014 | MS1-01, MS1-12, MS1-13 |
| T02 | Risk | Trace each **Very High** risk to its controls, evidence and the MD's tolerance or acceptance decision | All 4 | EVD-007 to 011 | MS1-08 |
| T03 | SoA | Choose 10 applicable controls (5 by risk, 5 at random); test that the status matches the evidence | 10 of the applicable controls | EVD-010 | MS1-02 |
| T04 | **KPI data** | Re-calculate KPI-14, KPI-18 and KPI-20 from source, plus 2 more chosen at random | 5 KPIs, latest period | EVD-019 | **MS1-05** |
| T05 | Leavers | Section 5.1 | All leavers in the period if under 25 | EVD-026 | AUD03-F01; RCA-01 |
| T06 | Access reviews | Check that every planned review happened, was recorded, and that removals were made | All reviews in 2 quarters | EVD-025 | AUD03-F02; CA-02 |
| T07 | Privileged access | Reverse test: every admin role assignment has a PIM approval; break-glass test records | All admin assignments | EVD-027 | AUD03-F03 |
| T08 | Suppliers | Trace due diligence, contract and monitoring | All 7 Critical suppliers | EVD-038 | MS1-05 (KPI-14) |
| T09 | Incidents | Trace INC-2027-014 and the EX-01 exercise report from report to lessons learned | Every Severity 1 or 2 incident, plus EX-01 | EVD-037 | 5.24–5.27 |
| T10 | Vulnerabilities | Trace critical findings from scan to fix to re-scan, and the annual penetration test | 25 critical findings, or all if fewer | EVD-030 | KPI-05 |
| T11 | Backup and recovery | Section 5.2 | Latest annual full restore, plus 2 quarterly restores | EVD-033, 034 | **MS1-09** |
| T12 | Continuity | Trace the failover test against the RTO, and the BCP exercise | Latest test of each | EVD-035 | R-09 |
| T13 | Awareness and competence | Sample staff and ISMS role holders; check training records and competence records | 25 staff; all ISMS role holders | EVD-015, 016 | MS1-07 |
| T14 | Internal audit | Check every planned audit was done, by an independent auditor, with findings followed up | All cycle 1 audits | EVD-020 | **MS1-03** |
| T15 | Management review | Trace inputs 9.3.2(a)–(g) to decisions and actions; review after the audit cycle | All reviews held | EVD-021 | MS1-13 |
| T16 | Corrective action | Choose closed actions and **re-test** their effectiveness | 2 closed actions, including CA-01 if closed | EVD-023 | RCA-01 |
| T17 | Legal requirements | Trace 3 contractual requirements (SLA, DORA term, DPA term) to controls | 3 | EVD-036 | MS1-06 |
| T18 | Head office | Observe physical controls; clear desk | Site walk-round | 7.4 (Wave 2: 7.1–7.3) | — |

## 5. Detailed tests

### 5.1 T05 — Access removal for leavers

**Objective:** access is removed **by the end of the last working day,** reliably, for employees **and contractors** (023 §9).

| Step | Action |
| --- | --- |
| 1 | Get the population of **all leavers** in the period from the **HR system,** including contractors. Reconcile its count with the leavers the HR Manager expects |
| 2 | Under 25 leavers: test all. Otherwise 25, chosen to include **every contractor and every early termination** (the RCA-01 weak point) |
| 3 | Compare each last working day with the Entra ID disable time and session revocation time |
| 4 | Check other access: Azure roles, database users, repository tokens, guest accounts, devices returned |
| 5 | For any late removal: was there an approved exception? Was there any sign-in after the leaving date? |
| 6 | **Reverse test:** all enabled accounts compared with current HR records, looking for accounts with no current person |
| 7 | Judge whether a failure is isolated or systemic: same cause as AUD03-F01? Same path (contractors)? |

### 5.2 T11 — Backup and recovery

**Objective:** backups can deliver the recovery objectives in NSD-ISMS-052 (**4-hour RTO, 1-hour RPO** for the customer database).

| Step | Action |
| --- | --- |
| 1 | Backup configuration and 30 days of job results (KPI-08) |
| 2 | Protection: immutability on, and production administrators **cannot** delete backups (T-14.1, T-14.2). Re-perform: check role assignments |
| 3 | Location: a copy outside the source region (BIA gap G2)? |
| 4 | The latest annual full restore report (BRT-01, 054): measured RTO from the declared start to the Customer Support Manager's confirmation; RPO from the last transaction in the restored data |
| 5 | **Observe** a restore if one falls in the audit window (030: AUD-08 includes observing a test) |
| 6 | Failed or missing tests: corrective actions and re-tests |

A successful backup job does not show that data can be restored. Only a measured restore does.

## 6. How current records would be judged (illustration only)

**These are not audit results.** If the tests above were run on the records held as at 30 September 2027, the auditor would expect findings like these. The real result depends on what exists in May 2028.

| Test | Current record | Likely grade | Why |
| --- | --- | --- | --- |
| T05 | AUD03-F01 (1 of 7 late), and a second late contractor in August; RCA-01 open | **Minor**, rising to **Major** if RCA-01 confirms the same cause (H3) | 033 §4: several late leavers showing the process is not working is a Major trigger |
| T11 | No annual restore report; 1 of 4 Q2 tests with no record; backups in the same region | **Major** | 5.30 and 8.13 not shown to work for a Very High risk (R-14) |
| T14 | 1 of 9 audits with records | **Major** | 9.2 not met across the scope |
| T04 | KPI-14, KPI-18, KPI-20 not supported by their sources | **Minor** | 9.1(c)–(d): results not valid |
| T15 | No management review recorded (038, 040 blank) | **Major** | 9.3 not met at all |

## 7. Findings record

| Ref | Requirement | Objective evidence | Condition | Sample and limits | Grade | Management response |
| --- | --- | --- | --- | --- | --- | --- |
| MS2-nn | To be recorded at the audit | | | | | |

**Conclusion:** to be recorded at the audit. It will state whether the ISMS would be likely to be recommended for certification **by a certification body,** and why. It will not state that Northstar is certified.

## 8. After the audit

| Step | Who | When |
| --- | --- | --- |
| Report issued | Lead auditor | Within 10 working days |
| Major: correction and plan within 10 working days; closed and verified **before the external Stage 2** | Finding owner | 030 §8 |
| Minor: plan within 20 working days; closed within 90 days | Finding owner | 030 §8 |
| Findings tracked through the remediation tracker into NSD-ISMS-034 | GRC Analyst | With the report |
| MD decides whether to book external Stage 2 | MD | After the report |

## 9. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-063) | Stage 2 objective, approach, 13-area test programme, two detailed tests, findings format |
| 0.3 | Aligned with the 066 correction: management review is unrecorded (MS1-13); entry condition, T01, T15 and the grading illustration updated. |
| 0.2 | Numbered NSD-ISMS-067 (MS2-01) and planned for May 2028, **behind five entry conditions**, so no results are claimed. Lead auditor and independence aligned with 066. Testing rules from the portfolio: populations from systems of record, 021 sample sizes, reverse tests, re-performance, a 12-month window. Programme extended to 18 tests, driven by the Very High risks and the mock Stage 1 findings, including **re-calculating KPIs** (MS1-05) and legal requirements. Leaver test covers contractors and early terminations (the RCA-01 weak point) and a reverse test; backup test checks immutability, the separate backup role, backup location, and measures RTO and RPO as 054 defines them. Section 6 illustrates grading using **existing** records only. Grades and deadlines from 030 §8. |

---

*Portfolio disclaimer: Simulated training exercise. No audit has been held, no certification decision is represented, and Northstar is not certified.*
