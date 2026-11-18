# Northstar Digital Solutions Ltd — Disaster Recovery Plan

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-051 (asset AST-019, with NSD-ISMS-050) |
| Version | 1.0 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 5.30, 8.13, 8.14, 5.29, 5.28, 8.15, 8.16 |
| Status | **Simulated. No actual recovery or technical test is claimed** |
| Related documents | [NSD-ISMS-049 BIA](49-business-impact-analysis.md) · [NSD-ISMS-050 BCP](50-business-continuity-plan.md) · [NSD-ISMS-028 Backup and Business Continuity Policy](../05-policies/28-backup-business-continuity-policy.md) · [NSD-ISMS-027 Incident Management](../05-policies/27-incident-management-policy.md) · Risks R-09, R-14, R-02 · Actions T-09.1, T-09.2, T-13.2, T-14.1–14.3 |
| Owner | IT Manager (owner of the backups, AST-011) |
| Platform runbooks | Head of Engineering (owner of AST-001, AST-006, AST-007) |
| Approver | Managing Director |
| Classification | Confidential |

---

## 1. Purpose

This plan sets out how Northstar restores its IT services and data **safely** after a disruption, within the RTOs and RPOs in NSD-ISMS-049, and **without restoring a compromised system or breaking a security control** along the way.

Detailed technical steps are in runbooks, held with this plan, including offline: the regional failover runbook (T-09.1) and the database restore procedure (T-14.3). This plan decides **which** runbook to use, **who** acts, and **what must be true** before service resumes.

## 2. Scope

| In scope | Assets |
| --- | --- |
| Customer platform: Azure production environment and databases (UK and EU regions) | AST-007, AST-001 |
| Secrets and keys | AST-006 |
| Identity and privileged access | AST-009, AST-010 |
| Backups | AST-011 |
| Security logging and monitoring | AST-012 |
| Microsoft 365 | AST-008 |
| Code repository and CI/CD | AST-004, AST-005 |
| Finance and HR systems (supplier-hosted) | AST-003, AST-002 |

Northstar has no data centre or office network of its own to recover. "Network" here means Azure network configuration, which is rebuilt from code with the environment. Staff use home or office internet; the office has no systems that customers depend on.

## 3. Roles

People who restore a system do not also sign off its security. That is the same independence rule used for audits and corrective actions.

| Role | Held by | Responsibility |
| --- | --- | --- |
| DR lead, platform | Head of Engineering, with the DevOps team | Failover; environment rebuild; database restore; application testing |
| DR lead, corporate IT | IT Manager, with IT Operations | Identity, break-glass, Microsoft 365, endpoints, backups |
| Security validation | GRC Analyst (incident manager) | Reviews the evidence that restored systems are clean, before return to service. **Does not restore systems** |
| Forensic support | External incident response provider, through the cyber insurer (IP-13), for ransomware or a confirmed breach | Evidence preservation; finding the time of compromise |
| Business acceptance | The BIA activity owner (NSD-ISMS-049 §4); the Customer Support Manager checks customer-facing functions for A1 | Confirms the activity works |
| Return-to-service approval | Managing Director, for Severity 1 (NSD-ISMS-027 §3) | Approves going live |

Until a deputy is named (proposed action MRA-2027-06), both DR leads are single points of failure (BIA gap G4).

## 4. Choose the recovery path

Recovery differs a great deal by cause, and choosing the wrong path is a common DR failure, for example failing over a ransomware infection into the second region.

| Scenario | Path | Key risk |
| --- | --- | --- |
| **Azure regional outage** (R-09) | Fail over to the paired region (T-09.1 runbook). EU data recovers only to an EU region (R-02) | Backups held in the same region may be unavailable too (BIA gap G2) |
| **Ransomware or destructive attack** (R-14) | **Do not fail over** (replication may carry the damage). Isolate; preserve evidence; rotate credentials; rebuild from code; restore data from an immutable backup taken **before** the compromise | Restoring a backup that already contains the attacker |
| **Data corruption or accidental deletion** | Point-in-time restore of the affected data to just before the event | Choosing the wrong restore point |
| **Entra ID or Microsoft 365 outage** (EXT-05) | Supplier-led recovery: monitor Microsoft status; use break-glass accounts where they work; BCP communication without M365 (NSD-ISMS-050 §6) | Nothing to restore; staff and admin access lost until Microsoft recovers |
| **Supplier-hosted system outage** (finance, HR, code repository) | Supplier recovery; BCP workarounds (NSD-ISMS-050 §5) | The supplier's own RTO may not meet the BIA (checked in supplier assessments, NSD-ISMS-026) |

## 5. Recovery stages

| Stage | Actions | Records |
| --- | --- | --- |
| **1. Assess and decide** | Confirm what failed and the cause. **Is it an attack?** If unsure, treat it as one. Choose the path in section 4. The DR lead activates DR, informing the MD | Time of disruption; time of decision; chosen path and why |
| **2. Contain and secure access** | Isolate affected systems. Preserve logs and images **before** changing anything (A 5.28). Sign in with break-glass accounts if normal admin access may be compromised. **If an attack is involved: rotate administrator credentials, Key Vault secrets and keys, and revoke all sessions** | Evidence list; credential rotation log |
| **3. Choose a clean recovery point** | Identify when the compromise started (from logs and forensics). Select the newest backup **before** that time. Check the backup is intact and was not reachable by the attacker (T-14.1 immutability; T-14.2 separate backup role) | Selected restore point and why. **Achieved RPO** = time of disruption minus restore point |
| **4. Restore in dependency order** | Following the BIA order (049 §7): identity and break-glass → Key Vault → environment, rebuilt from code with the **security baseline applied as it is built**, not added afterwards → databases → application → logging → other services | Start and end time of each step |
| **5. Validate** | Technical: data integrity checks and application tests. Security: no indicators of compromise; configuration matches the baseline; admin accounts and permissions as expected; logging and alerts working. Business: the activity owner confirms it works | Test results; GRC Analyst's security validation; owner acceptance |
| **6. Resume** | MD approves return for Severity 1. Monitor closely for 72 hours. Customers told the outcome, **including any data lost** (BCP §6) | Approval; **achieved RTO** = time of disruption to return to service |
| **7. Review** | Lessons-learned review within 10 working days (027 §10). If the achieved RTO or RPO was missed, it is recorded as a nonconformity (NSD-ISMS-034) | Review record |

**Why the restore point matters.** Ransomware often lies hidden for days before it encrypts anything. The newest backup may already contain it. A clean restore point may be older than the 1-hour RPO allows. That means data loss beyond the RPO: impact 5 on the NSD-ISMS-013 scale, an MD decision, and something customers must be told. The plan accepts this rather than restoring an infected system to meet a target.

## 6. Recovery prerequisites

| Prerequisite | Requirement | Current status (portfolio records) |
| --- | --- | --- |
| Immutable backups | Backup storage locked against deletion and changes (T-14.1) | Planned, due 18 Dec 2026; completion not recorded |
| Separate backup administration | Production administrators cannot delete backups (T-14.2) | Planned; completion not recorded |
| Backup location | A copy reachable when the primary region is down | **Same region as the source** (AST-011): BIA gap G2 |
| Break-glass access | Stored in the vault; alert on use; tested quarterly (T-13.2) | Planned; test results to be checked |
| Environment as code | The platform can be rebuilt from the repository with its security baseline | To be confirmed by the Head of Engineering |
| Offline copies | This plan, the runbooks and contact lists usable without Microsoft 365 | Required by NSD-ISMS-028 §7 |
| Competent people | At least two people able to run each runbook | Not met: BIA gap G4 |

Where a prerequisite is not in place, the RTO in NSD-ISMS-049 is a target the plan cannot yet be relied on to meet. That is reported, not assumed away.

## 7. Security during recovery (Annex A 5.29)

- No security control is switched off to recover faster. Any emergency deviation needs MD approval, is logged, and is reversed afterwards (NSD-ISMS-028 §8).
- Restored systems use the current security baseline, not the configuration at the time of the backup.
- EU customer data recovers only to an EU region (R-02).
- Evidence is preserved before systems are wiped or rebuilt.

## 8. Testing

| Test | Frequency | Pass criterion | KPI |
| --- | --- | --- | --- |
| Full production database restore into an isolated environment (T-14.3) | Annually, and after major changes (028 §6) | Within the **4-hour RTO** and **1-hour RPO**, measured | KPI-09 |
| Regional failover (T-09.2) | Annually (028 §7) | Within the 4-hour RTO; EU data stays in the EU | KPI-09 |
| Sample restore of other systems | Quarterly (028 §6) | Within each system's RTO | KPI-09 |
| Break-glass sign-in (T-13.2) | Quarterly | Sign-in works; alert fires | — |
| Ransomware recovery walk-through | Annually, with the BCP tabletop | Clean restore point chosen and credentials rotated, in the right order | — |

Every test records the measured times, the restore point, the integrity checks and the actions. **A test with no record counts as a failure** (KPI-09; NSD-ISMS-044). Completing a restore is not a pass; meeting the RTO and RPO is.

## 9. Recovery records

For each activation or test: activation record and chosen path; the single incident timeline (NSD-ISMS-027); evidence preserved; credential rotation log; restore point selected and the reason; integrity and security validation results; business acceptance; MD approval; **achieved RTO and RPO**; lessons learned and actions. Kept for 3 years, classified Confidential.

## 10. Maintenance

Reviewed annually; after every activation or test; and within 10 working days of any major platform, backup or identity change, or any change to the BIA.

## 11. Approval

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

---

*Portfolio disclaimer: Simulated DRP. No actual system recovery or technical test is claimed.*
