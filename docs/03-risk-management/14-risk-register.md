# Northstar Digital Solutions Ltd — Information Security Risk Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-014 |
| Version | 0.3 — Provisional: scores to be confirmed once NSD-ISMS-016 is approved |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 6.1.2, 8.2) |
| Related documents | [NSD-ISMS-010 Risk Mapping](../02-asset-management/10-asset-risk-mapping.md) · [NSD-ISMS-012 Methodology](12-risk-assessment-methodology.md) · [NSD-ISMS-013 Scoring Matrix](13-risk-scoring-matrix.md) · NSD-ISMS-015 Treatment Plan · NSD-ISMS-016 Acceptance Criteria · NSD-ISMS-017 Ownership Register |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director, with each risk owner for their risks |
| Review frequency | By band: Very High monthly, High quarterly, Medium six-monthly, Low annually (NSD-ISMS-012 §9) |
| Classification | Confidential |

---

## 1. Summary

The register holds 20 risks. Their **current residual** profile is **4 Very High, 15 High and 1 Medium**.

Four risks need escalation to the MD within 2 working days (NSD-ISMS-013 §4):

| Risk | Scenario | Current score |
| --- | --- | --- |
| R-06 | Secrets in code or pipelines | 20 |
| R-14 | Ransomware destroys backups | 20 |
| R-12 | Leavers keep access | 16 |
| R-19 | Restricted data pasted into unapproved AI tools | 16 |

If the treatment plan is delivered, the **target** profile is 2 High, 14 Medium and 4 Low. The two risks still High after treatment (R-07 and R-13) need explicit acceptance under NSD-ISMS-016.

**Why the scores are high.** Residual scores are reduced only for controls with test evidence (the control credit rule, NSD-ISMS-012 §5). Northstar's ISMS is new, so few controls have been tested yet. The scores reflect what can be proven, not what is believed. The 1.0 draft reduced every residual score while marking every control "(verify)". That would have overstated Northstar's security, so it is corrected here.

## 2. Basis and assumptions

| Item | Basis |
| --- | --- |
| Scales and bands | NSD-ISMS-013 v0.1 |
| Period | Likelihood within 12 months |
| Control status | **Simulated for this portfolio.** E = Effective (tested); P = Partially effective; U = Untested (no credit); N = Not in place. In a real assessment each status cites a test record |
| Sources | NSD-ISMS-010 scenarios (ARM), context issues (NSD-ISMS-002) and a process and supplier review |
| Approval order | NSD-ISMS-016 is not yet approved. Clause 6.1.2(a) requires the criteria first, so these scores are provisional until then |

## 3. Risk scenarios

| ID | Risk scenario | Source | Assets | Risk owner |
| --- | --- | --- | --- | --- |
| R-01 | An attacker uses a compromised staff account with broad database access to exfiltrate data belonging to several customers, causing a reportable breach | ARM-01 | AST-001, AST-009 | Head of Engineering |
| R-02 | EU customer data is copied or processed outside the EU region, e.g. in analytics or replicas, breaching EU GDPR transfer rules and customer contracts | ARM-02 | AST-001, AST-007 | Data Protection lead |
| R-03 | An insider or compromised account reaches HR records through broad SharePoint permissions, exposing employee personal and bank data | ARM-03 | AST-002, AST-008 | HR Manager |
| R-04 | Business email compromise persuades finance staff to change supplier bank details, causing a fraudulent payment | ARM-04 | AST-003 | Finance Manager |
| R-05 | Stolen developer credentials are used to push a malicious change to a repository without branch protection, which reaches production | ARM-05 | AST-004, AST-005 | Head of Engineering |
| R-06 | Secrets held in code or pipeline variables are found and used to reach production data and services | ARM-06, ARM-08 | AST-006, AST-004 | Head of Engineering |
| R-07 | A compromised third-party dependency or build tool injects malicious code into a release shipped to all customers | ARM-07 | AST-005 | Head of Engineering |
| R-08 | An Azure misconfiguration, such as a public storage endpoint, exposes customer data or services to the internet | ARM-09 | AST-007 | Head of Engineering |
| R-09 | An Azure regional outage takes the platform offline for more than 24 hours, because failover to the paired region has never been tested | ARM-10 | AST-007, AST-019 | Head of Engineering |
| R-10 | A phishing email captures a Microsoft 365 session, and the attacker reads mailboxes and SharePoint files holding Restricted data | ARM-11 | AST-008 | IT Manager |
| R-11 | Password spraying compromises an account not covered by MFA, such as a service account, giving access to company systems | ARM-13 | AST-009 | IT Manager |
| R-12 | A leaver or contractor keeps access to company systems and customer data because removal depends on an informal HR-to-IT email | ARM-14 | AST-009, AST-001 | HR Manager |
| R-13 | Administrator credentials are stolen or misused, giving full control of Azure or Microsoft 365 | ARM-15 | AST-010 | IT Manager |
| R-14 | Ransomware encrypts production **and** backups reachable with the same administrator credentials, so data cannot be restored within the RTO | ARM-16, ARM-17 | AST-011, AST-001 | IT Manager |
| R-15 | An attacker or administrator deletes or alters logs, or logs expire after 30 days, so Northstar cannot tell whether a breach happened | ARM-18 | AST-012 | GRC Analyst |
| R-16 | A compromised supplier account, such as an MSP or contractor guest account, gives an attacker access to Northstar systems | Supplier review; EXT-08 | AST-007, AST-008 | Finance Manager |
| R-17 | A critical vulnerability on an internet-facing service is exploited before it is patched | Process review; INT-04 | AST-007, AST-020 | Head of Engineering |
| R-18 | Slow internal escalation means a personal data breach is not assessed in time, so customers and regulators are notified late | ARM-22 | AST-017 | Data Protection lead |
| R-19 | Staff paste Restricted customer or HR data into unapproved generative AI tools, where it is kept or reused outside Northstar's control | ARM-12 | AST-008, AST-001 | Managing Director |
| R-20 | A laptop is lost or stolen and Restricted data held on it is exposed | ARM-25 | AST-020 | IT Manager |

## 4. Ratings

L × I = likelihood × impact. Colours show the band.

| ID | Inherent L×I | Existing controls (simulated status) | Current L×I | Conf. | Decision | Target L×I |
| --- | --- | --- | --- | --- | --- | --- |
| R-01 | 🟥 4×5 = 20 Very High | MFA for staff (E); database role-based access (P: engineers have broad read access); database audit logging (U) | 🟧 3×5 = 15 High | Med | Modify | 🟨 2×4 = 8 Medium |
| R-02 | 🟧 3×4 = 12 High | Region chosen at deployment (P: analytics copies not checked); Azure Policy allowed locations (N) | 🟧 3×4 = 12 High | Low | Modify | 🟩 1×4 = 4 Low |
| R-03 | 🟧 3×4 = 12 High | Restricted HR SharePoint site (P: inherited permissions found); access reviews (U) | 🟧 3×4 = 12 High | Med | Modify | 🟨 2×4 = 8 Medium |
| R-04 | 🟧 4×3 = 12 High | Dual approval written into the finance procedure (U) | 🟧 4×3 = 12 High | Med | Modify | 🟨 2×3 = 6 Medium |
| R-05 | 🟥 4×4 = 16 Very High | MFA on repositories (E); branch protection (P: not on all repositories); code review (P) | 🟧 3×4 = 12 High | Med | Modify | 🟨 2×4 = 8 Medium |
| R-06 | 🟥 4×5 = 20 Very High | Key Vault in use (P: some secrets in pipeline variables); secret scanning (N) | 🟥 4×5 = 20 Very High | Med | Modify (urgent) | 🟨 2×4 = 8 Medium |
| R-07 | 🟧 3×5 = 15 High | Dependency scanning (U) | 🟧 3×5 = 15 High | Low | Modify, then accept the target | 🟧 2×5 = 10 High |
| R-08 | 🟥 4×5 = 20 Very High | Defender for Cloud secure score monitored (P); infrastructure as code (P); Azure Policy enforcement (N) | 🟧 3×5 = 15 High | Med | Modify | 🟨 2×4 = 8 Medium |
| R-09 | 🟧 2×5 = 10 High | Failover design documented (U: never tested) | 🟧 2×5 = 10 High | Med | Modify | 🟨 2×3 = 6 Medium |
| R-10 | 🟥 5×4 = 20 Very High | MFA for staff (E); email filtering (E); awareness training (P: 70% completion); legacy authentication still allowed (N) | 🟧 3×4 = 12 High | Med | Modify | 🟨 2×4 = 8 Medium |
| R-11 | 🟥 5×4 = 20 Very High | MFA for staff (E); service accounts excluded from MFA (P) | 🟧 3×4 = 12 High | High | Modify | 🟨 2×4 = 8 Medium |
| R-12 | 🟥 4×4 = 16 Very High | HR emails IT when someone leaves (P: informal, no deadline); quarterly access review (U) | 🟥 4×4 = 16 Very High | Med | Modify (urgent) | 🟨 2×4 = 8 Medium |
| R-13 | 🟥 4×5 = 20 Very High | Separate admin accounts (E); just-in-time privileged access (N); break-glass vault (U) | 🟧 3×5 = 15 High | Med | Modify, then accept the target | 🟧 2×5 = 10 High |
| R-14 | 🟥 4×5 = 20 Very High | Daily backups (E); immutable or offline copy (N); restore testing (U) | 🟥 4×5 = 20 Very High | Med | Modify (urgent) | 🟨 2×3 = 6 Medium |
| R-15 | 🟧 3×4 = 12 High | Central Log Analytics (E); administrators can delete logs (N); 30-day retention (P) | 🟧 3×4 = 12 High | Med | Modify | 🟩 1×4 = 4 Low |
| R-16 | 🟧 3×5 = 15 High | Supplier due diligence (U); guest accounts with MFA (P) | 🟧 3×5 = 15 High | Low | Modify | 🟨 2×4 = 8 Medium |
| R-17 | 🟥 4×5 = 20 Very High | Weekly vulnerability scanning (E); 14-day patching deadline for critical fixes (P: met for 80%, against a 95% target for Obj 7) | 🟧 3×5 = 15 High | Med | Modify | 🟨 2×4 = 8 Medium |
| R-18 | 🟧 3×4 = 12 High | Incident reporting mailbox (E); incident procedure (U: draft only) | 🟧 3×4 = 12 High | Med | Modify | 🟩 1×4 = 4 Low |
| R-19 | 🟥 4×4 = 16 Very High | AI acceptable-use guidance (U); no technical blocking (N) | 🟥 4×4 = 16 Very High | Low | Modify (urgent) | 🟨 2×4 = 8 Medium |
| R-20 | 🟧 3×4 = 12 High | BitLocker through Intune (P: 96% of devices compliant); remote wipe (E) | 🟨 2×4 = 8 Medium | High | Modify | 🟩 1×4 = 4 Low |

**How to read the results**

- **No credit without evidence.** Twelve risks show no change between inherent and current scores: R-02, 03, 04, 06, 07, 09, 12, 14, 15, 16, 18 and 19. In most, the controls are untested or missing. In R-14 and R-15, the effective controls (daily backups, central logging) don't block that scenario's attack route, so they earn no credit either.
- **Some treatments reduce impact, not likelihood.** In R-09, R-14 and others, tested failover or immutable backups limit the damage rather than prevent the event.
- **R-07 and R-13 remain High after treatment.** A supply-chain compromise or an administrator takeover would still be severe. The Steering Group must accept their target scores under NSD-ISMS-016, with conditions.
- **Severe impact.** Nine risks have current impact 5: R-01, 06, 07, 08, 09, 13, 14, 16 and 17. Under NSD-ISMS-013 §5, all of these are reported to the Steering Group, whatever their band.

## 5. Risk profile

| Band | Inherent | Current residual | Target residual |
| --- | --- | --- | --- |
| 🟥 Very High | 11 | 4 | 0 |
| 🟧 High | 9 | 15 | 2 |
| 🟨 Medium | 0 | 1 | 14 |
| 🟩 Low | 0 | 0 | 4 |

## 6. Risk ownership

Owners were revised in NSD-ISMS-017, which assesses each owner's authority, budget and capacity.

| Risk owner | Risks | Very High (current) |
| --- | --- | --- |
| Head of Engineering | 7: R-01, 05, 06, 07, 08, 09, 17 | 1 |
| IT Manager | 5: R-10, 11, 13, 14, 20 | 1 |
| HR Manager | 2: R-03, R-12 | 1 |
| Finance Manager | 2: R-04, R-16 | 0 |
| Data Protection lead | 2: R-02, R-18 | 0 |
| Managing Director | 1: R-19 | 1 |
| GRC Analyst | 1: R-15 | 0 |

The 4 Very High risks now have 4 different owners. The Head of Engineering and IT Manager still own 12 risks. NSD-ISMS-017 §6 explains why, and how the load is managed.

**GRC Analyst as risk owner.** R-15 stays with the GRC Analyst as a recorded exception: no other role is independent of the administrators. The GRC Analyst does not **accept** the risk. Acceptance goes to the Steering Group, and treatment is verified by the internal auditor.

## 7. Scenarios not yet in the register

These NSD-ISMS-010 scenarios are lower priority or are partly covered above. They are assessed in the next cycle:

| Scenario | Reason deferred |
| --- | --- |
| ARM-17 restore failure | Covered in R-14 |
| ARM-19 support ticket attachments | P3; Medium impact |
| ARM-20 contract obligations | P2; to be added with NSD-ISMS-005 (legal register) |
| ARM-21 vulnerability reports leaked | Linked to R-17; assessed next cycle |
| ARM-23 architecture documentation | P3; Medium impact |
| ARM-24 BC/DR plan out of date | Linked to R-09; assessed with the BC/DR plan |
| ARM-26 both senior owners unavailable | Organisational; assessed with NSD-ISMS-017 |

## 8. Changes from the 1.0 draft

| 1.0 draft | v0.1 |
| --- | --- |
| Numbered NSD-ISMS-012 | NSD-ISMS-014; 012 is the methodology |
| Residual scores reduced for every control marked "(verify)" | Credit only for controls with simulated test evidence that address the scenario. Twelve risks show no reduction |
| Band "Critical"; 16 shown as High | "Very High"; 16 is Very High (NSD-ISMS-013) |
| Owners included Head of Customer Operations, Head of Development, Security Lead, Procurement Manager, Operations Director, Commercial Director and Department Managers | Owners aligned with NSD-ISMS-007 and 010. Each risk has one owner |
| Inherent and residual only | Inherent, current residual and target residual, plus confidence and treatment decision |
| No link to assets or scenarios | Each risk links to its ARM scenario and AST assets |
| R-016 phishing and R-020 awareness overlapped | Merged into R-10 |
| Network architecture and contract disclosure in the top 20 | Deferred (section 7). Replaced by secrets in code, CI/CD supply chain, EU data residency, AI tool misuse and breach-notification delay |
| Some scenarios read as labels, e.g. "Security awareness" | All risks written as full scenarios (NSD-ISMS-012 §5) |

## 9. Version history

| Version | Change |
| --- | --- |
| 0.1 | First version of the register |
| 0.3 | Risk owners changed for R-02 (Data Protection lead), R-12 (HR Manager), R-18 (Data Protection lead) and R-19 (Managing Director), following NSD-ISMS-017. Section 6 updated. |
| 0.2 | R-20: BitLocker changed from Effective to Partially effective (4% of devices non-compliant), found in the SoA cross-check (NSD-ISMS-019 §6). Score unchanged: remote wipe is effective, and the gap is small. |

## 10. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the register; acts on the Very High escalations | Pending | |
| Risk owners | Confirm scenarios, scores and treatment decisions | Pending | |
| ISMS Steering Group | Reviews consistency and the Severe-impact risks | Pending | |
| Information Security / GRC Analyst | Prepared the register | Prepared | |

---

*Portfolio note: Scores and control statuses are simulated assumptions for a fictional organisation. A real assessment would validate them through interviews, technical evidence, incident history, vulnerability results and supplier assurance.*
