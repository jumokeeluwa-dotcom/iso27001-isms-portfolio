# Northstar Digital Solutions Ltd — Backup and Business Continuity Policy

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-028 |
| Version | 1.0 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (Annex A 5.29, 5.30, 8.13, 8.14) |
| Parent policy | [NSD-ISMS-022 Information Security Policy](22-information-security-policy.md) |
| Policy owner | IT Manager (backup and recovery) |
| Business continuity owner | Managing Director (owner of the BC/DR plans, AST-019) |
| Approver | Managing Director |
| Review frequency | Annually, after each test, and after any invocation |
| Classification | Internal |

---

## 1. Purpose

Northstar can recover its information and services after data loss, ransomware, a cloud outage or other disruption, within agreed time limits, and stays secure while doing so.

## 2. Scope

The policy covers:

- the SaaS platform and its databases (Azure, UK and EU regions);
- Microsoft 365 data;
- finance and HR systems;
- the BC/DR plans for the people and processes that run them.

## 3. Recovery objectives

Recovery objectives follow the asset's availability rating (NSD-ISMS-009 §5). They are confirmed through a business impact analysis (BIA), reviewed every year. The table below gives the **defaults**. System-level objectives derived from the BIA ([NSD-ISMS-049](../10-business-continuity/49-business-impact-analysis.md)) are held in the [Recovery Objectives Register (NSD-ISMS-052)](../10-business-continuity/52-recovery-objectives-register.md); once approved, they apply instead.

| Availability rating | Example assets | Recovery time objective (RTO) | Recovery point objective (RPO) |
| --- | --- | --- | --- |
| High | Customer platform (AST-001, 007), identity (AST-009), keys (AST-006) | **4 hours or less** | **1 hour or less** |
| Medium | Microsoft 365, finance, support systems | 2 working days or less | 24 hours or less |
| Low | Documentation, contracts | 5 working days or less | 1 week or less |

## 4. Backup requirements

1. Every in-scope system has a documented backup arrangement: what is backed up, how often, retention, location, protection, monitoring and recovery objective.
2. Backup frequency meets the RPO. For the platform, this means continuous or hourly protection.
3. **At least one immutable, locked copy** of platform and Microsoft 365 backups is kept, which ransomware or an administrator cannot delete (T-14.1).
4. **Backup administration is a separate role.** Production administrators do not hold it, and it requires MFA (T-14.2).
5. Backups are encrypted and kept in the **same region as the source**, so EU customer data stays in the EU (R-02).
6. Retention periods are set with the Data Protection lead and customer contracts. They are proposed as 35 days of daily backups and 12 months of monthly backups, for MD approval.

## 5. Monitoring

- Backup jobs are monitored every day.
- A failed job for a High-availability system is investigated **the same working day**. Other failures are investigated the next working day.
- Success rate target: **at least 99%** over each 30 days (NSD-ISMS-021, 8.13).

## 6. Restore testing

1. The production database is fully restored into an isolated environment **at least once a year**, and after major changes. The test measures recovery against the RTO and RPO (T-14.3).
2. A sample of other systems is restored every quarter.
3. Every test records the result, the measured times, the integrity checks and any corrective actions.

## 7. Business continuity

1. The **BC/DR plan** (AST-019) covers:
    - roles and decision-making;
    - communication with staff and customers;
    - recovery steps for each High-availability system;
    - alternative working arrangements, such as staff working from home if the office is unavailable.
2. **A copy of the plan is kept offline**, so it can be used when Microsoft 365 is down.
3. **Regional failover** to the paired Azure region is documented in a runbook (T-09.1) and **tested at least annually** (T-09.2; Obj 8).
4. Climate and physical disruption scenarios are covered (EXT-12).

## 8. Security during disruption (Annex A 5.29)

Security controls stay in force during an incident and recovery:

- MFA, access control, logging and encryption are not bypassed to speed up recovery;
- any emergency deviation needs MD approval, is recorded, and is reversed and reviewed afterwards.

## 9. Measures

| Measure | Target |
| --- | --- |
| Backup job success over 30 days | 99% or higher |
| Annual production restore test within the 4-hour RTO and 1-hour RPO | Pass |
| Annual regional failover test within the 4-hour RTO | Pass |
| Platform backups with an immutable copy | 100% |

## 10. Related controls and risks

Annex A 5.29, 5.30, 8.13, 8.14 · Risks R-02, R-09, R-14 · Actions T-09.1, T-09.2, T-14.1, T-14.2, T-14.3

## 11. Approval

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

---

*Portfolio note: Draft only. This is not an approved or implemented policy.*
