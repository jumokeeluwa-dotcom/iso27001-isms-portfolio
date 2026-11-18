# Northstar Digital Solutions Ltd — Information Asset Risk Mapping Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-010 |
| Version | 1.0 — Draft for risk owner review |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 6.1.2, 8.2; Annex A controls as referenced) |
| Related documents | [NSD-ISMS-002 Context](../01-initiation-and-context/02-organisational-context-register.md) · [NSD-ISMS-006 Asset Register](06-information-asset-register.md) · [NSD-ISMS-007 Ownership](07-asset-ownership-register.md) · [NSD-ISMS-009 Valuation](09-asset-valuation-methodology.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Quarterly until the risk register is approved; then replaced by risk register reviews |
| Classification | Confidential — it describes how Northstar could be attacked |

---

## 1. Purpose

This register links each registered asset to credible risk scenarios. It is the bridge between the asset documents (NSD-ISMS-006 to 009) and the formal risk assessment in project phase 2.

For each scenario it records:

- The asset and the C, I or A dimension at risk.
- The threat and the exposure that would let it happen.
- The context issue behind it (NSD-ISMS-002).
- The **impact**, taken directly from the asset valuation (NSD-ISMS-009).
- Candidate Annex A controls and the proposed risk owner.

**What it does not do:** it does not rate likelihood or overall risk. Those need the risk assessment methodology and the MD's risk acceptance criteria, which are phase 2 deliverables. Every scenario here must be assessed through that methodology before treatment decisions are made.

## 2. Conventions

| Item | Rule |
| --- | --- |
| Scenario ID | ARM-nn. IDs are never reused. When a scenario moves to the risk register, it keeps a cross-reference to its ARM ID |
| Exposure | A **hypothesis to test**, not a confirmed weakness. Phase 2 confirms or rejects each one with evidence |
| Impact | The asset's rating in NSD-ISMS-009 for the dimension at risk. Where several dimensions are at risk, the highest applies |
| Proposed risk owner | The asset owner from NSD-ISMS-007, unless the scenario crosses assets |
| Assessment priority | **P1:** Critical-tier asset with High impact. **P2:** High-tier asset with High impact, or a scenario spanning several assets. **P3:** Medium impact |
| Coverage | Every registered asset has at least one scenario. Every Critical asset has a scenario for each dimension rated High, where credible |

## 3. Risk scenarios

| ID | Asset | Dim. | Threat | Exposure to test | Context |
| --- | --- | --- | --- | --- | --- |
| ARM-01 | AST-001 Customer platform data | C | External attacker exfiltrates customer data | Excessive database access, or a data store exposed through misconfiguration | INT-04, EXT-01 |
| ARM-02 | AST-001 Customer platform data | C | EU customer data stored or processed outside the EU region | Region settings, replicas or analytics copies not restricted to the EU | EXT-03, EXT-04 |
| ARM-03 | AST-002 HR records | C | Insider or compromised account accesses HR records | HR files in SharePoint sites with broad permissions | INT-07 |
| ARM-04 | AST-003 Financial and billing records | I | Payment fraud through business email compromise, e.g. altered supplier bank details | One person can change and approve payment details | EXT-01 |
| ARM-05 | AST-004 Source code | I | Malicious or unreviewed change reaches production | Branch protection and code review not enforced on all repositories | INT-05 |
| ARM-06 | AST-006 Keys and secrets (via AST-004) | C | Secrets committed to code are found and used | No secret scanning; secrets held outside Key Vault | INT-05 |
| ARM-07 | AST-005 CI/CD pipelines | I | Supply-chain attack through a pipeline or third-party dependency | Unpinned dependencies; broad pipeline permissions | INT-05, EXT-08 |
| ARM-08 | AST-006 Keys and secrets | C, I | Theft or misuse of encryption keys or secrets | Broad Key Vault access; no rotation | INT-04 |
| ARM-09 | AST-007 Production environment | C, I | Azure misconfiguration exposes services or data | No enforced configuration baseline or policy checks | INT-04 |
| ARM-10 | AST-007 Production environment | A | Azure regional outage takes the platform offline | Single-region deployment, or failover not tested | EXT-05, EXT-12 |
| ARM-11 | AST-008 Microsoft 365 | C | Phishing leads to account compromise and data theft | Inconsistent awareness; legacy authentication still allowed | INT-09, EXT-01 |
| ARM-12 | AST-008 Microsoft 365 | C | Staff paste Restricted data into unapproved AI tools | No technical control on AI tool use | INT-13 |
| ARM-13 | AST-009 Identity directory | C, I | Account takeover through password attacks | MFA not enforced for every account, including service accounts | EXT-01 |
| ARM-14 | AST-009 Identity directory | C | Leavers or contractors keep access | Informal joiner, mover and leaver process | INT-07 |
| ARM-15 | AST-010 Privileged credentials | C, I | Theft or misuse of administrator credentials | Standing admin rights; no privileged access vault | INT-01 |
| ARM-16 | AST-011 Backups | I, A | Ransomware encrypts or deletes the backups as well as production | Backups reachable with the same administrator credentials; no immutable copy | EXT-01 |
| ARM-17 | AST-011 Backups | A | A restore fails when it is needed | Restores not tested | INT-11 |
| ARM-18 | AST-012 Security event logs | I | Attacker or administrator alters or deletes logs | Administrators can change logs; retention too short | INT-10 |
| ARM-19 | AST-013 Support records | C | Customer data in ticket attachments is exposed | Production data attached to tickets; broad ticket access | EXT-06 |
| ARM-20 | AST-014 / AST-015 Contracts | I | Contract obligations are missed or changed without approval, e.g. DPA breach-notification timescales | No obligation tracking or version control | EXT-06, EXT-07 |
| ARM-21 | AST-016 Vulnerability reports | C | Reports leak and are used for a targeted attack | Reports shared by email or stored with broad access | INT-04 |
| ARM-22 | AST-017 Incident and breach records | I | Incomplete records cause a missed 72-hour breach notification | Informal incident logging and escalation | INT-10 |
| ARM-23 | AST-018 Technical documentation | C | Architecture details help an attacker plan an attack | Wiki open to all staff and contractors | INT-06 |
| ARM-24 | AST-019 BC/DR plans | I, A | Plan is out of date or unavailable during a disaster | Plan held only in Microsoft 365; never tested | EXT-05, EXT-12 |
| ARM-25 | AST-020 Endpoints | C | A lost or stolen laptop exposes data | Encryption not verified on every device, including EU home workers' | INT-08 |
| ARM-26 | AST-001 to AST-011 (engineering and IT assets) | A | Head of Engineering and IT Manager are both unavailable during a major incident | They deputise for each other with no third cover (NSD-ISMS-007 §4) | INT-01, INT-02 |

## 4. Impact, controls and ownership

| ID | Asset tier | Impact | Candidate Annex A controls | Proposed risk owner | Priority |
| --- | --- | --- | --- | --- | --- |
| ARM-01 | Critical | H | 5.15 access control; 8.3 information access restriction; 8.24 cryptography; 8.12 DLP; 8.16 monitoring | Head of Engineering | P1 |
| ARM-02 | Critical | H | 5.31 legal requirements; 5.34 privacy; 8.9 configuration management | Head of Engineering | P1 |
| ARM-03 | Critical | H | 5.15 access control; 5.18 access rights; 8.15 logging | HR Manager | P1 |
| ARM-04 | High | H | 5.3 segregation of duties; 6.3 awareness; 8.15 logging | Finance Manager | P2 |
| ARM-05 | High | H | 8.4 access to source code; 8.28 secure coding; 8.32 change management | Head of Engineering | P2 |
| ARM-06 | Critical | H | 8.4 access to source code; 8.24 cryptography; 8.28 secure coding | Head of Engineering | P1 |
| ARM-07 | High | H | 5.21 ICT supply chain; 8.25 secure development lifecycle; 8.29 security testing | Head of Engineering | P2 |
| ARM-08 | Critical | H | 8.24 cryptography; 5.17 authentication information; 8.2 privileged access | Head of Engineering | P1 |
| ARM-09 | Critical | H | 8.9 configuration management; 8.20 network security; 8.22 network segregation; 5.23 cloud services | Head of Engineering | P1 |
| ARM-10 | Critical | H | 5.30 ICT readiness for business continuity; 8.14 redundancy; 5.23 cloud services | Head of Engineering | P1 |
| ARM-11 | Critical | H | 6.3 awareness; 8.5 secure authentication; 8.23 web filtering | IT Manager | P1 |
| ARM-12 | Critical | H | 5.10 acceptable use; 5.14 information transfer; 8.12 DLP | IT Manager | P1 |
| ARM-13 | Critical | H | 8.5 secure authentication; 5.17 authentication information | IT Manager | P1 |
| ARM-14 | Critical | H | 5.18 access rights; 6.5 responsibilities after termination | IT Manager | P1 |
| ARM-15 | Critical | H | 8.2 privileged access; 5.17 authentication information; 8.15 logging | IT Manager | P1 |
| ARM-16 | Critical | H | 8.13 backup; 8.2 privileged access; 8.7 malware protection | IT Manager | P1 |
| ARM-17 | Critical | H | 8.13 backup; 5.30 ICT readiness for business continuity | IT Manager | P1 |
| ARM-18 | High | H | 8.15 logging; 8.16 monitoring; 5.3 segregation of duties | GRC Analyst | P2 |
| ARM-19 | Medium | M | 5.10 acceptable use; 8.11 data masking | Customer Support Manager | P3 |
| ARM-20 | High | H | 5.20 supplier agreements; 5.31 legal requirements; 5.33 protection of records | Sales lead (customers); Finance Manager (suppliers) | P2 |
| ARM-21 | Critical | H | 5.12 classification; 5.13 labelling; 8.8 technical vulnerabilities | GRC Analyst | P1 |
| ARM-22 | Critical | H | 5.24–5.26 incident management; 5.28 evidence collection; 6.8 event reporting | GRC Analyst | P1 |
| ARM-23 | Medium | M | 5.15 access control; 5.12 classification | Head of Engineering | P3 |
| ARM-24 | Critical | H | 5.29 security during disruption; 5.30 ICT readiness for business continuity | Managing Director | P1 |
| ARM-25 | Medium | M | 8.1 user endpoint devices; 7.9 assets off-premises; 8.24 cryptography | IT Manager | P3 |
| ARM-26 | Several | H | 5.2 roles and responsibilities; 5.29 security during disruption | Managing Director | P2 |

Candidate controls are inputs to risk treatment. The final selection is justified in the Statement of Applicability (clause 6.1.3).

## 5. Coverage summary

| Measure | Result |
| --- | --- |
| Scenarios | 26 |
| Registered assets with at least one scenario | 20 of 20 |
| Critical assets covered | 11 of 11 |
| Assessment priority | 17 P1 · 6 P2 · 3 P3 |
| Dimensions | Confidentiality 15 · Integrity 12 · Availability 5 (some scenarios affect more than one) |
| Proposed risk owners | Head of Engineering 9 · IT Manager 8 · GRC Analyst 3 · MD 2 · Finance Manager 1 · HR Manager 1 · Sales lead 1 · Customer Support Manager 1 |

**Observation.** The Head of Engineering and IT Manager would own 17 of the 26 scenarios. This repeats the concentration found in NSD-ISMS-007 and makes scenario ARM-26 more important. The Steering Group should confirm they have time for phase 2 risk workshops (charter §8.1).

## 6. Handover to the risk register

When phase 2 starts, each scenario moves into the risk register with these fields:

| Field | Source | Status |
| --- | --- | --- |
| Risk ID and ARM cross-reference | Risk register | To be assigned |
| Asset, threat and exposure | This register | Done |
| Context link | This register | Done |
| Existing controls | Evidence from custodians | To be gathered in phase 2 |
| Exposure confirmed or rejected | Control testing | To be done in phase 2 |
| Impact | NSD-ISMS-009 | Done |
| Likelihood | Risk assessment methodology | Needs the methodology |
| Inherent and residual risk rating | Risk assessment methodology | Needs the methodology |
| Risk owner | This register, confirmed by the owner | Proposed |
| Treatment decision and target date | Risk treatment plan | To be done in phase 2 |

## 7. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the register as input to phase 2 | Pending | |
| Proposed risk owners | Confirm scenarios and ownership | Pending | |
| Information Security / GRC Analyst | Prepared the register | Prepared | |

---

*Portfolio note: These are preliminary risk scenarios, not completed or approved risk assessments. Likelihood and risk ratings must be set using the organisation's approved risk methodology.*
