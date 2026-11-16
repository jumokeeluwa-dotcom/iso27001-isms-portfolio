# Northstar Digital Solutions Ltd — Statement of Applicability

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-019 |
| Version | 0.3 — 48 of 93 controls assessed |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clause 6.1.3(d); Annex A) |
| Method | [NSD-ISMS-018 SoA Methodology](18-soa-methodology.md) |
| Related documents | [NSD-ISMS-014 Risk Register](../03-risk-management/14-risk-register.md) · [NSD-ISMS-015 Treatment Plan](../03-risk-management/15-risk-treatment-plan.md) · [NSD-ISMS-016 Acceptance Criteria](../03-risk-management/16-risk-acceptance-criteria-register.md) · [NSD-ISMS-004 Scope](../01-initiation-and-context/04-isms-scope-statement.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Classification | Confidential — implementation statuses show where controls are incomplete |

---

## 1. Summary

This version assesses **48 of the 93 Annex A controls**, chosen by risk:

- **30 controls** from the initial representative set.
- **17 controls** named in the treatment plan (NSD-ISMS-015) but missing from that set. The NSD-ISMS-018 §8 quality check requires every treatment action to map to an applicable control.
- **1 control** (5.21) moved from Wave 2 during the supplier milestone (v0.3).

The other 45 controls are listed in section 5 with a preliminary view. They are scheduled for assessment by **29 January 2027**. A control awaiting assessment is not an exclusion.

| Status | Controls |
| --- | --- |
| Applicable | 48 |
| Not applicable (excluded) | 0 so far: 3 exclusion candidates identified in section 5 |
| Awaiting assessment | 45 |
| **Total accounted for** | **93** |

**Implementation status of the 48 applicable controls**

| Status (NSD-ISMS-018 §5) | Count | Risk register equivalent |
| --- | --- | --- |
| Implemented | 0 | E: Effective |
| Partially implemented | 23 | P: Partially effective |
| Planned | 11 | N: Not in place, with a dated plan |
| To be assessed | 13 | U: Untested |
| Not implemented | 1 | N: Not in place, no plan (**escalated**: 5.27) |

**No control is yet marked Implemented.** Most controls have parts that work, but every one has a tested gap or untested element. The SoA and the risk register use the same evidence rule, so the SoA cannot be more optimistic than NSD-ISMS-014. This is expected for a new ISMS. Statuses rise as treatment actions are verified.

## 2. Scope, definitions and evidence basis

### 2.1 Scope covered

This SoA covers the ISMS scope in NSD-ISMS-004:

- **Activities:** development, operation, support and sale of Northstar's SaaS platform for UK and European business customers.
- **People and places:** the UK head office, UK home-based staff and EU-based personnel.
- **Technology:** the Azure (UK and EU regions) and Microsoft 365 environments that Northstar manages.
- **Third parties:** relevant third-party dependencies, managed through the interfaces in NSD-ISMS-004 §9.

### 2.2 Applicability (two values only)

| Decision | Meaning |
| --- | --- |
| **Applicable** | Necessary for risk treatment or a requirement; at least one reason code |
| **Not applicable** | Assessed and excluded, with a specific justification that meets NSD-ISMS-018 §4 |

"To be assessed" is **not** an applicability decision. A control whose applicability is still open is listed in section 5 (awaiting assessment), never in the applicability column.

### 2.3 Implementation status

| Status | Meaning |
| --- | --- |
| Implemented | Operating, with test evidence from the last 12 months |
| Partially implemented | Some parts operate, with tested gaps |
| Planned | Not in place; a dated treatment action or charter milestone exists |
| Not implemented | Applicable, with no implementation and no plan: escalated |
| To be assessed | Said to exist, or unknown; not yet tested |

### 2.4 Evidence basis

The statuses use the **simulated control evidence** recorded in the risk register (NSD-ISMS-014 §2). An alternative would be to mark every control "To be assessed" until real evidence is collected. That would make the SoA contradict the risk register, which already credits some controls (for example, staff MFA is Effective). The two documents must use the same evidence. If the portfolio later switches to "no evidence yet", both change together.

In a real implementation, every status would cite a dated evidence record from the control owner before approval.

### 2.5 Conventions

| Item | Meaning |
| --- | --- |
| Reason codes | **RT** risk treatment · **LR** legal or regulatory · **CO** contractual · **BR** business requirement · **IP** interested party (NSD-ISMS-018 §3) |
| Status rule | Taken from the control's status in NSD-ISMS-014. Where a control has several elements, the weakest element sets the status |
| Owner | The role that runs the control (NSD-ISMS-007). Not necessarily the risk owner (NSD-ISMS-017) |
| Control titles | ISO/IEC 27001:2022 Annex A |

**Exclusion principle.** Controls are not excluded simply because Northstar uses cloud providers, outsources a service or does not run a technology directly. Northstar's responsibilities, dependencies, risks and contracts are considered first (NSD-ISMS-018 §4).

## 3. Assessed controls (48)

### 3.1 Organisational controls (A.5) — 25 assessed

| Control | Title | Reasons | Why applicable | Risks / actions | Status | Evidence or gap | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 5.1 | Policies for information security | BR, IP | Required for the ISMS; charter Obj 1 | Charter phase 1 | Planned | Information security policy due month 2 (charter §7) | MD / GRC Analyst |
| 5.2 | Information security roles and responsibilities | BR | Roles defined in charter §6 and NSD-ISMS-007 | Obj 1 | Planned | Roles drafted; owner acceptance pending (NSD-ISMS-007 §6) | MD |
| 5.3 | Segregation of duties | RT | Prevents fraud, unapproved deployment and backup tampering | R-04, R-07, R-14; T-04.1, T-07.2, T-14.2 | Planned | Dual payment approval untested; deployment and backup roles not yet separated | IT Manager |
| 5.7 | Threat intelligence | BR, IP | Triggers risk re-assessment (NSD-ISMS-012 §4) | All risks | To be assessed | No defined source or review routine yet | GRC Analyst |
| 5.9 | Inventory of information and other associated assets | BR, RT | Basis of the ISMS; Obj 2 | NSD-ISMS-006, 011 | Partially implemented | Register of 20 assets exists; owner acceptance and first reconciliation pending | GRC Analyst |
| 5.10 | Acceptable use of information and other associated assets | RT | Defines handling and AI use | R-19; T-19.1 | Planned | Handling rules drafted (NSD-ISMS-008 §4); AI rule not yet published | IT Manager |
| 5.12 | Classification of information | BR, LR | Protection matched to sensitivity | NSD-ISMS-008 | Planned | Standard drafted; awaiting MD approval | GRC Analyst |
| 5.13 | Labelling of information | RT | Purview labels drive encryption and DLP | R-03, R-19; T-03.2 | Planned | Labels not yet deployed | IT Manager |
| 5.15 | Access control | RT, LR | Least privilege to customer and HR data | R-01, R-03; T-01.1, T-03.1 | Partially implemented | Role-based access exists; engineers have broad database access; HR site has inherited permissions | Head of Engineering / IT Manager |
| 5.16 | Identity management | RT | Full identity lifecycle | R-12; T-12.3 | Partially implemented | Leaver process informal, with no deadline | IT Manager |
| 5.17 | Authentication information | RT | Secrets, service accounts and break-glass credentials | R-06, R-11, R-13; T-06.1, T-11.1, T-13.2 | Partially implemented | Some secrets in pipeline variables; break-glass vault untested | Head of Engineering / IT Manager |
| 5.18 | Access rights | RT | Granting, reviewing and removing access | R-03, R-12, R-16; T-12.1–12.3, T-03.1, T-16.1 | Partially implemented | Access reviews untested; guest accounts without expiry | IT Manager |
| 5.19 | Information security in supplier relationships | RT, CO | Suppliers process customer data, hold privileged access and support the platform: 7 Critical, 9 High (NSD-ISMS-055) | R-16; T-16.2 | To be assessed | Register, methodology and questionnaire drafted (055–057). **No assessment record for any supplier** (058 §2); Q2 KPI-14 figure not traceable to records | GRC Analyst |
| 5.20 | Addressing information security within supplier agreements | CO, LR | Security clauses and Article 28 DPAs required for Critical and High suppliers; DORA flow-down (NSD-ISMS-026 §4) | ARM-20; NSD-ISMS-005 | To be assessed | Contract clauses not yet reviewed; review of Critical and High contracts due 31 Jan 2028 (NSD-ISMS-060 §4) | Finance Manager |
| 5.21 | Managing information security in the ICT supply chain | RT | Northstar builds its platform from open-source components through a third-party CI/CD service that deploys to production (SUP-09) | R-07; T-07.1 | To be assessed | Dependency scanning untested (NSD-ISMS-014: U); CI/CD provider not assessed (058) | Head of Engineering |
| 5.22 | Monitoring, review and change management of supplier services | RT | Ongoing supplier assurance (Obj 9); sub-processor changes need customer notice before processing | R-16; T-16.2 | To be assessed | Review procedure drafted (NSD-ISMS-059); no review evidenced; sub-processor status of 5 suppliers to confirm (055 gap 4) | GRC Analyst |
| 5.23 | Information security for use of cloud services | RT, BR | Azure and Microsoft 365 shared-responsibility model; concentration on one supplier (EXT-05) | R-08, R-09; T-08.1 | Partially implemented | Secure score monitored; policy enforcement not in place. Microsoft assurance mapping due 10 Dec 2027 (058) | Head of Engineering |
| 5.24 | Information security incident management planning and preparation | RT, LR | Breach readiness; 72-hour duty | R-18; T-18.1 | To be assessed | Procedure in draft only | GRC Analyst |
| 5.25 | Assessment and decision on information security events | RT, LR | Timely breach assessment | R-18; T-18.1 | To be assessed | Assessment steps untested | GRC Analyst |
| 5.26 | Response to information security incidents | RT | Containment and recovery | R-18; T-18.1 | To be assessed | Response untested | IT Manager |
| 5.27 | Learning from information security incidents | BR (clause 10) | Lessons feed back into risk | R-18 | **Not implemented** | No process and no treatment action. **Escalated**: proposed new action T-18.2 to add lessons learned to the incident procedure | GRC Analyst |
| 5.29 | Information security during disruption | RT | Security maintained during incidents and failover | R-09; T-09.1 | To be assessed | Failover design documented, never tested | Head of Engineering |
| 5.30 | ICT readiness for business continuity | RT, CO | 4-hour RTO and customer SLAs | R-09, R-14; T-09.2, T-14.3 | To be assessed | No failover or restore test evidence | Head of Engineering / IT Manager |
| 5.31 | Legal, statutory, regulatory and contractual requirements | LR, CO | UK GDPR, EU GDPR, DUAA 2025, DORA flow-down | R-02; T-02.1; NSD-ISMS-005 | Planned | Legal register planned (NSD-ISMS-005) | Data Protection lead |
| 5.34 | Privacy and protection of PII | LR | Northstar's duties as processor and controller | R-02, R-03; T-02.1 | Partially implemented | Regions chosen at deployment; analytics copies not checked | Data Protection lead |

### 3.2 People controls (A.6) — 3 assessed

| Control | Title | Reasons | Why applicable | Risks / actions | Status | Evidence or gap | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 6.3 | Information security awareness, education and training | RT, BR | Phishing resistance; Obj 5 | R-10; T-10.2 | Partially implemented | 70% completion against a 95% target | HR Manager / GRC Analyst |
| 6.5 | Responsibilities after termination or change of employment | RT | Leaver access and asset return | R-12; T-12.1–12.3 | Partially implemented | Informal HR-to-IT email; no deadline | HR Manager |
| 6.8 | Information security event reporting | RT, LR | Staff report events promptly | R-18; T-18.1 | Partially implemented | Reporting mailbox works; procedure in draft | GRC Analyst |

### 3.3 Physical controls (A.7) — 1 assessed

| Control | Title | Reasons | Why applicable | Risks / actions | Status | Evidence or gap | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 7.4 | Physical security monitoring | BR | **Applies to the UK head office only.** Northstar runs no datacentre; Microsoft's facilities are assured through 5.23 (NSD-ISMS-004 §10) | No risk yet: new scenario to raise for the next assessment | To be assessed | Office alarm and access monitoring not yet reviewed | IT Manager |

### 3.4 Technological controls (A.8) — 19 assessed

| Control | Title | Reasons | Why applicable | Risks / actions | Status | Evidence or gap | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 8.1 | User endpoint devices | RT | Laptops in the UK office, UK homes and EU locations | R-20; T-20.1 | Partially implemented | BitLocker on 96% of devices; remote wipe works | IT Manager |
| 8.2 | Privileged access rights | RT | Admin control of Azure and Microsoft 365 | R-13, R-01, R-14; T-13.1, T-01.1, T-14.2 | Partially implemented | Separate admin accounts work; just-in-time access not in place | IT Manager |
| 8.3 | Information access restriction | RT | Customer data access limited to need | R-01; T-01.1 | Partially implemented | Standing engineer read access | Head of Engineering |
| 8.4 | Access to source code | RT | Protects code integrity | R-05, R-06; T-05.1, T-06.2 | Partially implemented | MFA works; branch protection not on all repositories | Head of Engineering |
| 8.5 | Secure authentication | RT, CO | MFA; insurer requirement (IP-13) | R-10, R-11; T-10.1, T-11.1 | Partially implemented | Staff MFA works; legacy authentication allowed; service accounts excluded | IT Manager |
| 8.8 | Management of technical vulnerabilities | RT, BR | Obj 7 patching target | R-17; T-17.1 | Partially implemented | Scanning works; 80% patched on time against a 95% target | Head of Engineering |
| 8.9 | Configuration management | RT | Azure secure baseline | R-08, R-02; T-08.1 | Partially implemented | Infrastructure as code partly used; no policy enforcement | Head of Engineering |
| 8.12 | Data leakage prevention | RT | Restricted data and AI tools | R-19; T-19.2 | Planned | No DLP policies yet | IT Manager |
| 8.13 | Information backup | RT, CO | Recovery within RPO and RTO | R-14; T-14.1, T-14.3 | Partially implemented | Daily backups work; no immutable copy; restores untested | IT Manager |
| 8.14 | Redundancy of information processing facilities | RT, CO | Regional failover for availability SLAs | R-09; T-09.2 | To be assessed | Failover never tested | Head of Engineering |
| 8.15 | Logging | RT, LR | Evidence for breach decisions | R-15, R-01, R-06; T-15.1, T-01.2, T-06.3 | Partially implemented | Central logging works; admins can delete logs; 30-day retention | IT Manager |
| 8.16 | Monitoring activities | RT | Detection of misuse and misconfiguration | R-01, R-08; T-01.2, T-08.2 | Partially implemented | Secure score reviewed irregularly; no bulk-export alert | Head of Engineering |
| 8.20 | Networks security | RT | Protects internet-facing services | R-17; T-17.2 | Planned | Web application firewall not yet deployed | Head of Engineering |
| 8.21 | Security of network services | RT | Secure configuration of network services | R-17; T-17.2 | Planned | As 8.20 | Head of Engineering |
| 8.23 | Web filtering | RT | Blocks unapproved AI and malicious sites | R-19, R-10; T-19.2 | Planned | No web filtering policy | IT Manager |
| 8.24 | Use of cryptography | RT, LR | Encryption and key management | R-06, R-20; T-06.1 | Partially implemented | Key Vault in use; some secrets outside it | Head of Engineering |
| 8.25 | Secure development life cycle | RT, BR | Northstar develops its own SaaS platform (INT-05) | R-07; T-07.1 | To be assessed | Dependency scanning untested | Head of Engineering |
| 8.28 | Secure coding | RT | Code review and secret scanning | R-05, R-06; T-05.1, T-06.2 | Partially implemented | Code review partial; no secret scanning | Head of Engineering |
| 8.32 | Change management | RT | Approved, reviewed deployments | R-05, R-07; T-05.1, T-07.2 | Partially implemented | Branch protection partial; no second approver for production | Head of Engineering |

## 4. Additional controls (not in Annex A)

| ID | Control | Reason | Link | Status |
| --- | --- | --- | --- | --- |
| NSD-C-01 | Software bill of materials (SBOM) verification for releases | RT | R-07; record AR-01, condition 2 | Planned: roadmap due to the Steering Group by June 2027 |
| NSD-C-02 | DORA contract terms for FS customers: audit rights, incident notification, exit plans | CO | IP-03; EXT-07 | To be assessed |

## 5. Controls awaiting assessment (45)

**Wave 2, due 29 January 2027.** The preliminary views below are a starting point only. Each one needs the same full assessment as section 3.

| Control | Title | Preliminary view |
| --- | --- | --- |
| 5.4 | Management responsibilities | Likely applicable (charter §6) |
| 5.5 | Contact with authorities | Likely applicable (ICO, NCSC: IP-08, IP-15) |
| 5.6 | Contact with special interest groups | Likely applicable (supports 5.7) |
| 5.8 | Information security in project management | Likely applicable (new-system workflow, NSD-ISMS-011 §4) |
| 5.11 | Return of assets | Likely applicable (leaver devices, R-12) |
| 5.14 | Information transfer | Likely applicable (NSD-ISMS-008 §4; ARM-12) |
| 5.28 | Collection of evidence | Likely applicable (ARM-22) |
| 5.32 | Intellectual property rights | Likely applicable (software licences, open source) |
| 5.33 | Protection of records | Likely applicable (ARM-20; retention) |
| 5.35 | Independent review of information security | Likely applicable (outsourced internal audit, charter §6) |
| 5.36 | Compliance with policies, rules and standards for information security | Likely applicable (NSD-ISMS-008 §9) |
| 5.37 | Documented operating procedures | Likely applicable |
| 6.1 | Screening | Likely applicable (UK and EU staff; EXT-09) |
| 6.2 | Terms and conditions of employment | Likely applicable |
| 6.4 | Disciplinary process | Likely applicable (NSD-ISMS-008 §9) |
| 6.6 | Confidentiality or non-disclosure agreements | Likely applicable (contractors, IP-05) |
| 6.7 | Remote working | **Likely applicable — priority** (hybrid and EU working, INT-08) |
| 7.1 | Physical security perimeters | Likely applicable, head office only |
| 7.2 | Physical entry | Likely applicable, head office only |
| 7.3 | Securing offices, rooms and facilities | Likely applicable, head office only |
| 7.5 | Protecting against physical and environmental threats | Likely applicable, head office only (EXT-12) |
| 7.6 | Working in secure areas | **Exclusion candidate**, if the office has no secure areas such as a server room. Confirm on site |
| 7.7 | Clear desk and clear screen | Likely applicable (office and home) |
| 7.8 | Equipment siting and protection | Likely applicable, head office only |
| 7.9 | Security of assets off-premises | **Likely applicable — priority** (ARM-25; home and EU working) |
| 7.10 | Storage media | Likely applicable (NSD-ISMS-008 removable media rules) |
| 7.11 | Supporting utilities | Likely applicable, head office only |
| 7.12 | Cabling security | **Exclusion candidate**, if there is no on-site network equipment beyond the ISP link. Confirm on site |
| 7.13 | Equipment maintenance | Likely applicable (endpoints) |
| 7.14 | Secure disposal or re-use of equipment | Likely applicable (NSD-ISMS-011 §8) |
| 8.6 | Capacity management | Likely applicable (platform capacity) |
| 8.7 | Protection against malware | Likely applicable (ARM-16; EDR) |
| 8.10 | Information deletion | Likely applicable (NSD-ISMS-011 §8) |
| 8.11 | Data masking | Likely applicable (NSD-ISMS-008 §4 test data; ARM-19) |
| 8.17 | Clock synchronization | Likely applicable (log evidence) |
| 8.18 | Use of privileged utility programs | Likely applicable |
| 8.19 | Installation of software on operational systems | Likely applicable |
| 8.22 | Segregation of networks | Likely applicable (ARM-09) |
| 8.26 | Application security requirements | Likely applicable |
| 8.27 | Secure system architecture and engineering principles | Likely applicable |
| 8.29 | Security testing in development and acceptance | Likely applicable (ARM-07) |
| 8.30 | Outsourced development | **Exclusion candidate**, if Northstar uses no outsourced developers. Confirm with the Head of Engineering |
| 8.31 | Separation of development, test and production environments | Likely applicable (NSD-ISMS-008 §4) |
| 8.33 | Test information | Likely applicable (NSD-ISMS-008 §4) |
| 8.34 | Protection of information systems during audit testing | Likely applicable (penetration tests) |

**The three exclusion candidates** (7.6, 7.12 and 8.30) are excluded only if the facts are confirmed, with a justification that meets the NSD-ISMS-018 §4 rules. None of them is based on cost or on supplier responsibility.

## 6. Findings from this assessment

| # | Finding | Action |
| --- | --- | --- |
| 1 | 17 controls in the treatment plan were missing from the initial sample | Added to section 3 |
| 2 | 5.27 is applicable, with no implementation and no plan | Escalated: propose action T-18.2 for NSD-ISMS-015 |
| 3 | 7.4 has no linked risk | Raise a physical security scenario for the head office in the next risk assessment |
| 4 | The 7.4 entry in the draft put "To be assessed" in the applicability column | Corrected: applicability is Yes or No; "To be assessed" is a status |
| 5 | R-20 in NSD-ISMS-014 recorded BitLocker as Effective, although 4% of devices are non-compliant | Corrected to Partially effective in NSD-ISMS-014 v0.2, to match 8.1 here |

## 7. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves applicability decisions | Pending, after Wave 2 | |
| Control owners | Confirm statuses and evidence | Pending | |
| Information Security / GRC Analyst | Prepared the SoA | Prepared | |

When approved, the version number and date are entered in the scope statement (NSD-ISMS-004 §3).

## 8. Change log

| Version | Change |
| --- | --- |
| 0.3 | Supplier milestone (NSD-ISMS-055 to 060). **5.21 assessed and moved from Wave 2:** applicable, justified by R-07 and the CI/CD provider; status To be assessed, because dependency scanning is untested. 5.19, 5.20, 5.22 and 5.23 updated with justifications and evidence references. **Statuses unchanged:** the milestone produced documents but no assessment evidence, and the SoA follows evidence, not documents. Counts: 48 assessed, 45 awaiting; To be assessed 12 → 13. |
| 0.2 | Aligned with the portfolio SoA draft (numbered NSD-ISMS-016 there; 016 is the acceptance criteria). Added its scope statement and exclusion principle. Applicability limited to two values: the draft's "To be assessed" applicability for 7.4 is now an implementation status. Evidence basis explained: statuses follow the simulated evidence in NSD-ISMS-014, rather than the draft's "To be assessed" for all 30, so the SoA does not contradict the risk register. Approver changed from Senior Management to the MD. |
| 0.1 | Initial assessment of 47 controls: the 30-control representative set plus 17 treatment-plan controls. 46 controls listed for Wave 2, with preliminary views and 3 exclusion candidates. Statuses derived from NSD-ISMS-014 using the NSD-ISMS-018 mapping. Two additional controls added. |

---

*Portfolio note: All control decisions and statuses are simulated for learning. They do not demonstrate actual implementation or certification.*
