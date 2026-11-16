# Northstar Digital Solutions Ltd — Information Security KPI Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-042 |
| Version | 0.2 — Proposed, for Steering Group and MD approval |
| Procedure | [NSD-ISMS-041](41-monitoring-measurement-procedure.md): this register is the **single source** of measure definitions (§3) |
| Register owner | Information Security / GRC Analyst |
| Approver | Managing Director. The Steering Group approves definition changes |
| Classification | Internal. Results are Confidential |

---

> **All targets and thresholds are proposals** and need management approval before use. Most targets come from commitments already in the charter or policies, and the source is shown.

## 1. Principles

- A KPI must be **measurable and useful for a decision.** "Access management is good" is not a KPI. "The percentage of leavers disabled by the end of their last working day" is.
- **Missing records are never counted as success.** An item with no record counts as a failure in the numerator and stays in the denominator.
- **Where there are no events in a period, report "No events",** never 100%.
- **A good percentage does not prove a control works.** Hard limits (section 4) and audit re-performance (AUD-10) back up the numbers.
- **Targets come from real requirements:** the charter objectives, policies, contracts and law. The source is cited for each.

## 2. KPI definitions

Types (NSD-ISMS-041 §4): **OBJ** objective measure · **KPI** control effectiveness · **KRI** risk indicator · **PRC** ISMS process.

| ID | Indicator | Type | Calculation: numerator ÷ denominator; population and timing | Source | Frequency |
| --- | --- | --- | --- | --- | --- |
| KPI-01 | Leavers disabled on time | KPI | Leavers disabled by the end of their last working day ÷ all leavers in the month, **taken from the HR system** | HR leaver report; Entra ID audit log | Monthly |
| KPI-02 | Access reviews completed and recorded on time | KPI | Reviews of Restricted assets and privileged roles completed **with a record** by the due date ÷ reviews due in the quarter | Entra ID Access Reviews | Quarterly |
| KPI-03 | MFA coverage | KPI | Enabled accounts with MFA **or** a managed identity ÷ all enabled accounts, including service accounts, at month end | Entra ID MFA and authentication method reports | Monthly |
| KPI-04 | Standing privileged access | KRI | Number of standing privileged role assignments, excluding the 2 break-glass accounts, at month end | Entra ID PIM | Monthly |
| KPI-05 | Critical vulnerabilities fixed on time | KPI | Critical vulnerabilities fixed within 14 days ÷ critical vulnerabilities due in the month | Vulnerability scanner; tickets | Monthly |
| KPI-06 | Cloud configuration compliance | KPI | Compliant resources ÷ resources assessed against the Azure Policy baseline, at month end | Azure Policy | Monthly |
| KPI-07 | Production deployments with second-person approval | KPI | Deployments approved by someone other than the author ÷ all production deployments in the month | CI/CD deployment log | Monthly |
| KPI-08 | Backup job success | KPI | Successful backup jobs ÷ scheduled jobs over 30 days | Backup console | Monthly |
| KPI-09 | Recovery tests within RTO and RPO | OBJ | Restore and failover tests meeting the RTO and RPO ÷ tests scheduled in the quarter | DR test reports | Quarterly |
| KPI-10 | Security awareness training completion | OBJ | Staff and contractors with training completed in the last 12 months ÷ all staff and contractors, at quarter end | Training system | Quarterly |
| KPI-11 | Phishing simulation report rate | KRI (leading) | Users who reported the simulated phish ÷ users who received it | Simulation platform | Quarterly |
| KPI-12 | Severity 1 triage within 1 hour | KPI | Severity 1 incidents triaged within 1 hour ÷ Severity 1 incidents in the month | Incident log | Monthly |
| KPI-13 | Breach handling on time | KPI | Personal data breaches with **both** an assessment within 24 hours **and** customer notification within DPA timescales ÷ personal data breaches in the month | Incident and breach log | Monthly |
| KPI-14 | Critical suppliers assessed | OBJ | Critical suppliers assessed in the last 12 months ÷ Critical suppliers, at quarter end | Supplier register | Quarterly |
| KPI-15 | Guest accounts within expiry | KPI | Guest accounts with a sponsor and expiry within 90 days ÷ all guest accounts, at month end | Entra ID | Monthly |
| KPI-16 | DLP blocks of Restricted data | KRI | Count of DLP blocks: Restricted data sent to personal email or unapproved AI tools in the month | Purview DLP reports | Monthly |
| KPI-17 | Risk treatment actions on time | PRC | Treatment actions verified by their due date ÷ treatment actions due | NSD-ISMS-015 | Monthly |
| KPI-18 | Very High risks beyond their tolerance period | KRI | Very High residual risks tolerated longer than the 3-month limit without MD renewal | NSD-ISMS-014, 016 | Monthly |
| KPI-19 | Corrective actions closed on time | PRC | Corrective actions verified effective by their due date ÷ corrective actions due | NSD-ISMS-034 | Monthly |
| KPI-20 | Policy acknowledgement | OBJ | Staff and contractors who have acknowledged the current policies ÷ all staff and contractors | HR system or acknowledgement tool | Quarterly |
| KPI-21 | Open major nonconformities | PRC | Count of major nonconformities from internal or external audits still open | NSD-ISMS-033, 034 | Monthly |

## 3. Targets, thresholds and owners

Ratings follow NSD-ISMS-041 §7. **Hard limits** are breaches that make the KPI Red whatever the percentage, and are escalated to the MD within 2 working days.

| ID | Target (source) | Amber | Red / hard limit | Data owner | Links |
| --- | --- | --- | --- | --- | --- |
| KPI-01 | 100% (023 §9) | One late, with no sign-in after leaving and a corrective action raised | Two or more late in the month. **Hard limit: any sign-in after the leaving date** | HR Manager (R-12 owner); IT Manager provides the log data | R-12; A 6.5 |
| KPI-02 | 100% (023 §8) | 90–99% | Below 90%, or any Restricted asset unreviewed for 2 quarters | IT Manager | R-03, R-12; A 5.18 |
| KPI-03 | 100% (023 §6) | 98–99.9%, with exceptions approved | Below 98%. **Hard limit: any admin account without phishing-resistant MFA** | IT Manager | R-10, R-11, R-13; A 8.5; Obj 6 |
| KPI-04 | 0 (023 §7) | — | **Hard limit: any standing assignment** | IT Manager | R-13; A 8.2; Obj 6 |
| KPI-05 | 95% or higher (Obj 7; 029 §4) | 85–94% | Below 85%. **Hard limit: any actively exploited internet-facing critical not fixed within 72 hours** | Head of Engineering | R-17; A 8.8; Obj 7 |
| KPI-06 | 95% or higher (029 §6) | 90–94% | Below 90% | Head of Engineering | R-08, R-02; A 8.9 |
| KPI-07 | 100% (029 §5) | — | **Hard limit: any deployment without second-person approval** | Head of Engineering | R-07; A 8.32 |
| KPI-08 | 99% or higher (028 §5) | 97–98.9% | Below 97%, or any High-availability system failing 2 days running | IT Manager | R-14; A 8.13 |
| KPI-09 | 100% (028 §6–7; Obj 8) | — | Any test missing the RTO or RPO, or a scheduled test not done | IT Manager (restore); Head of Engineering (failover) | R-09, R-14; A 5.30; Obj 8 |
| KPI-10 | 95% or higher (Obj 5) | 85–94% | Below 85% | HR Manager | R-10; A 6.3; Obj 5 |
| KPI-11 | Rising trend; illustrative target 50% or higher | Flat across 2 quarters | Falling across 2 quarters | GRC Analyst | R-10; A 6.3 |
| KPI-12 | 100% (027 §5) | — | Any Severity 1 triaged later than 1 hour | GRC Analyst (incident manager) | R-18; A 5.25 |
| KPI-13 | 100% (027 §8) | — | **Hard limit: any assessment over 24 hours or any late customer notification** | Data Protection lead | R-18; A 5.24–5.26 |
| KPI-14 | 100% (Obj 9; 026 §7) | 90–99% | Below 90% | Finance Manager | R-16; A 5.19–5.22; Obj 9 |
| KPI-15 | 100% (023 §10) | 95–99% | Below 95%, or any account of an ended contract still active | IT Manager | R-16; A 5.18 |
| KPI-16 | Trend monitored; spikes investigated | Rise of 50% or more on the previous month | Any Restricted data found sent externally **without** a block, from an incident or audit | IT Manager | R-19, R-21; A 8.12 |
| KPI-17 | 90% or higher (NSD-ISMS-015) | 80–89% | Below 80%, or any P1 action overdue | GRC Analyst | Obj 3 |
| KPI-18 | 0 (016 §3) | — | **Hard limit: any Very High risk beyond its tolerance period** | GRC Analyst | Obj 3; NSD-ISMS-016 |
| KPI-19 | 90% or higher (030 §13; 034 §7) | 80–89% | Below 80%, or any Minor more than 30 days overdue | GRC Analyst | Clause 10.2 |
| KPI-20 | 95% or higher (022 §11) | 85–94% | Below 85% | HR Manager | Obj 1; A 5.1 |
| KPI-21 | 0 (Obj 10) | — | Any open major nonconformity | GRC Analyst | Obj 10 |

**Separation of duties.** Where the GRC Analyst is the data owner (KPI-11, 12, 17, 18, 19, 21), the internal auditor checks the figures during AUD-10 (NSD-ISMS-041 §6).

## 4. Hard limits

A hard limit is a single event that matters more than the overall percentage. One leaver account used after leaving is serious even if 99% of leavers were disabled on time.

Seven KPIs have hard limits: **KPI-01, 03, 04, 05, 07, 13 and 18.** Any breach is escalated to the MD within 2 working days (NSD-ISMS-041 §9), and assessed as a possible incident under NSD-ISMS-027.

## 5. Objective coverage (clause 6.2)

| Charter objective | Measured by |
| --- | --- |
| Obj 1: governance (policy and scope approved) | KPI-20; approval milestones tracked on the dashboard |
| Obj 2: asset inventory owned | Milestone: owner acceptance at 100% (NSD-ISMS-007), then the quarterly attestation rate (NSD-ISMS-011) |
| Obj 3: high risks treated | KPI-17, KPI-18 |
| Obj 4: controls determined by risk | Milestone: SoA v1.0 approved; then the share of SoA controls with current evidence |
| Obj 5: awareness | KPI-10 (with KPI-11 as the leading indicator) |
| Obj 6: privileged access controlled | KPI-03, KPI-04 |
| Obj 7: vulnerabilities fixed on time | KPI-05 |
| Obj 8: BC/DR tested within RTO | KPI-09 |
| Obj 9: suppliers assured | KPI-14 |
| Obj 10: audit readiness | KPI-21 |

## 6. Interpretation and limits

The draft's principles are kept:

- A high percentage does not on its own prove a control is effective. Hard limits and audit testing support it.
- The population must be complete and come from the system of record. For example, KPI-01 takes leavers from HR, not from IT's list.
- Missing records are not counted as success.
- Targets must reflect real business, legal, contractual and risk requirements.
- Some KPIs need written analysis alongside the number. KPI-11 and KPI-16 are trend measures, not pass or fail.
- Where there are no events in a period, record "No events", not 100%.

## 7. Review

The register is reviewed **annually,** and when objectives, risks or policies change. Definition changes need Steering Group approval and are version-controlled. The dashboard marks any break in a trend (NSD-ISMS-041 §6).

## 8. What happened to the draft's KPIs

| Draft | Now | Change |
| --- | --- | --- |
| KPI-001 Leaver removal | KPI-01 | "Required timeframe" set to the end of the last working day; population from HR; hard limit on use after leaving |
| KPI-002 Access reviews | KPI-02 | Must be **recorded** (the lesson from AUD03-F02) |
| KPI-003 MFA | KPI-03 | Includes service accounts and managed identities; admin hard limit |
| KPI-004 Critical vulnerabilities | KPI-05 | 14-day deadline and the 72-hour exploited hard limit stated; owner changed to the Head of Engineering |
| KPI-005 Restore testing | KPI-09 | Pass means meeting the RTO and RPO, not just completing a restore |
| KPI-006 Training | KPI-10 | **Target changed from 100% to 95%** to match charter Obj 5 |
| KPI-007 Incident acknowledgement | KPI-12, KPI-13 | Activity measure replaced by outcome measures: triage within 1 hour; breach assessment and notification on time |
| KPI-008 Corrective actions | KPI-19 | "Closed" means verified effective |
| KPI-009 Supplier reviews | KPI-14 | Critical suppliers within 12 months; owner changed to the Finance Manager |
| KPI-010 Risk treatment progress | KPI-17 | "Completed" means verified; KPI-18 added for Very High tolerance |
| (gap) | KPI-04, 06, 07, 08, 11, 15, 16, 20, 21 | Added for privileged access, cloud configuration, deployment approval, backups, phishing behaviour, guest accounts, DLP and R-21, policy acknowledgement, and major nonconformities |

## 9. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-038) | 10 KPIs with calculations, targets, owners, thresholds and interpretation principles |
| 0.2 | Numbered NSD-ISMS-042 and made the single source of measures (NSD-ISMS-041 §3). Expanded to 21 KPIs covering every charter objective and the main risks. Precise calculations with population, source and timing. One data owner per KPI, using existing roles. Targets taken from the charter and policies, including the training target changed to 95% to match Obj 5. Amber and Red thresholds set per KPI, and seven hard limits defined. Added separation of duties for GRC-owned KPIs and an objective coverage table. The draft's interpretation principles are kept. |

---

*Portfolio disclaimer: All KPI targets are proposed examples and require management approval before operational use.*
