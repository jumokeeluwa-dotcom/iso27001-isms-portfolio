# Northstar Digital Solutions Ltd — ISMS Monitoring and Measurement Plan

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-043 |
| Version | 0.2 — Proposed |
| Procedure | [NSD-ISMS-041](41-monitoring-measurement-procedure.md) · KPI definitions: [NSD-ISMS-042](42-kpi-register.md) |
| Plan owner | Information Security / GRC Analyst |
| Approver | ISMS Steering Group |
| Classification | Internal |

---

> **Proposed plan.** Data sources, owners and timings must be confirmed before use. No results have been collected.

## 1. Who does what (clause 9.1(d)–(f))

| Step | Role | Rule |
| --- | --- | --- |
| **Collect** (monitor and measure) | Data owner named for each KPI | Extracts from the system of record and submits the source report with the figure |
| **Analyse** | GRC Analyst | Validates, calculates, rates, identifies trends and drafts commentary |
| **Evaluate** | ISMS Steering Group monthly; MD quarterly and at management review | Decides on actions and escalations. **A data owner does not evaluate their own KPI** |
| **Check the checker** | Internal auditor | Checks the figures for GRC-owned KPIs and samples others in AUD-10 |

## 2. Monthly cycle

| Working day after month end | Activity | Who |
| --- | --- | --- |
| Month end | Data cut-off | — |
| WD 5 | Data owners submit figures **with source extracts** | Data owners |
| WD 7 | Validation and analysis; ratings and trends; queries back to owners | GRC Analyst |
| WD 8 | Hard-limit breaches escalated to the MD, if not already raised | GRC Analyst |
| WD 10 | Dashboard (NSD-ISMS-044) issued | GRC Analyst |
| Steering Group meeting (mid-month) | Evaluation, decisions and actions | Steering Group |

**Quarterly.** Quarterly KPIs are added in the month after quarter end, together with a **trend review** across at least 3 periods and a summary for the MD.

**Annually.** A full-year performance analysis is an input to management review (NSD-ISMS-037, item 5).

## 3. Collection plan

| KPI | Source and extraction method | Data owner | Due | Validation check |
| --- | --- | --- | --- | --- |
| KPI-01 Leavers disabled on time | HR leaver report (the population), compared with Entra ID disable events and sign-in logs | HR Manager, with the IT Manager | Monthly WD 5 | Leaver count matches HR headcount movement; every leaver has a disable timestamp |
| KPI-02 Access reviews recorded | Entra ID Access Reviews: completed vs scheduled | IT Manager | Quarterly | Every Restricted asset (NSD-ISMS-006) has a scheduled review |
| KPI-03 MFA coverage | Entra ID authentication method and MFA reports at month end | IT Manager | Monthly WD 5 | Account total matches the enabled-account count; exclusions listed by name |
| KPI-04 Standing privileged access | Entra ID PIM eligible vs active assignments | IT Manager | Monthly WD 5 | Break-glass accounts identified by ID |
| KPI-05 Critical vulnerabilities | Scanner export and remediation tickets: discovered, due, closed | Head of Engineering | Monthly WD 5 | Every critical finding from the scanner has a ticket |
| KPI-06 Cloud configuration compliance | Azure Policy compliance export | Head of Engineering | Monthly WD 5 | Scope covers all subscriptions in UK and EU regions |
| KPI-07 Deployment approvals | CI/CD deployment log | Head of Engineering | Monthly WD 5 | Deployment count matches the release log |
| KPI-08 Backup job success | Backup console job history over 30 days | IT Manager | Monthly WD 5 | All in-scope systems have scheduled jobs |
| KPI-09 Recovery tests | DR and restore test reports with measured times | IT Manager / Head of Engineering | Quarterly | Measured times recorded, not just pass or fail |
| KPI-10 Training completion | Training system report vs HR headcount | HR Manager | Quarterly | Population taken from HR, including contractors |
| KPI-11 Phishing report rate | Simulation platform results | GRC Analyst | Quarterly | Recipients match the target list |
| KPI-12 Severity 1 triage | Incident log timestamps | GRC Analyst | Monthly WD 5 | "Reported" and "triage started" times both recorded |
| KPI-13 Breach handling | Breach log: assessment and notification times vs DPA timescales | Data Protection lead | Monthly WD 5 | Every incident involving personal data appears in the breach log |
| KPI-14 Critical suppliers assessed | Supplier register | Finance Manager | Quarterly | Tiering current; new suppliers included |
| KPI-15 Guest accounts within expiry | Entra ID guest report, compared with supplier contract end dates | IT Manager | Monthly WD 5 | Every guest has a named sponsor |
| KPI-16 DLP blocks | Purview DLP reports | IT Manager | Monthly WD 5 | Policy coverage unchanged; any spike explained |
| KPI-17 Treatment actions on time | NSD-ISMS-015 tracker | GRC Analyst | Monthly WD 5 | "Verified" means the evidence was checked |
| KPI-18 Very High risks beyond tolerance | NSD-ISMS-014 and NSD-ISMS-016 Part B | GRC Analyst | Monthly WD 5 | Tolerance start dates recorded |
| KPI-19 Corrective actions on time | NSD-ISMS-034 | GRC Analyst | Monthly WD 5 | "Closed" means verified effective |
| KPI-20 Policy acknowledgement | Acknowledgement tool vs HR headcount | HR Manager | Quarterly | Current policy versions only |
| KPI-21 Open major nonconformities | NSD-ISMS-033 and 034; external audit reports | GRC Analyst | Monthly WD 5 | Includes external audit findings |

## 4. Data quality and validation

Before any result is reported, the GRC Analyst confirms:

1. The reporting period and cut-off date.
2. The population, taken from the **system of record**, with its count.
3. That the source records are complete. **Missing records count as failures,** not successes.
4. That calculations and timestamps are correct.
5. That missing or inconsistent records have been investigated with the data owner.
6. That the source extract and calculation are kept with the result.
7. Any limitations and exclusions. Unvalidated results are labelled **"Unvalidated"** (NSD-ISMS-041 §6).

**Quarterly re-performance.** The GRC Analyst recalculates **3 KPIs a quarter** directly from the source system, rotating so that every KPI is covered each year. The internal auditor does the same for the GRC-owned KPIs (KPI-11, 12, 17, 18, 19, 21) in AUD-10.

## 5. Reporting schedule

| Report | Frequency | Audience |
| --- | --- | --- |
| Performance dashboard (NSD-ISMS-044) | Monthly | ISMS Steering Group; data owners |
| Technical detail (platform and IT) | Monthly | Head of Engineering; IT Manager |
| Risk treatment and acceptance status | Monthly | Steering Group; risk owners |
| Quarterly trend review and summary | Quarterly | Managing Director |
| Annual performance analysis | Annually | Management review (NSD-ISMS-037) |
| **Hard-limit escalation** | **Within 2 working days** of discovery | Managing Director |

## 6. Escalation

These match NSD-ISMS-041 §9 and the hard limits in NSD-ISMS-042 §4. The draft's list is kept, with timescales added:

| Situation | Escalate to | Within |
| --- | --- | --- |
| Active or suspected compromise of a privileged account | Incident manager; MD (Severity 1 under NSD-ISMS-027) | **1 hour** |
| Unauthorised access to Restricted information, or a leaver account used after leaving (KPI-01 hard limit) | Incident manager; Data Protection lead; MD | **1 hour** for incident triage; MD within 2 working days |
| Critical vulnerability past its deadline, or actively exploited and past 72 hours (KPI-05) | Head of Engineering; MD for the hard limit | 2 working days |
| Failed recovery test for a High-availability service (KPI-09) | IT Manager or Head of Engineering; Steering Group | Next Steering Group, or sooner if the service is at risk |
| Any other hard limit (KPI-03, 04, 07, 13, 18) | MD | 2 working days |
| Serious or repeated control failure: Red for 2 periods | Steering Group; possible nonconformity (NSD-ISMS-034) | Next Steering Group |
| A High or Very High risk with no approved treatment or acceptance | Risk owner; Steering Group; MD for Very High | Next Steering Group; 2 working days for Very High |

## 7. Evidence retention

The following are kept in the GRC evidence repository (Confidential) for **3 years** (NSD-ISMS-041 §11):

- source extracts;
- calculations;
- validation notes and re-performance results;
- exceptions;
- escalations;
- dashboards.

## 8. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-039) | Collection plan for 10 KPIs, validation steps, reporting schedule and escalation list |
| 0.2 | Numbered NSD-ISMS-043, aligned with the 21 KPIs in NSD-ISMS-042. Separate roles for collecting (data owner), analysing (GRC Analyst) and evaluating (Steering Group, MD), with internal audit checking GRC-owned figures. A monthly working-day timetable. Collection plan with a validation check for each KPI. Quarterly re-performance of 3 KPIs. "Security Lead" and "Procurement Manager" replaced with existing roles; "senior management" replaced with the MD and Steering Group. "Promptly, based on severity" replaced with escalation timescales tied to the incident policy and hard limits. The draft's seven data-quality steps and its escalation situations are kept. |

---

*Portfolio disclaimer: Proposed simulated monitoring plan. Data sources, owners, intervals and targets must be validated before real-world use.*
