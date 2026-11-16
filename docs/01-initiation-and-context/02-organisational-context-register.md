# Northstar Digital Solutions Ltd — Organisational Context Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-002 |
| Version | 0.3 — Draft for review |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 4.1, 6.1.1) |
| Related documents | [NSD-ISMS-001 Project Charter](01-isms-project-charter.md) · [NSD-ISMS-003 Interested-Party Requirements Register](03-interested-party-requirements-register.md) · [NSD-ISMS-004 ISMS Scope Statement](04-isms-scope-statement.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually, and on the triggers in section 7 |
| Classification | Internal — Simulated portfolio document |

---

## 1. Purpose

This register records the internal and external issues that affect Northstar's ability to achieve the intended outcomes of its ISMS (clause 4.1). It also assesses how significant each issue is and shows where it feeds into the ISMS: scope, risk assessment, objectives and governance.

The ISMS intended outcomes, taken from the charter, are:

1. Protect the confidentiality, integrity and availability of customer, employee and financial information.
2. Meet legal, regulatory and contractual obligations in the UK and EU.
3. Achieve and maintain ISO/IEC 27001:2022 certification for the SaaS platform.

## 2. Method

| Element | Approach |
| --- | --- |
| Inputs | Charter NSD-ISMS-001 v0.2; organisation chart; customer contracts; supplier list; architecture diagrams; incident history; interviews with the MD, IT Manager and department heads (simulated) |
| Technique | PESTLE for external issues; strengths and weaknesses review for internal issues |
| Risks and opportunities | Each issue is labelled as a risk, an opportunity, or both (clause 6.1.1) |
| Significance | Rated High / Medium / Low using the criteria below |
| Traceability | The **Informs** column links each issue to a charter section (§) or objective (Obj) in NSD-ISMS-001, a scope section (Scope §) in NSD-ISMS-004, or an interested party (IP) in NSD-ISMS-003 |

**Significance criteria**

| Rating | Meaning |
| --- | --- |
| High | Could directly prevent an intended outcome, such as a reportable breach, a lost certification, or a breached contract |
| Medium | Weakens an outcome or makes it costly to achieve |
| Low | Limited effect; monitor only |

Issues are context, not risks. High-significance issues are carried into the risk register in project phase 2, where risk IDs, owners and treatments are assigned.

## 3. Internal issues

| ID | Issue | Type | Source | Effect on ISMS outcomes | Sig. | Informs | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |
| INT-01 | A small IT team and one GRC Analyst support about 85 personnel and the SaaS platform | Risk | Org chart | Slow monitoring and remediation; people both operate and check controls | High | §6 segregation of duties; §8.1; Obj 7 | MD |
| INT-02 | ISMS knowledge sits with a single GRC Analyst | Risk | Charter §8.3 | Project stalls or registers lapse if the analyst is absent | Medium | §6 deputy; §8.3 | MD |
| INT-03 | Management commitment and budget not yet documented | Risk | Charter §8.1, §9 | ISMS lacks resources; clause 5.1 nonconformity | High | §8.1; §9; Obj 1 | MD |
| INT-04 | Northstar's side of the cloud shared-responsibility model (identity, configuration, keys) in Azure and M365 is not formally governed | Risk | Architecture review | Misconfiguration exposes customer data | High | Scope §9; Obj 6, 7 | IT Manager |
| INT-05 | Fast release cycle with source code, secrets and CI/CD pipelines central to the business | Risk | Engineering interview | Insecure code or a compromised pipeline reaches production | High | Scope §7; Obj 4, 7 | Head of Engineering |
| INT-06 | Asset inventory is incomplete | Risk | IT records | Unknown assets are unprotected and outside risk assessment | High | Obj 2; §7 phase 2 | IT Manager |
| INT-07 | Joiner, mover and leaver process is informal, including for contractors and EU-based staff | Risk | HR records | Excess or orphaned access | Medium | Scope §5; Obj 6 | HR Manager |
| INT-08 | Hybrid and cross-border working: UK office, UK homes and EU locations | Risk | HR policy | Endpoint, home network and remote access exposure | Medium | Scope §6; Scope §9 | IT Manager |
| INT-09 | Staff security awareness is inconsistent | Risk | Phishing test results (TBC) | Phishing and accidental disclosure | Medium | Obj 5 | HR Manager / GRC Analyst |
| INT-10 | Incident reporting and escalation are informal | Risk | Incident history | Missed 72-hour GDPR breach notification; late containment | High | IP-08, IP-09; §7 phase 3 | IT Manager |
| INT-11 | Policies and procedures are incomplete or uncontrolled | Risk | Document review | Inconsistent practice; audit findings on documented information | Medium | §7 phases 1 and 3 | GRC Analyst |
| INT-12 | Finance systems (billing, payroll) hold financial data outside the core platform | Risk | Finance interview | Financial data not covered by platform controls | Medium | Scope §8 | Finance Manager |
| INT-13 | Staff use of generative AI tools with company or customer data is unmanaged | Risk | Staff survey (TBC) | Data leaves controlled environments | Medium | Scope §7; topic policy set | GRC Analyst |
| INT-14 | Microsoft security tooling (Defender, Entra ID, Purview, Azure Policy) is available but under-used | Opportunity | Licence review | Faster control implementation and automated evidence | Medium | §8.3 evidence risk; Obj 6, 7 | IT Manager |
| INT-15 | Small size and direct MD involvement allow quick decisions and policy adoption | Opportunity | Charter §6 | Shorter implementation timeline | Medium | §6; §7 | MD |

## 4. External issues

| ID | Issue | Type | Source | Effect on ISMS outcomes | Sig. | Informs | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |
| EXT-01 | Cloud-targeted threats: credential phishing against M365, exploitation of misconfigured Azure services, ransomware | Risk | NCSC and vendor threat reporting | Account takeover, data breach, service outage | High | Risk assessment; Obj 6, 7 | GRC Analyst |
| EXT-02 | UK data protection law: UK GDPR, DPA 2018 and PECR, as amended by the Data (Use and Access) Act 2025 (main changes in force since 5 February 2026) | Risk | Legal register | Regulatory action and fines | High | IP-08; legal register | Data Protection lead |
| EXT-03 | EU GDPR applies through EU-based personnel, EU-hosted data and processing for EU customers | Risk | Charter §3 | Non-compliance with processor and controller duties | High | IP-01, IP-09; legal register | Data Protection lead |
| EXT-04 | UK–EU personal data flows depend on the EU's adequacy decision for the UK | Risk | Legal register | Extra transfer safeguards needed if adequacy changes | Medium | IP-09; legal register | Data Protection lead |
| EXT-05 | Concentration on Microsoft: Azure regional outage or M365 service incident | Risk | Supplier list | Platform unavailable to customers | High | Scope §9; Obj 8 | IT Manager |
| EXT-06 | Customer contracts and security questionnaires demand demonstrable assurance | Risk and opportunity | Contract review | Lost deals or breached terms; certification wins tenders | High | IP-01, IP-02; §1 drivers | Sales lead / GRC Analyst |
| EXT-07 | DORA ICT third-party terms flow down from EU financial services customers | Risk | Contract review (TBC) | Audit rights, incident reporting and exit-plan obligations | Medium (High if FS customers confirmed) | IP-03; §9 | GRC Analyst |
| EXT-08 | Supply chain compromise through sub-processors and engineering tools | Risk | Supplier list | Breach through a trusted third party | High | IP-11, IP-12; Obj 9 | GRC Analyst |
| EXT-09 | Employment and local law for EU-based personnel | Risk | Legal review (TBC) | Gaps in screening, monitoring and contract terms | Medium | §8.3; IP-04, IP-05 | HR Manager |
| EXT-10 | Cyber insurers set minimum controls (MFA, backups, EDR) | Risk and opportunity | Insurance policy | Cover refused or premiums rise; controls justified | Medium | IP-13; Obj 6 | Finance Manager |
| EXT-11 | Regulation keeps changing: the UK Cyber Security and Resilience (NIS) Bill (not yet law; could cover managed service providers), possible EU NIS2 applicability, and the EU AI Act | Risk | Regulatory monitoring | New obligations missed | Medium | Legal register | Data Protection lead |
| EXT-12 | Climate change (see section 5) | Risk | Amendment 1:2024 | Physical disruption to premises, staff and suppliers | Medium | Obj 8; BC/DR plan | IT Manager |
| EXT-13 | Market expectation of ISO 27001 certification in UK and EU B2B SaaS | Opportunity | Sales pipeline | Certification becomes a sales differentiator | High | §1; §7 phase 5 | MD |

**Note on overlaps.** INT-04 covers how *Northstar* configures and governs its cloud services. EXT-05 covers *Microsoft* failing. Likewise, INT-07 and INT-11 are internal process gaps, while EXT-08 is the threat from suppliers.

## 5. Climate change assessment (Amendment 1:2024)

**Conclusion: relevant.** Climate change can affect the availability outcome of the ISMS through premises, people and suppliers.

| Consideration | Northstar-specific effect |
| --- | --- |
| Extreme weather at the UK office | Office closure; staff move to home working (depends on INT-08 controls) |
| Power and connectivity loss at home and EU locations | Staff unable to work or support customers |
| Azure regional disruption | Platform outage for UK or EU customers unless failover is designed and tested |
| Disruption at critical suppliers | Delayed support or service from sub-processors |
| Interested party requirements | Customer and investor sustainability requests are handled by the sustainability process, not the ISMS (NSD-ISMS-003, IP-16) |

Specific climate-related risks are assigned in phase 2 once the Azure region pairing and supplier locations are confirmed.

## 6. Conclusions

The register contains 28 issues: 15 internal and 13 external. 13 are rated High.

The High issues fall into five themes:

1. **Resourcing and commitment:** INT-01, INT-03.
2. **Cloud and platform security:** INT-04, INT-05, EXT-01, EXT-05.
3. **Visibility and response:** INT-06, INT-10.
4. **Legal and contractual obligations:** EXT-02, EXT-03, EXT-06.
5. **Third parties and market:** EXT-08, EXT-13.

**How the register is used**

| ISMS element | Use of this register |
| --- | --- |
| Scope (NSD-ISMS-004) | Confirms the locations, EU presence, interfaces and financial data in scope |
| Interested parties (NSD-ISMS-003) | Supplies the legal and contractual issues behind IP-01 to IP-17 |
| Risk assessment (phase 2) | High issues become risk register entries with owners |
| Objectives (charter §2) | Supports Obj 1, 2, 4, 5, 6, 7, 8 and 9 |
| Statement of Applicability | Explains why controls are selected |
| Management review (clause 9.3) | Changes to issues are a required input |

## 7. Monitoring and review

The register is reviewed:

- At least annually, before management review.
- After significant changes to technology, services or organisation.
- After a material security incident.
- After relevant legal or regulatory changes.
- When new services, suppliers or locations are introduced.
- When significant customer requirements change.

## 8. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Overall approval | Pending | |
| IT Manager | Technical validation | Pending | |
| Information Security / GRC Analyst | Register maintenance | Prepared | |

## 9. Change log

| Version | Change |
| --- | --- |
| 1.0 (portfolio draft) | First draft: 10 internal and 10 external issues |
| 0.1 | Renumbered as a draft pending approval. Aligned with charter v0.2. Added method, significance ratings, sources, owners and opportunities. Replaced "Proposed response" with traceability to the charter. Added secure development, key-person, finance data, AI use, EU GDPR, data transfers, DORA, EU employment and insurer issues. Removed overlapping and generic items. Made the climate assessment Northstar-specific. |
| 0.2 | Linked to NSD-ISMS-003 as the master interested-party record. Updated EXT-02 with DUAA 2025 commencement. Updated EXT-11 with the Cyber Security and Resilience Bill status and NIS2, and raised it to Medium. |
| 0.3 | Scope references now point to NSD-ISMS-004 (Scope §n) instead of charter §4. |

---

*Portfolio note: All organisational issues are simulated assumptions. A real implementation would validate them against business evidence.*
