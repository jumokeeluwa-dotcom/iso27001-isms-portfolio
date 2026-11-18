# Northstar Digital Solutions Ltd — Control Evidence Checklist

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-021 |
| Version | 1.0 — Draft for control owner review |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 6.1.3(d), 7.5, 9.1, 9.2) |
| Related documents | [NSD-ISMS-012 Methodology](../03-risk-management/12-risk-assessment-methodology.md) · [NSD-ISMS-015 Treatment Plan](../03-risk-management/15-risk-treatment-plan.md) · [NSD-ISMS-018 SoA Methodology](18-soa-methodology.md) · [NSD-ISMS-019 SoA](19-statement-of-applicability.md) · [NSD-ISMS-020 Risk–Control Mapping](20-risk-control-mapping.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | With each SoA version, and before internal and certification audits |
| Classification | Internal. The evidence itself is Confidential (section 7) |

---

## 1. Purpose

A control is not proven effective just because a policy exists. This checklist defines, for each priority control, the evidence needed to show that the control is:

- **designed** appropriately (documented evidence);
- **operating** in practice (operational evidence);
- **achieving its outcome** (effectiveness evidence).

It also sets the rule linking evidence to SoA status, so that no control is marked "Implemented" (NSD-ISMS-019) or given full credit in the risk register (NSD-ISMS-014) without the right evidence.

## 2. Three types of evidence

| Type | Question it answers | Examples | Audit term |
| --- | --- | --- | --- |
| **Documented** | Is the control designed? | Approved policy, procedure, standard, configuration design | Design adequacy |
| **Operational** | Is it actually happening? | Records, logs, approvals, tickets, configuration exports, over a defined period | Operation |
| **Effectiveness** | Does it achieve its intended outcome? | Test results, samples checked against criteria, measured results against targets | Operating effectiveness |

A policy without records shows only intent. Records without testing show activity, not success. All three are needed before a control is called implemented.

## 3. Evidence and SoA status

| Evidence held | SoA status (NSD-ISMS-018 §5) | Risk register credit (NSD-ISMS-012 §5) |
| --- | --- | --- |
| All three types, effectiveness tested in the last 12 months, test passed | **Implemented** | E: full credit |
| All three types, but the effectiveness test found gaps or exceptions | **Partially implemented** | P: partial credit |
| Documented and/or operational only, with no effectiveness test | **To be assessed** | U: no credit |
| None, but a dated treatment action or charter milestone exists | **Planned** | N: no credit |
| None, and no plan | **Not implemented**, escalated | N: no credit |

**Two consequences**

- A control moves to Implemented only when its effectiveness test passes. Completing a treatment action is not enough on its own.
- When an effectiveness test fails for a control marked Implemented, it drops to Partially implemented. Every risk linked to it in NSD-ISMS-020 is then re-scored.

## 4. Evidence quality

### 4.1 How strong is each kind of evidence?

| Rank | Evidence | Reliability |
| --- | --- | --- |
| 1 | **Re-performance:** the assessor repeats the control or test themselves | Strongest |
| 2 | **System-generated records:** audit logs, sign-in logs, job histories | Strong: hard to alter |
| 3 | **Configuration exports:** policy, role or settings exports from the system | Strong for a point in time |
| 4 | **System reports:** dashboards, compliance summaries | Good, if the source and date are shown |
| 5 | **Screenshots** | Weak: only with the date, system and user visible |
| 6 | **Documents:** policies, procedures | Design only |
| 7 | **Statements:** "we do this" | Not evidence on its own |

### 4.2 What good evidence looks like

- **Relevant:** it tests the control as described in the SoA.
- **Dated:** inside the assessment period; effectiveness evidence less than 12 months old.
- **Complete:** samples are drawn from the full population, and the source of the population is recorded.
- **Independent:** the GRC Analyst or internal auditor checks it, not only the control owner (NSD-ISMS-015 §2).
- **Minimal:** personal data not needed for the test is redacted.

### 4.3 Sample sizes

These sizes are illustrative and based on common audit practice. Larger or riskier populations may need more.

| How often the control runs | Sample size |
| --- | --- |
| Annually | 1 |
| Quarterly | 2 |
| Monthly | 2–3 |
| Weekly | 5 |
| Daily | 20–25 |
| Many times a day, or per event (e.g. each leaver, each deployment) | 25, or all if the population is under 25 |

## 5. Priority controls (27)

### 5.1 How they were chosen

The 27 controls are those that meet any of three criteria:

1. **The 18 controls in the initial evidence request:** 5.1, 5.9, 5.12, 5.16, 5.18, 5.19, 5.23, 5.24, 6.3, 6.5, 8.2, 8.5, 8.8, 8.9, 8.13, 8.15, 8.16 and 8.24.
2. **Controls that treat a Very High risk** (R-06, R-12, R-14, R-19): adds 5.3, 5.10, 5.13, 5.17, 5.30, 8.4, 8.12, 8.23 and 8.28.
3. **The most relied-on controls** in NSD-ISMS-020 §2 (8.5, 8.2, 8.15, 8.16, 5.3): already covered by 1 and 2.

The other 20 applicable controls follow in version 0.2 (section 6).

### 5.2 Evidence checklist

| Control | Documented evidence | Operational evidence | Effectiveness test | SoA status now | Links |
| --- | --- | --- | --- | --- | --- |
| **5.1** Policies for information security | Information security policy approved and signed by the MD | Publication record; staff acknowledgement report | At least 95% of staff and contractors have acknowledged it; annual review record exists | Planned | Obj 1 |
| **5.3** Segregation of duties | Matrix of incompatible duties | Role exports: backup admin vs production admin; deployment author vs approver. Payment approval logs | Sample 25 production deployments: approver is never the author. Sample 5 bank-detail changes: call-back and second approver recorded. Zero overlap in role exports | Planned | R-04, R-07, R-14; T-04.1, T-07.2, T-14.2 |
| **5.9** Inventory of information and other associated assets | NSD-ISMS-006 and NSD-ISMS-011 approved | Register with owner acceptances; attestation records; quarterly reconciliation results | Trace 10 Azure resources and 10 devices from discovery tools to the register: all present, with owners. Obj 2 coverage 100% | Partially implemented | Obj 2 |
| **5.10** Acceptable use of information and other associated assets | Handling rules (NSD-ISMS-008 §4) and AI rule published | Acknowledgement records; approved AI tool record | DLP and web filter logs show no Restricted uploads to unapproved AI tools over 30 days | Planned | R-19; T-19.1 |
| **5.12** Classification of information | NSD-ISMS-008 approved | All registered assets classified in NSD-ISMS-006; label usage report | Sample 25 documents from Restricted SharePoint sites: correct label applied | Planned | NSD-ISMS-008 |
| **5.13** Labelling of information | Purview label configuration | Label usage statistics by site | All files on the HR site carry the Restricted label with encryption; an unlabelled test file is detected | Planned | R-03; T-03.2 |
| **5.16** Identity management | Joiner, mover and leaver procedure | HR workflow logs; account creation and change records | Sample 25 joiners, movers and leavers from the quarter: accounts match HR records; no shared accounts | Partially implemented | R-12; T-12.3 |
| **5.17** Authentication information | Secrets management standard; break-glass procedure | Key Vault inventory; rotation logs; secret scanning reports | Full secret scan of all repositories finds zero live secrets. Quarterly break-glass test passed | Partially implemented | R-06, R-11, R-13; T-06.1, T-11.1, T-13.2 |
| **5.18** Access rights | Access management procedure | Access approval records; quarterly review results | Sample 25 access grants: each approved by the asset owner (NSD-ISMS-007). Last review completed, with removals actioned | Partially implemented | R-03, R-12, R-16; T-03.1, T-12.1–12.3, T-16.1 |
| **5.19** Information security in supplier relationships | Supplier security policy | Supplier register with criticality ratings; assessment records | 100% of critical suppliers assessed in the last 12 months (Obj 9). Sample 3 assessments checked for completeness | To be assessed | R-16; T-16.2 |
| **5.23** Information security for use of cloud services | Cloud security standard; shared-responsibility matrix (NSD-ISMS-004 §9) | Azure Policy compliance; Defender secure score history; review of Microsoft's ISO 27001 and SOC 2 reports | Policy compliance of 95% or higher. A test attempt to create a public storage account is blocked | Partially implemented | R-08, R-09; T-08.1 |
| **5.24** Information security incident management planning and preparation | Incident and breach procedure, including processor notification to customers; roles; contact list | Incident log | Tabletop exercise: breach assessment completed within 24 hours; contact list tested | To be assessed | R-18; T-18.1 |
| **5.30** ICT readiness for business continuity | BC/DR plan with RTO and RPO; failover runbook | DR test schedule; test reports | Failover test and database restore both meet the 4-hour RTO and 1-hour RPO | To be assessed | R-09, R-14; T-09.2, T-14.3 |
| **6.3** Information security awareness, education and training | Training plan and materials | Completion records; phishing simulation results | Completion of 95% or higher (Obj 5). Phishing report rate improving and click rate falling across simulations | Partially implemented | R-10; T-10.2 |
| **6.5** Responsibilities after termination or change of employment | Leaver checklist | Completed checklists; device return records | Sample 25 leavers (or all, if fewer): account disabled by the end of the last working day (HR leaving date vs Entra ID disable time); device returned | Partially implemented | R-12; T-12.1–12.3 |
| **8.2** Privileged access rights | Privileged access standard | Privileged account inventory; just-in-time activation logs and approvals | No standing Global Administrators apart from 2 break-glass accounts. Sample 25 activations: each approved and justified. Quarterly review completed | Partially implemented | R-13, R-01, R-14; T-13.1, T-01.1, T-14.2 |
| **8.4** Access to source code | Repository access and branch protection standard | Repository permission export; branch protection settings | 100% of repositories protected. Sample 25 merged pull requests: each independently reviewed | Partially implemented | R-05, R-06; T-05.1, T-06.2 |
| **8.5** Secure authentication | Authentication policy; Conditional Access design | Conditional Access policy export; MFA registration report; sign-in logs | MFA or managed identity covers 100% of accounts, including service accounts. Zero legacy authentication sign-ins over 30 days. A test legacy sign-in is blocked | Partially implemented | R-01, R-05, R-10, R-11, R-13, R-16; T-10.1, T-11.1 |
| **8.8** Management of technical vulnerabilities | Vulnerability management procedure with fix deadlines | Scan reports; remediation tickets; approved exceptions | At least 95% of critical vulnerabilities fixed within 14 days over the quarter (Obj 7). Sample 25 tickets checked for dates | Partially implemented | R-17; T-17.1 |
| **8.9** Configuration management | Secure baselines; infrastructure-as-code repository | Azure Policy assignments; change records | Compliance of 95% or higher. Sample 5 resources: live configuration matches the infrastructure code | Partially implemented | R-08, R-02; T-08.1 |
| **8.12** Data leakage prevention | DLP policy design | DLP policy export; alert records | Test upload of a Restricted-labelled file to an unapproved site is blocked. Alerts are triaged | Planned | R-19; T-19.2 |
| **8.13** Information backup | Backup policy: frequency, retention, immutability | Backup job reports; immutability configuration | At least 99% of backup jobs succeed over 30 days. Restore test meets the 4-hour RTO and 1-hour RPO | Partially implemented | R-14; T-14.1, T-14.3 |
| **8.15** Logging | Logging standard: sources and 12-month retention | Diagnostic settings export; retention configuration; role assignments | An administrator's attempt to delete logs fails. An event from the start of the retention period can still be retrieved | Partially implemented | R-15, R-01, R-06; T-15.1, T-01.2, T-06.3 |
| **8.16** Monitoring activities | Monitoring and alerting procedure | Alert rules; investigation tickets; weekly review log | A test bulk-export alert is raised and triaged within the target time. Sample 25 alerts: triage and escalation recorded | Partially implemented | R-01, R-08; T-01.2, T-08.2 |
| **8.23** Web filtering | Web filtering policy | Filtering policy export; block logs | A test visit to an unapproved AI site is blocked on a managed device, both in the office and remotely | Planned | R-19; T-19.2 |
| **8.24** Use of cryptography | Cryptography standard: algorithms and key management | Database and storage encryption settings; Key Vault configuration; BitLocker report | 100% of devices encrypted. Keys rotated on schedule. TLS configuration scan passes | Partially implemented | R-06, R-20; T-06.1, T-20.1 |
| **8.28** Secure coding | Secure coding standard | Pull request review records; code and secret scanning results | Sample 25 pull requests: each reviewed and scans passed. No critical findings merged | Partially implemented | R-05, R-06; T-05.1, T-06.2 |

**Current statuses** are taken from NSD-ISMS-019. None of the 27 is Implemented yet: no effectiveness test has been completed and passed. Most completion evidence in NSD-ISMS-015 doubles as the effectiveness test here. When the GRC Analyst verifies it, the status can move.

## 6. Remaining applicable controls (20)

Checklist entries for these follow in version 0.2, using the same three columns:

5.2, 5.7, 5.15, 5.20, 5.22, 5.25, 5.26, 5.27, 5.29, 5.31, 5.34, 6.8, 7.4, 8.1, 8.3, 8.14, 8.20, 8.21, 8.25 and 8.32.

Controls confirmed in SoA Wave 2 (NSD-ISMS-020 §5) are added once they are assessed.

## 7. Evidence handling

| Item | Rule |
| --- | --- |
| Location | GRC evidence repository: a Restricted SharePoint site with access limited to the GRC Analyst, control owners and the internal auditor |
| Classification | **Confidential**. Evidence shows how controls work and where they fail (NSD-ISMS-008) |
| Naming | EV-[control]-[YYYYMM]-[nn], e.g. EV-8.5-202701-01 |
| Record for each item | Evidence ID; control; evidence type; description; period covered; source system; provided by; collected by and date; reviewer; result (pass, exceptions, fail) |
| Personal data | Redact anything the test does not need, e.g. use employee IDs instead of names in leaver samples |
| Retention | 3 years: one full certification cycle (NSD-ISMS-011 §11) |
| Who collects | Control owners provide it. The GRC Analyst collects and verifies it. Where the GRC Analyst owns the control or action, the internal auditor verifies it |

## 8. How this is used

| Activity | Use of the checklist |
| --- | --- |
| Treatment verification (NSD-ISMS-015) | When an action is complete, its evidence is checked against the effectiveness test here |
| SoA updates (NSD-ISMS-019) | Status changes only as section 3 allows |
| Risk re-scoring (NSD-ISMS-014) | Credit follows the same evidence |
| Internal audit (clause 9.2) | The auditor re-performs a sample of effectiveness tests |
| Certification audit | Evidence packs prepared per control from the repository |

## 9. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the checklist and the evidence-to-status rule | Pending | |
| Control owners | Confirm the evidence they can provide | Pending | |
| Internal auditor | Reviews the effectiveness tests for adequacy | Pending | |
| Information Security / GRC Analyst | Prepared the checklist | Prepared | |

---

*Portfolio note: Evidence requirements are simulated for a fictional organisation. No evidence has been collected.*
