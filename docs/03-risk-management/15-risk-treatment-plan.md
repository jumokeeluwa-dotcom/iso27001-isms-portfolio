# Northstar Digital Solutions Ltd — Information Security Risk Treatment Plan

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-015 |
| Version | 0.3 — Draft for risk owner and MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 6.1.3(e)–(f), 8.3) |
| Related documents | [NSD-ISMS-012 Methodology](12-risk-assessment-methodology.md) · [NSD-ISMS-013 Scoring Matrix](13-risk-scoring-matrix.md) · [NSD-ISMS-014 Risk Register](14-risk-register.md) · NSD-ISMS-016 Acceptance Criteria · Statement of Applicability (planned) |
| Plan owner | Information Security / GRC Analyst |
| Approver | Managing Director. Each risk owner approves the treatment and target residual for their risks (clause 6.1.3(f)) |
| Planning assumption | Plan approved on **1 December 2026**. All due dates count from that date |
| Classification | Confidential |

---

## 1. Summary

The plan treats all 20 risks in NSD-ISMS-014 through **36 actions** in four priority groups. Every action states the evidence that proves it is complete. An auditor or manager can ask for that evidence, rather than accepting a statement that the work is done.

| Priority | Risks | Actions | Due by |
| --- | --- | --- | --- |
| 🟥 P1 — Very High residual | R-06, R-12, R-14, R-19 | 11 | Mostly 18 December 2026; automation and testing by 29 January 2027 |
| 🟧 P2 — High residual with Severe impact | R-01, R-07, R-08, R-09, R-13, R-16, R-17 | 14 | 29 January 2027; failover test by 1 March 2027 |
| 🟧 P3 — Other High residual | R-02, R-03, R-04, R-05, R-10, R-11, R-15, R-18 | 10 | 1 March 2027 |
| 🟨 P4 — Medium residual | R-20 | 1 | 31 March 2027 |

If every action is delivered and verified, the residual profile moves from **4 Very High, 15 High and 1 Medium** to the target of **0 Very High, 2 High, 14 Medium and 4 Low** (NSD-ISMS-014 §5).

## 2. Rules for this plan

| Rule | Detail |
| --- | --- |
| Risk owner and action owner | The **risk owner** (NSD-ISMS-014) is accountable and approves the treatment. The **action owner** does the work, often a custodian team (NSD-ISMS-007) |
| Specific actions | Each action names what changes, where, and to what standard. "Review", "establish" or "consider" alone is not an action |
| Completion evidence | An action is complete only when its evidence is filed **and** verified by the GRC Analyst. Owners do not mark their own actions complete |
| Independent verification | Where the GRC Analyst owns the risk (R-15) or the action (T-16.2, T-18.1), the evidence is verified by the internal auditor or the MD |
| Re-scoring | After verification, the risk is re-scored using the control credit rule (NSD-ISMS-012 §5). Completing the actions does not automatically deliver the target score |
| Interim controls | Where the permanent fix takes longer, a dated interim control reduces exposure in the meantime |
| Annex A references | Candidate controls from NSD-ISMS-010. The final selection is justified in the Statement of Applicability (clause 6.1.3(b)–(d)) |

## 3. Treatment actions

### 3.1 P1 — Very High residual risks

| Action | Risk | Action | Completion evidence | Annex A | Action owner | Due |
| --- | --- | --- | --- | --- | --- | --- |
| T-06.1 | R-06 | Move every secret from code and pipeline variables into Key Vault. Rotate every secret found | Secret inventory before and after; rotation log showing every exposed secret rotated | 8.24, 5.17 | DevOps team | 18 Dec 2026 |
| T-06.2 | R-06 | Turn on secret scanning with push protection for **all** repositories; scan the full commit history | Repository settings export showing 100% coverage; history scan report with all findings closed | 8.4, 8.28 | DevOps team | 18 Dec 2026 |
| T-06.3 | R-06 | Restrict Key Vault access to named managed identities; send access logs to Log Analytics | Key Vault role assignment export; diagnostic settings; sample access log | 8.2, 8.15 | DevOps team | 15 Jan 2027 |
| T-12.1 | R-12 | **Interim:** each working day, compare HR's leaver list with active Entra ID accounts and disable leavers the same day | Daily reconciliation log, from the start date until T-12.3 is live | 5.18, 6.5 | IT Operations | Starts 4 Dec 2026 |
| T-12.2 | R-12 | One-off sweep of everyone who left in the last 12 months: Entra ID, database users, repository tokens and guest accounts | Sweep report listing each account found and the date it was removed | 5.18 | IT Operations | 11 Dec 2026 |
| T-12.3 | R-12 | Automate removal: a leaver record in the HR system disables the Entra ID account and revokes sessions by the end of their last working day | Workflow configuration; test record for 3 leavers showing the time of removal | 5.16, 5.18, 6.5 | IT Manager, with HR Manager | 29 Jan 2027 |
| T-14.1 | R-14 | Turn on immutable, locked backup storage for production databases and Microsoft 365 backups | Backup vault configuration showing immutability locked | 8.13 | IT Operations | 18 Dec 2026 |
| T-14.2 | R-14 | Create a separate backup administrator role that production administrators do not hold; require MFA | Role assignment export showing no overlap between the two roles | 8.2, 5.3 | IT Operations | 18 Dec 2026 |
| T-14.3 | R-14 | Fully restore the production database into an isolated environment and measure against the 4-hour RTO and 1-hour RPO | Restore test report with measured times, signed off by the Head of Engineering | 8.13, 5.30 | IT Operations, with DevOps team | 29 Jan 2027 |
| T-19.1 | R-19 | Approve one enterprise AI tool with contractual data protection. Publish the AI rule from NSD-ISMS-008 §4: Restricted data is prohibited | Approved tool record and contract terms; policy acknowledgement by at least 95% of staff | 5.10 | IT Manager, with GRC Analyst | 18 Dec 2026 |
| T-19.2 | R-19 | Block unapproved AI sites through web filtering, and block uploads of Restricted-labelled content with DLP | Blocking policy export; DLP test showing a Restricted file upload blocked | 8.12, 8.23 | IT Operations | 15 Jan 2027 |

### 3.2 P2 — High residual risks with Severe impact

| Action | Risk | Action | Completion evidence | Annex A | Action owner | Due |
| --- | --- | --- | --- | --- | --- | --- |
| T-01.1 | R-01 | Replace engineers' standing read access to the production database with just-in-time, approved, time-limited access | Role export showing no standing read access; access approval log | 5.15, 8.2, 8.3 | DevOps team | 29 Jan 2027 |
| T-01.2 | R-01 | Send database audit logs to Log Analytics, with an alert on bulk data exports | Diagnostic settings; record of a test alert being raised and received | 8.15, 8.16 | DevOps team | 29 Jan 2027 |
| T-07.1 | R-07 | Pin dependency versions and fail any build with a critical dependency vulnerability | Pipeline configuration; record of a build blocked by a test vulnerability | 8.25, 8.28 | DevOps team | 29 Jan 2027 |
| T-07.2 | R-07 | Reduce pipeline permissions to least privilege; require a second person to approve production deployments | Pipeline permission export; deployment approval log | 8.32, 5.3 | DevOps team | 29 Jan 2027 |
| T-08.1 | R-08, R-02 | Assign an Azure Policy initiative in deny mode: no public storage, no public database endpoints, and allowed locations limited to the UK and EU regions. Fix existing breaches | Policy assignment export; compliance report at 95% or higher | 8.9, 5.23 | DevOps team | 29 Jan 2027 |
| T-08.2 | R-08 | Review high-severity Defender for Cloud recommendations weekly; close each within 14 days | Weekly review log; closure times report | 8.16 | DevOps team | 29 Jan 2027, then weekly |
| T-09.1 | R-09 | Write the failover runbook for the paired Azure region, with roles, steps and decision points | Approved runbook stored with the BC/DR plans (AST-019) | 5.30, 8.14 | DevOps team | 29 Jan 2027 |
| T-09.2 | R-09 | Carry out a failover test and measure recovery against the 4-hour RTO | DR test report with measured recovery time and lessons learned | 5.29, 5.30 | DevOps team, with IT Operations | 1 Mar 2027 |
| T-13.1 | R-13 | Turn on just-in-time privileged access (Entra PIM) for all admin roles. Leave no standing Global Administrators except 2 break-glass accounts | PIM configuration; role assignment report | 8.2 | IT Operations | 29 Jan 2027 |
| T-13.2 | R-13 | Store break-glass credentials in the vault; alert on any use; test quarterly | Vault record; alert rule; first quarterly test record | 5.17, 8.15 | IT Operations | 29 Jan 2027 |
| T-16.1 | R-16 | List every supplier and guest account. Remove unused ones, enforce MFA, and set a 90-day expiry with an internal sponsor | Guest access review report: accounts removed, MFA coverage, expiry settings | 5.18, 5.19 | IT Operations | 29 Jan 2027 |
| T-16.2 | R-16 | Complete security due diligence for critical suppliers (IP-10 to IP-12): certificate review or questionnaire | Supplier assessment records (measure for Obj 9) | 5.19, 5.22 | GRC Analyst | 29 Jan 2027 |
| T-17.1 | R-17 | Enforce the 14-day deadline for critical vulnerabilities with an exception process; report overdue items weekly to the Steering Group | Patching performance report showing at least 95% of critical vulnerabilities fixed within 14 days (Obj 7) | 8.8 | DevOps team, with IT Operations | 29 Jan 2027 |
| T-17.2 | R-17 | Put a web application firewall in front of all internet-facing services | WAF configuration covering every public endpoint | 8.20, 8.21 | DevOps team | 29 Jan 2027 |

### 3.3 P3 — Other High residual risks

| Action | Risk | Action | Completion evidence | Annex A | Action owner | Due |
| --- | --- | --- | --- | --- | --- | --- |
| T-02.1 | R-02 | List every copy of EU customer data, including analytics and replicas; move any outside the EU region. Location rule enforced by T-08.1 | Data location inventory signed off by the Data Protection lead | 5.31, 5.34 | DevOps team, with Data Protection lead | 1 Mar 2027 |
| T-03.1 | R-03 | Remove inherited permissions on the HR site; limit it to the HR group; review membership quarterly | Permissions report; first quarterly review record | 5.15, 5.18 | IT Operations | 1 Mar 2027 |
| T-03.2 | R-03 | Apply the Restricted sensitivity label, with encryption, to all HR files (NSD-ISMS-008 §5) | Purview label report for the HR site | 5.13 | IT Operations | 1 Mar 2027 |
| T-04.1 | R-04 | Build call-back verification on a known number and a second approver into the finance system for every bank detail change | Workflow configuration; test record for 5 sample changes | 5.3 | Finance team | 1 Mar 2027 |
| T-05.1 | R-05 | Enforce branch protection and mandatory review on **all** repositories | Repository settings export showing 100% coverage | 8.4, 8.32 | DevOps team | 1 Mar 2027 |
| T-10.1 | R-10 | Block legacy authentication; require phishing-resistant MFA for administrators through Conditional Access | Conditional Access policy export; sign-in logs showing no legacy authentication | 8.5 | IT Operations | 1 Mar 2027 |
| T-10.2 | R-10 | Raise security awareness training completion to 95% and run a quarterly phishing simulation (Obj 5) | Training completion report; first simulation results | 6.3 | HR Manager, with GRC Analyst | 1 Mar 2027 |
| T-11.1 | R-11 | Replace service account passwords with managed identities, or restrict them by Conditional Access | MFA and managed-identity coverage report showing 100% | 5.17, 8.5 | IT Operations | 1 Mar 2027 |
| T-15.1 | R-15 | Make logs unchangeable by administrators: send them to immutable archive storage and keep them for 12 months | Archive configuration; role assignments showing no administrator can delete logs | 8.15 | IT Operations | 1 Mar 2027 |
| T-18.1 | R-18 | Approve the incident and breach procedure, including Northstar's duty as processor to notify customers. Test it with a tabletop exercise | Approved procedure; exercise report showing breach assessment completed within 24 hours | 5.24–5.26, 6.8 | GRC Analyst, with Data Protection lead | 1 Mar 2027 |

### 3.4 P4 — Medium residual risks

| Action | Risk | Action | Completion evidence | Annex A | Action owner | Due |
| --- | --- | --- | --- | --- | --- | --- |
| T-20.1 | R-20 | Raise device encryption from 96% to 100%, and block unencrypted devices through Conditional Access | Intune compliance report showing 100% encrypted | 8.1 | IT Operations | 31 Mar 2027 |

## 4. Target residual risk and approvals

| Risk | Risk owner | Current | Target | Approval needed |
| --- | --- | --- | --- | --- |
| R-06 | Head of Engineering | 🟥 20 | 🟨 8 | Risk owner |
| R-12 | HR Manager | 🟥 16 | 🟨 8 | Risk owner |
| R-14 | IT Manager | 🟥 20 | 🟨 6 | Risk owner |
| R-19 | Managing Director | 🟥 16 | 🟨 8 | Risk owner |
| R-01 | Head of Engineering | 🟧 15 | 🟨 8 | Risk owner |
| R-07 | Head of Engineering | 🟧 15 | 🟧 10 | Risk owner, **plus Steering Group with MD approval** (High target, impact 5; NSD-ISMS-016 record AR-01) |
| R-08 | Head of Engineering | 🟧 15 | 🟨 8 | Risk owner |
| R-09 | Head of Engineering | 🟧 10 | 🟨 6 | Risk owner |
| R-13 | IT Manager | 🟧 15 | 🟧 10 | Risk owner, **plus Steering Group with MD approval** (High target, impact 5; NSD-ISMS-016 record AR-02) |
| R-16 | Finance Manager | 🟧 15 | 🟨 8 | Risk owner |
| R-17 | Head of Engineering | 🟧 15 | 🟨 8 | Risk owner |
| R-02 | Data Protection lead | 🟧 12 | 🟩 4 | Risk owner |
| R-03 | HR Manager | 🟧 12 | 🟨 8 | Risk owner |
| R-04 | Finance Manager | 🟧 12 | 🟨 6 | Risk owner |
| R-05 | Head of Engineering | 🟧 12 | 🟨 8 | Risk owner |
| R-10 | IT Manager | 🟧 12 | 🟨 8 | Risk owner |
| R-11 | IT Manager | 🟧 12 | 🟨 8 | Risk owner |
| R-15 | GRC Analyst | 🟧 12 | 🟩 4 | Steering Group (the GRC Analyst does not accept risk) |
| R-18 | Data Protection lead | 🟧 12 | 🟩 4 | Risk owner |
| R-20 | IT Manager | 🟨 8 | 🟩 4 | Risk owner |

## 5. Resources and capacity

| Need | For | Decision needed from |
| --- | --- | --- |
| Entra ID P2 licences for admins (PIM) | T-13.1 | MD (budget) |
| Immutable backup storage costs | T-14.1 | MD (budget) |
| Web filtering and DLP for AI sites, if not covered by current Microsoft 365 licences | T-19.2 | IT Manager to confirm; MD if extra cost |
| Integration between the HR system and Entra ID | T-12.3 | IT Manager, with HR Manager |
| Temporary extra DevOps and IT Operations time in December–January | 25 P1 and P2 actions | Steering Group (charter §8.1) |

**Capacity warning.** DevOps and IT Operations own 30 of the 36 actions, and P1 falls over the December holiday period. Without temporary extra capacity, P2 dates are at risk. This is the same concentration flagged in NSD-ISMS-007, 010 and 014, and the Steering Group must decide on it when approving this plan.

## 6. Treatment option terms: Modify or Mitigate?

This plan uses **Modify**, matching NSD-ISMS-012 and NSD-ISMS-014.

| Term | Source | Meaning |
| --- | --- | --- |
| **Modify** | ISO/IEC 27005:2022 (risk modification); ISO 31000 | Change the likelihood **or** the impact through controls |
| **Mitigate** | Common industry usage; NIST | Same meaning in practice |

ISO/IEC 27001:2022 does not prescribe names for the treatment options. Either term is acceptable if it is used **consistently** across the methodology, register and plan. Northstar uses **Modify (mitigate)** as its formal term, so readers familiar with either word understand it.

The ISO term is also the more accurate one. "Modify" covers treatments that reduce impact as well as likelihood, such as tested failover (R-09) and immutable backups (R-14). "Mitigate" is often heard as "prevent".

## 7. Implementation tracking

The working tracker records these fields for each action:

| Field | Values or content |
| --- | --- |
| Status | Not started · In progress · Blocked · Complete (evidence filed) · Verified |
| Actual completion date | Date the evidence was filed |
| Evidence reference | Location in the GRC evidence repository |
| Verified by and date | GRC Analyst, or internal auditor or MD for GRC-owned actions |
| Delay or exception | Reason, new date, and approval for the change |
| Re-scored residual | L × I after verification, using the control credit rule |
| Risk-owner review | Date and outcome |

All 36 actions are currently **Not started**.

**Reporting**

- P1 actions are tracked weekly by the GRC Analyst with the action owners.
- The Steering Group sees overall progress, overdue actions and re-scored risks at each meeting.
- Any P1 action that slips is escalated to the MD within 2 working days (NSD-ISMS-013 §4).

## 8. Statement of Applicability link

The Annex A references are candidate controls, not evidence of implementation. Northstar determines which controls are necessary from its risk treatment decisions and requirements (clause 6.1.3(b)). It then compares them with Annex A to check that nothing is missing (6.1.3(c)), and records every Annex A control in the Statement of Applicability, applicable or not, with its justification and implementation status (6.1.3(d)).

## 9. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the plan, resources and capacity decision | Pending | |
| Risk owners (NSD-ISMS-017) | Approve treatment and target residual for their risks | Pending | |
| ISMS Steering Group | Accepts the High targets for R-07 and R-13 with MD approval; approves the R-15 target | Pending | |
| Information Security / GRC Analyst | Prepared the plan | Prepared | |

## 10. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-013) | 10 risks with planned actions and relative targets (30–60 days) |
| 0.1 | Numbered NSD-ISMS-015; 013 is the scoring matrix. Risk IDs aligned with NSD-ISMS-014. Coverage extended to all 20 risks in four priority groups, with the 4 Very High risks first. "Review" and "establish" actions replaced by 36 specific actions, each with completion evidence and dated deadlines. Action owners changed to custodian teams from NSD-ISMS-007; the Cloud Administrator, Security Lead, Procurement Manager, Operations Director and Department Managers roles removed. Approver changed from Senior Management to the MD and risk owners. Added interim controls, independent verification, target residual approvals, resource and capacity needs, and the Modify/Mitigate note. |
| 0.3 | Risk owners for R-02, R-12, R-18 and R-19 updated to match NSD-ISMS-017. Verification rule now covers GRC-owned actions. |
| 0.2 | Approval authorities aligned with NSD-ISMS-016: R-07 and R-13 targets need Steering Group with MD approval (impact 5). |

---

*Portfolio note: Actions, dates and evidence are simulated for a fictional organisation. They are proposed treatments, not evidence of implementation.*
