# Northstar Digital Solutions Ltd — Recovery Objectives Register (RTO and RPO)

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-052 |
| Version | 0.2 — Proposed objectives for validation |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 5.30, 8.13, 8.14 |
| Status | **Simulated. All objectives are proposals. None has been validated, approved or demonstrated** |
| Derived from | [NSD-ISMS-049 BIA](49-business-impact-analysis.md) §4–5 |
| Used by | [NSD-ISMS-028 Backup and Business Continuity Policy](../05-policies/28-backup-business-continuity-policy.md) §3 · [NSD-ISMS-051 DRP](51-disaster-recovery-plan.md) · KPI-09 |
| Register owner | Information Security / GRC Analyst (maintains the register). Each objective is owned by the asset owner |
| Approver | Managing Director, with the BIA |
| Classification | Confidential |

---

## 1. Purpose and how objectives are set

This register is the **single place** where system-level recovery objectives are recorded. NSD-ISMS-028 §3 sets defaults by availability rating; once an objective here is approved, it applies instead.

Objectives are **derived, not chosen:**

1. The BIA (NSD-ISMS-049) sets each **activity's** RTO, RPO and MTPD from the impact over time.
2. Each **system's** required RTO is the shortest RTO of the activities that depend on it, and its required RPO is the smallest RPO of those activities.
3. The **proposed** objective must meet the requirement, or the gap is recorded and decided by the MD.
4. **Backups or replication must run at least as often as the RPO.** An hourly RPO cannot be met by a nightly backup.

| Term | Meaning |
| --- | --- |
| RTO | Target time to restore the system after disruption |
| RPO | Target maximum data loss, measured in time, back to the recovery point |
| MTPD | The point after which the impact on the activity becomes unacceptable (from the BIA). Every RTO must be shorter |
| **Achieved RTO / RPO** | What a test or real recovery actually measured. Only this shows capability |

## 2. Register

| # | System (asset) | Owner | Supports (BIA) | Required by BIA | Draft proposal | **Proposed objective** | How the RPO is met | Demonstrated? | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Identity and break-glass access (AST-009, AST-010) | IT Manager | A1, A3, A5 | RTO 1 h | 2 h / 30 min | **Break-glass sign-in: 1 h.** Entra ID itself is restored by Microsoft, so Northstar's objective is access through break-glass accounts. **Configuration RPO: 24 h** (conditional access, PIM and role settings) | Daily export of identity configuration (to be confirmed) | Quarterly break-glass test (T-13.2): results to be linked | Proposed |
| 2 | Keys and secrets (AST-006) | Head of Engineering | A1 | RTO 4 h | Not in draft | **RTO 4 h; RPO zero.** A lost encryption key means the data it protects cannot be recovered | Every key and secret version recoverable after deletion (to be confirmed) | Not tested separately | Proposed |
| 3 | Production environment (AST-007) | Head of Engineering | A1 | RTO 4 h | 4 h / 1 h (with the platform) | **RTO 4 h.** No RPO: the environment is rebuilt from code | Environment held as code in the repository | **Not evidenced:** failover test (T-09.2) due 1 Mar 2027; no result recorded | Proposed |
| 4 | Customer databases, UK and EU (AST-001) | Head of Engineering | A1 | RTO 4 h; RPO 1 h | 4 h / 1 h | **RTO 4 h; RPO 1 h.** EU data restored only to an EU region (R-02) | Continuous or hourly protection (028 §4) | **Partly:** KPI-09 Q2 2027, 3 of 4 recovery tests met the RTO and RPO; the 4th has no record | Proposed |
| 5 | Backups (AST-011) | IT Manager | A1, A5, A6, A7 | Available within 4 h, including in a regional outage | Not in draft | **Available within 4 h from outside the affected region** | Copy held outside the source region | **Not met:** backups are in the same region as the source (BIA gap G2) | **Gap:** for risk review (R-09, R-14) |
| 6 | Security logs (AST-012) | GRC Analyst | A3 | RTO 4 h | 4 h / 1 h | **RTO 4 h; RPO 1 h** | Logs forwarded continuously to the log store | Not tested | Proposed. **Differs from 028** (Medium: 2 working days) |
| 7 | Customer status channel, independent of the platform and Microsoft 365 | Customer Support Manager | A2 | RTO 1 h | Not in draft | **Available within 1 h** | Not applicable | **Not in place,** and not in the asset register (BIA gap G1) | **Gap** |
| 8 | Support ticketing (AST-013) | Customer Support Manager | A2 | RTO 1 h, **unless** item 7 exists | 12 h / 4 h | **2 working days; RPO 24 h, if item 7 is in place.** Without it, 1 h | Supplier backup (to be confirmed in 026) | Not tested | Proposed, conditional on item 7 |
| 9 | Microsoft 365 (AST-008) | IT Manager | A2, A5, A6 | 4 h for email (A2), unless item 7 exists; 2 working days for data | 8 h / 4 h | **Service: supplier-restored;** Northstar's objective is BCP workarounds within 1 h. **Data restore: 2 working days; RPO 24 h** | Daily backup of mail, SharePoint and Teams (AST-011) | Quarterly sample restores (028 §6): results to be linked | Proposed |
| 10 | Code repository and CI/CD (AST-004, AST-005) | Head of Engineering | A4, A8 | RTO 1 working day | 24 h / 8 h | **1 working day; RPO 24 h** | Repository copies and daily backup (to be confirmed) | Not tested | Proposed. **Differs from 028** (2 working days) |
| 11 | Finance and banking systems (AST-003) | Finance Manager | A6 | RTO 2 working days; MTPD 1 working day in payroll week | 3 business days / 24 h | **2 working days; RPO 24 h.** In a payroll week the bank's own service is used (BCP §5) | Supplier-hosted; supplier backup (026) | Not tested | Proposed |
| 12 | HR system (AST-002) | HR Manager | A7, A7a | RTO 2 working days; leavers the same day | 3 business days / 24 h | **2 working days; RPO 24 h.** The manual leaver fallback (BCP §5) runs from day 1 | Supplier-hosted; supplier backup (026) | Not tested | Proposed |

## 3. Objectives that depend on suppliers

For Entra ID, Microsoft 365, the finance system and the HR system, **Northstar cannot restore the service itself.** An RTO for these is a statement of need, not something Northstar controls. Two things make it meaningful:

1. **The supplier's commitment.** Its SLA and recovery arrangements are checked in the supplier assessment (NSD-ISMS-026), and where they fall short, the gap is recorded as a risk.
2. **Northstar's own fallback.** The BCP workaround (NSD-ISMS-050 §5) keeps the activity running until the supplier recovers.

## 4. Conflicts this register resolves or records

| Conflict | Resolution |
| --- | --- |
| The draft gave support systems 12 hours, the BIA needs customer communication within 1 hour, and NSD-ISMS-028 gives 2 working days | Separated into the **status channel** (1 h, item 7) and the **ticketing system** (2 working days, if item 7 exists) |
| The draft gave finance an RTO of 3 business days, equal to its MTPD | RTO 2 working days, leaving a margin. An RTO equal to the MTPD leaves no time for anything to go wrong |
| The draft gave identity a 30-minute RPO | Entra ID data is held by Microsoft. Northstar's RPO applies to its own configuration |
| Security logs and CI/CD are rated Medium in NSD-ISMS-028 | Shorter objectives proposed here. If approved, the asset availability ratings (NSD-ISMS-009) are raised to match |
| Keys and backups were missing from the draft | Added. Every other recovery depends on them |

## 5. Validation

| Check | Who | Evidence |
| --- | --- | --- |
| Against the BIA (activity RTO, RPO, MTPD) | GRC Analyst | NSD-ISMS-049 §4 |
| Against customer SLAs and DORA terms | Sales lead, with the Data Protection lead | Contract register (NSD-ISMS-005) |
| Technical feasibility: backup frequency, replication, rebuild time | Asset owner | Configuration evidence |
| Supplier commitments | Finance Manager | Supplier assessments (NSD-ISMS-026) |
| People able to carry out the recovery | Asset owner | Runbook trained to at least two people (BIA gap G4) |
| Cost of meeting the objective | Finance Manager | Estimate, for the MD's decision |
| Approval | Managing Director | With the BIA, by 30 Nov 2027 |

## 6. Status values

| Status | Meaning |
| --- | --- |
| Proposed | Derived from the BIA; not yet validated |
| Validated | Checked against all items in section 5 |
| Approved | Approved by the MD |
| **Demonstrated** | A test has measured an achieved RTO and RPO within the objective, in the last 12 months |
| Gap | The objective cannot currently be met; recorded and routed |

Only **Demonstrated** shows capability. An approved objective with no test is still a target.

## 7. Review

Reviewed with the BIA every year, and within 10 working days of:

- a change to the BIA;
- a new or changed customer commitment;
- a platform, backup or supplier change;
- any test or real recovery that missed its objective.

## 8. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-048) | Nine services with illustrative RTO, RPO and priority |
| 0.2 | Numbered NSD-ISMS-052. One register owner (the GRC Analyst) and one owner for each objective, replacing "IT Manager / GRC Analyst". Every objective **derived from the BIA,** with the draft's values kept for comparison. "Critical/High" priority removed, because recovery order is set in BIA §7 and "Critical" is an asset tier. Added keys, backups and a customer status channel. Supplier-restored services handled separately. Columns added for how the RPO is met and what has been demonstrated, using portfolio records only. Conflicts with the draft and with NSD-ISMS-028 resolved or recorded. Validation with named roles; review triggers made specific. |

---

*Portfolio disclaimer: All recovery objectives are illustrative proposals. They have not been validated against real systems or approved by Northstar management.*
