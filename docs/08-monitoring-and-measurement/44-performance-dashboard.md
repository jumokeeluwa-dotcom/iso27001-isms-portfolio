# Northstar Digital Solutions Ltd — ISMS Performance Dashboard and Report

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-044 |
| Version | 0.2 — Illustrative example |
| Reporting period | **August 2027** (data cut-off 31 August 2027). This is also the cut-off for management review MR-2027-01 |
| Status | **Simulated. All figures are fictional training examples, not actual performance data** |
| Prepared by (analysis) | Information Security / GRC Analyst |
| Evaluated by | ISMS Steering Group (September meeting) |
| Definitions | [NSD-ISMS-042 KPI Register](42-kpi-register.md): calculations, targets and thresholds · Plan: [NSD-ISMS-043](43-monitoring-measurement-plan.md) |
| Classification | Confidential |

---

## 1. Executive summary

**7 KPIs Green, 7 Amber, 5 Red, and 2 with no events. No hard limit was breached this month.**

**Red KPIs needing attention**

| KPI | Issue |
| --- | --- |
| KPI-02 | Access reviews recorded (80%). Red for the **second period in a row**, so the fix from the AUD-03 finding is not yet working |
| KPI-03 | MFA coverage (96%) |
| KPI-09 | Recovery tests (75%): one test not evidenced |
| KPI-14 | Critical suppliers assessed (80%): **Obj 9 off track** |
| KPI-17 | Risk treatment actions on time (70%): linked to the resource gap already raised for management review |

**Improving**

- KPI-01: one late leaver in the month, with no sign-in after leaving. Rated Amber.
- KPI-11: phishing report rate is rising.

All results were validated against source extracts (NSD-ISMS-043 §4), except where noted in section 3.

## 2. Dashboard

Ratings come **only** from the thresholds in NSD-ISMS-042 §3. Small populations are shown as counts as well as percentages, because 90% of 10 is a single item.

| KPI | Indicator | Result | Target | Trend (Jun → Jul → Aug) | Rating | Hard limit breached? |
| --- | --- | --- | --- | --- | --- | --- |
| KPI-01 | Leavers disabled on time | 90% (9 of 10) | 100% | 100% → 100% → 90% | 🟨 Amber | No: no sign-ins after leaving |
| KPI-02 | Access reviews recorded (Q2) | 80% (4 of 5) | 100% | Q1 80% → Q2 80% | 🟥 Red | — |
| KPI-03 | MFA coverage | 96% (104 of 108) | 100% | 97% → 96% → 96% | 🟥 Red | No: none of the 4 is an admin account |
| KPI-04 | Standing privileged access | 0 | 0 | 0 → 0 → 0 | 🟩 Green | No |
| KPI-05 | Critical vulnerabilities fixed on time | 90% (9 of 10) | 95% | 92% → 95% → 90% | 🟨 Amber | No: nothing actively exploited |
| KPI-06 | Cloud configuration compliance | 96% | 95% | 93% → 95% → 96% | 🟩 Green | — |
| KPI-07 | Deployments with second-person approval | 100% (42 of 42) | 100% | 100% → 100% → 100% | 🟩 Green | No |
| KPI-08 | Backup job success | 99.4% | 99% | 99.1% → 99.3% → 99.4% | 🟩 Green | — |
| KPI-09 | Recovery tests within RTO and RPO (Q2) | 75% (3 of 4) | 100% | — (first quarter) | 🟥 Red | — |
| KPI-10 | Training completion (Q2) | 91.8% | 95% | Q1 70% → Q2 91.8% | 🟨 Amber | — |
| KPI-11 | Phishing report rate (Q2) | 42% | Rising; 50% illustrative | Q1 35% → Q2 42% | 🟩 Green | — |
| KPI-12 | Severity 1 triage within 1 hour | No events | 100% | — | No events | — |
| KPI-13 | Breach handling on time | No events | 100% | — | No events | — |
| KPI-14 | Critical suppliers assessed (Q2) | 80% (4 of 5) | 100% | Q1 60% → Q2 80% | 🟥 Red | — |
| KPI-15 | Guest accounts within expiry | 97% | 100% | 95% → 96% → 97% | 🟨 Amber | — |
| KPI-16 | DLP blocks of Restricted data | 14 | Trend monitored | 10 → 9 → 14 | 🟨 Amber | — |
| KPI-17 | Risk treatment actions on time | 70% | 90% | 78% → 74% → 70% | 🟥 Red | — |
| KPI-18 | Very High risks beyond tolerance | 0 | 0 | 0 → 0 → 0 | 🟩 Green | No |
| KPI-19 | Corrective actions closed on time | 80% (4 of 5) | 90% | — → 75% → 80% | 🟨 Amber | — |
| KPI-20 | Policy acknowledgement (Q2) | 93% | 95% | Q1 88% → Q2 93% | 🟨 Amber | — |
| KPI-21 | Open major nonconformities | 0 | 0 | 0 → 0 → 0 | 🟩 Green | — |

**"No events"** (KPI-12, 13) is not counted as Green or as 100% (NSD-ISMS-042 §1).

## 3. Analysis of Red and Amber results

| KPI | What the data shows | Validation | Next step (NSD-ISMS-041 §9) |
| --- | --- | --- | --- |
| **KPI-02** Red | 1 of 5 Restricted asset reviews not recorded in Q2, the same pattern as AUD03-F02 in Q1. **Second period Red** | Validated against Entra ID Access Reviews | Report to the Steering Group: evidence that **CA-02 is not yet effective.** The auditor is told before the CA-02 effectiveness check |
| **KPI-03** Red | 4 accounts without MFA: 3 service accounts awaiting managed identity migration (T-11.1), and 1 joiner inside the registration window. No admin accounts | Validated; exclusions listed by name | IT Manager investigates and reports within 10 working days. Check whether T-11.1's closure evidence matches reality (a C-23 type check) |
| **KPI-09** Red | 3 of 4 tests met the RTO and RPO. The 4th has **no test record.** It is counted as a failure, because missing records never count as success | Validated. The record is missing, not failed | IT Manager confirms whether the test ran; if not, reschedules within 30 days. Assess as a possible nonconformity (Obj 8) |
| **KPI-14** Red | 1 Critical supplier not assessed in the last 12 months. **Obj 9 off track** | Validated against the supplier register | Finance Manager investigates. Input to management review decision D-07 (objective targets) |
| **KPI-17** Red | Treatment actions on time falling for 3 months (78% → 74% → 70%) | Validated against NSD-ISMS-015 | **A worsening 3-month trend.** Linked to the DevOps and IT capacity gap. Input to management review decision D-04 (resources) |
| KPI-01 Amber | 1 contractor disabled 2 days late; no sign-ins after leaving | Validated with sign-in logs | Covered by CA-01 (due 31 August). The September result shows whether it worked |
| KPI-05 Amber | 1 critical vulnerability fixed in 17 days; not internet-facing or exploited | Validated | Owner confirms the cause; monitor |
| KPI-10 Amber | Improving from 70% to 91.8%; still below 95% | Validated against HR headcount | Covered by proposed action MRA-2027-04 |
| KPI-15 Amber | 3 guest accounts without expiry set; none belongs to an ended contract | Validated | IT Manager sets the expiries |
| KPI-16 Amber | Blocks rose from 9 to 14 (+56%), after the DLP rule for personal email went live (CA-03.1) | **Partly validated:** the rise is expected from the new rule, but the cause is not yet confirmed | The IT Manager confirms the rise comes from the new rule and not from new behaviour. Feeds the R-21 assessment |
| KPI-19 Amber | 4 of 5 corrective actions on time | Validated | Overdue item reported to the Steering Group |
| KPI-20 Amber | Improving from 88% to 93% | Validated | HR Manager chases outstanding acknowledgements |

## 4. Objective status (clause 6.2)

| Objective | Measured by | Status |
| --- | --- | --- |
| Obj 3: high risks treated | KPI-17, KPI-18 | **Off track** (KPI-17 Red) |
| Obj 5: awareness | KPI-10 | Improving; below target |
| Obj 6: privileged access | KPI-03, KPI-04 | Privileged accounts met (KPI-04 Green); overall MFA coverage Red |
| Obj 7: vulnerabilities | KPI-05 | Slightly below target |
| Obj 8: BC/DR | KPI-09 | **Off track** (missing test record) |
| Obj 9: suppliers | KPI-14 | **Off track** |
| Obj 10: audit readiness | KPI-21 | On track: no major nonconformities |

Obj 1, 2 and 4 are tracked as milestones in the charter.

## 5. Escalations and actions this month

**Hard-limit escalations to the MD: none.**

| Item | Owner | Due | Where it is tracked |
| --- | --- | --- | --- |
| Investigate KPI-03 Red | IT Manager | 14 Sep 2027 (10 working days) | This dashboard; next month's commentary |
| Investigate KPI-09 Red; assess as a possible nonconformity | IT Manager | 14 Sep 2027 | NSD-ISMS-034 if confirmed |
| Investigate KPI-14 Red | Finance Manager | 14 Sep 2027 | This dashboard |
| KPI-02 second-period Red: evidence that CA-02 is not yet effective | HR Manager (CA-02 owner) | Next Steering Group | NSD-ISMS-034 (CA-02) |
| KPI-17 falling trend: resource decision | **MD** | MR-2027-01 (22 September) | Management review decision D-04 (NSD-ISMS-037) |

These are **investigations, not new corrective actions.** Where an investigation confirms a nonconformity, the corrective action goes in NSD-ISMS-034. Actions are not tracked in two places.

## 6. Analyst conclusion

Most technical controls that protect against the most serious risks are performing to target: privileged access, deployment approval, backups, cloud configuration and major nonconformities. The weaknesses are mainly in **processes that depend on people completing and recording tasks:** access reviews, supplier assessments, test records and treatment actions.

The falling risk treatment trend points to a capacity issue rather than control failure. This supports the resource decision already on the agenda for management review.

All Red results are validated and assigned for investigation, and no hard limit was breached. These results are input (d)(2) to MR-2027-01.

## 7. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-040) | 10 illustrative KPIs, observations, recommended actions and conclusion |
| 0.2 | Numbered NSD-ISMS-044 and expanded to all 21 KPIs in NSD-ISMS-042. **Ratings recalculated strictly from the register thresholds:** MFA 96% changed from Amber to **Red** (below 98%); supplier reviews 80% from Amber to **Red** (below 90%); leavers 90% from Red to **Amber** (one late, no sign-ins, corrective action in place). Training target corrected to 95%. Incident acknowledgement replaced by KPI-12 and 13, reported as "No events". Added counts for small populations, 3-period trends, a hard-limit column, validation status, objective status, escalation timings and links to the corrective action and management review registers. Owners aligned: "Security Lead" removed; "Risk Owners / Senior Management" became the MD's resource decision. The illustrative month is set as August 2027 to connect with MR-2027-01. The draft's investigation-first observations are kept and made specific. |

---

*Portfolio disclaimer: All figures, observations and proposed actions are fictional training examples. They must not be presented as actual organisational results or evidence of control effectiveness.*
