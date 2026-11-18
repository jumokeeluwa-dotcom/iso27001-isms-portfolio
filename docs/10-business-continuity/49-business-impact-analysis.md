# Northstar Digital Solutions Ltd — Business Impact Analysis

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-049 |
| Version | 1.0 — Draft for validation workshops |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 5.29, 5.30; clauses 6.1, 8.1. Terms follow ISO 22301 |
| Status | **Simulated. All ratings and times are proposals for validation. No workshop has been held and nothing has been approved** |
| Related documents | [NSD-ISMS-028 Backup and Business Continuity Policy](../05-policies/28-backup-business-continuity-policy.md) §3 · NSD-ISMS-050 Business Continuity Plan · [NSD-ISMS-013 Impact scale](../03-risk-management/13-risk-scoring-matrix.md) §3 · [NSD-ISMS-006 Asset register](../02-asset-management/06-information-asset-register.md) · [NSD-ISMS-014 Risk register](../03-risk-management/14-risk-register.md) (R-09, R-14, R-02, R-12) |
| Owner | Information Security / GRC Analyst (facilitates). Each activity's ratings are owned by its activity owner |
| Approver | Managing Director |
| Review | Annually (NSD-ISMS-028 §3), after any major change to the platform or organisation, and after any Severity 1 incident or BCP activation |
| Classification | Confidential |

---

## 1. Purpose and terms

The BIA identifies Northstar's business activities, how the impact of losing each one grows over time, and how quickly each must be recovered. Its results set the recovery objectives in NSD-ISMS-028 §3 and the priorities in the business continuity plan (NSD-ISMS-050).

| Term | Meaning | Example: customer platform down at 10:00 |
| --- | --- | --- |
| **MTPD** (maximum tolerable period of disruption) | The point after which the impact becomes unacceptable | 24 hours: by 10:00 the next day |
| **RTO** (recovery time objective) | Target time to restore the activity. Must be **shorter than the MTPD,** leaving time for decisions and problems | 4 hours: restored by 14:00 |
| **RPO** (recovery point objective) | The most data loss, measured in time, that is acceptable. It sets how often data is backed up | 1 hour: data no older than 09:00 |

**Targets are not capabilities.** An RTO of 4 hours means Northstar *intends* to recover in 4 hours. Only a test with measured times shows whether it *can.* Section 5 compares the two.

## 2. Scope

The BIA covers **business activities,** meaning what Northstar does for customers and itself. Systems, suppliers and people appear as **dependencies** of those activities, and their recovery times are derived from the activities they support.

Identity management, cloud infrastructure and backup and restoration are resources, not activities. A backup system has no tolerable disruption of its own: it matters because the platform and data depend on it.

## 3. Method

1. Each activity owner rates the impact of losing the activity after **1 hour, 4 hours, 1 day and 3 days,** using the 1–5 impact scale in NSD-ISMS-013 §3: financial, customer and contractual, legal and regulatory, operational, and reputational. **The highest category sets the rating,** as in risk assessment.
2. **RTO** is the latest point at which impact is still below **4 (Major).**
3. **MTPD** is the point at which impact reaches **5 (Severe).**
4. **RPO** comes from the data loss the activity can tolerate.
5. Time-sensitive peaks are recorded, such as payroll dates.
6. Dependencies are listed by asset ID, supplier and key person. Each dependency's RTO must be **no longer than** the shortest RTO of the activities that rely on it.

Using the same impact scale as the risk register means that a "Major" impact means the same thing in both documents.

## 4. Impact assessment (proposed)

| Activity | Owner | Impact at 1 h / 4 h / 1 day / 3 days | RTO | RPO | MTPD | Time-sensitive peaks |
| --- | --- | --- | --- | --- | --- | --- |
| **A1** Customer platform service (UK and EU) | Head of Engineering | 2 / 🟧 4 / 🟥 5 / 🟥 5 | 4 h | 1 h | 24 h | Customer business hours; financial services customers' month-end |
| **A2** Customer communication and support during disruption | Customer Support Manager | 2 / 3 / 🟧 4 / 🟥 5 | **1 h** | 24 h | 3 days | Whenever A1 is down: demand rises at the moment the platform fails |
| **A3** Security incident response and breach assessment | GRC Analyst | 3 / 🟧 4 / 🟥 5 / 🟥 5 | 1 h | — | 24 h | Breach assessment within 24 h (NSD-ISMS-027 §8) |
| **A4** Emergency security fixes to the platform | Head of Engineering | 1 / 2 / 3 / 🟥 5 | 1 working day | 24 h (code) | 72 h | Any actively exploited, internet-facing critical: 72-hour hard limit (KPI-05) |
| **A5** Staff access and internal collaboration | IT Manager | 2 / 3 / 3 / 🟧 4 | 4 h (identity); 2 working days (M365 data) | 24 h | 3 working days | Identity is needed to run A1 and A3 |
| **A6** Finance: billing, payroll and supplier payments | Finance Manager | 1 / 1 / 2 / 3 | 2 working days | 24 h | 3 working days; **1 working day** in payroll week | Payroll date; month-end billing |
| **A7** HR administration | HR Manager | 1 / 1 / 2 / 2 | 2 working days | 24 h | 5 working days | — |
| **A7a** Leaver notification to IT (part of A7) | HR Manager | 1 / 2 / 🟧 4 / 🟧 4 | Same working day | — | 1 working day | Every leaving date: accounts must be disabled by the end of the last working day (NSD-ISMS-023 §9; R-12) |
| **A8** Routine software development | Head of Engineering | 1 / 1 / 2 / 2 | 5 working days | 24 h (code) | 10 working days | Committed release dates |

Notes on the ratings:

- **A1:** NSD-ISMS-013 rates "platform down 4–24 hours; SLA breached" as 4, and "down more than 24 hours" as 5. The 24-hour MTPD follows from the impact scale, but the **customer SLAs and DORA contract terms are not yet recorded** (NSD-ISMS-005, MRA-2027-02) and may make it shorter.
- **A2** is rated separately because Northstar's duties to customers continue, and become more urgent, when the platform is down: notifying controllers without undue delay, and DORA-related incident terms for financial services customers (IP-03).
- **A4 and A8** separate software development into two activities. Routine releases can wait. A fix for an exploited vulnerability cannot: 3 business days over a weekend is more than 72 hours.
- **A7a** splits the leaver step out of HR. HR administration can wait a week, but a leaver missed for a day is the R-12 scenario, rated Very High.

## 5. Dependencies and capability

| Dependency | Needed by | Required RTO (shortest of its activities) | RTO in NSD-ISMS-028 | Capability evidenced? |
| --- | --- | --- | --- | --- |
| Entra ID and break-glass accounts (AST-009, AST-010) | A1, A3, A5 | 1 h | 4 h | Break-glass test quarterly (T-13.2); results to be checked |
| Key Vault (AST-006) | A1 | 4 h | 4 h | Not separately tested |
| Production environment and database (AST-007, AST-001) | A1 | 4 h; RPO 1 h | 4 h; 1 h | **Partly:** KPI-09 Q2 2027, 3 of 4 recovery tests met the RTO and RPO; the 4th has **no record** |
| Regional failover (T-09.1, T-09.2) | A1 | 4 h | 4 h | **Not evidenced:** the failover test was due 1 Mar 2027; no result is recorded in the portfolio |
| Backups (AST-011) | A1, A5, A6, A7 | 4 h | 4 h | Immutable storage planned (T-14.1). **Stored in the same region as the source:** see G2 |
| Support ticketing (AST-013) and a channel to customers that does not depend on the platform | A2 | **1 h** | 2 working days (Medium) | **Conflict:** see G1 |
| Security logs (AST-012) | A3 | 4 h | 2 working days (Medium) | Conflict: rated Medium, but needed within hours in an incident |
| Code repository and CI/CD (AST-004, AST-005) | A4, A8 | 1 working day | 2 working days | Conflict for A4 |
| Microsoft 365 (AST-008) | A2, A5, A6 | 4 h (email for A2) | 2 working days | Offline copy of the BC/DR plan exists (NSD-ISMS-028 §7) |
| HR system (AST-002) | A7, A7a | Same day (A7a, with a manual fallback) | 2 working days | **No documented manual fallback** for leavers: see G6 |
| Finance and banking systems (AST-003) | A6 | 2 working days | 2 working days | Not tested |
| **Microsoft as a supplier** (Azure, M365, Entra ID) | All | — | — | Concentration risk (EXT-05): one provider for platform, identity and email |
| **Key people:** Head of Engineering, IT Manager | A1, A3, A4, A5 | — | — | Both lead most recovery steps; a named third person is proposed under MRA-2027-06 (039; not yet decided) |
| **Locations:** UK office, UK and EU homes | All | — | — | Home working is the alternative to the office. Climate-related disruption (EXT-12), such as flooding, heat or power loss, can affect homes as well as the office |

**Constraint on recovery:** EU customer data must stay in the EU when failing over or restoring (R-02). The recovery target region for EU data is part of the failover runbook (T-09.1).

## 6. Gaps found

The BIA records these gaps; it does not resolve them. The GRC Analyst triages each one under NSD-ISMS-045 §2, so it is tracked in one place.

| Gap | Why it matters | Proposed route |
| --- | --- | --- |
| **G1** Customer communication needs a 1-hour RTO, but its systems are rated Medium (2 working days) | Northstar could be unable to tell customers about an outage while the outage is happening | Asset availability re-rating (NSD-ISMS-009); BCP communication arrangements (NSD-ISMS-050 §6) |
| **G2** Backups are kept in the same Azure region as the source (AST-011) | A regional outage (R-09) could take the backups down with the platform, so the 4-hour RTO could not be met from backup | Risk review with the R-09 and R-14 owners |
| **G3** Failover test result not evidenced, and one restore test has no record (KPI-09 Red) | The 4-hour RTO is a target, not a demonstrated capability | Already open: NSD-ISMS-044 action (IT Manager); NSD-ISMS-034 if confirmed |
| **G4** Recovery depends on two people | If both are unavailable, A1, A3 and A4 have no recovery lead | Proposed: MRA-2027-06 (039) |
| **G5** Security logs and CI/CD rated Medium, but needed sooner by A3 and A4 | Investigation and emergency fixes could be delayed | Asset availability re-rating |
| **G6** No manual fallback for leaver notification if the HR system is down | The R-12 scenario, and the same weakness examined in RCA-01 (NSD-ISMS-048) | BCP workaround (NSD-ISMS-050 §5) |
| **G7** Customer SLAs and DORA terms not recorded | A1's MTPD cannot be confirmed | NSD-ISMS-005; proposed action MRA-2027-02 (039) |

## 7. Recovery priority

Recovery follows dependencies, not only importance. A platform cannot be restored by people who cannot sign in.

1. Identity and break-glass access (AST-009, AST-010).
2. A customer communication channel that does not depend on the platform (A2).
3. Key Vault (AST-006).
4. Production environment and database (AST-007, AST-001), restored from clean backups (AST-011).
5. Security logging (AST-012), to confirm that the restored systems are clean.
6. Microsoft 365 (AST-008).
7. Code repository and CI/CD (AST-004, AST-005), for emergency fixes.
8. Finance, ahead of HR in a payroll week (AST-003).
9. HR system (AST-002); the manual leaver fallback runs meanwhile.

## 8. Validation and approval

| Step | Who | By |
| --- | --- | --- |
| Validation workshop for each activity: impact ratings, times, dependencies and peaks | Each activity owner, facilitated by the GRC Analyst | 31 Oct 2027 |
| Check A1 against customer SLAs and DORA terms | Sales lead, with the Data Protection lead | When NSD-ISMS-005 is approved |
| Update NSD-ISMS-028 §3 and asset availability ratings for any changed RTO | GRC Analyst | Within 10 working days of validation |
| Approval | Managing Director | 30 Nov 2027 |

Approval accepts the MTPDs, which are statements of the impact management is prepared to tolerate. That makes them an MD decision, not an analyst's.

---

*Portfolio disclaimer: Simulated BIA. No business impact workshop or management approval has taken place. Ratings and times are proposals for validation.*
