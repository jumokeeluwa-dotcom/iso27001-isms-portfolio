# Northstar Digital Solutions Ltd — Information Asset Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-006 |
| Version | 1.0 — Draft for owner review |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (Annex A 5.9, 5.10, 5.12, 5.13) |
| Related documents | [NSD-ISMS-001 Charter](../01-initiation-and-context/01-isms-project-charter.md) · [NSD-ISMS-002 Context](../01-initiation-and-context/02-organisational-context-register.md) · [NSD-ISMS-003 Interested Parties](../01-initiation-and-context/03-interested-party-requirements-register.md) · [NSD-ISMS-004 Scope](../01-initiation-and-context/04-isms-scope-statement.md) · [NSD-ISMS-007 Ownership](07-asset-ownership-register.md) · [NSD-ISMS-008 Classification](08-information-classification-scheme.md) · [NSD-ISMS-009 Valuation](09-asset-valuation-methodology.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Quarterly for Restricted assets; six-monthly for all others; and after material change |
| Classification | Internal — Simulated portfolio document |

---

## 1. Purpose

This register records the information and other associated assets inside the ISMS scope (NSD-ISMS-004). For each asset it records the owner, custodian, location, classification and security requirements.

It meets Annex A 5.9 (inventory of information and associated assets) and delivers charter objective **Obj 2**: 100% of in-scope assets with a named owner by month 3.

This version registers the 20 highest-value assets. Section 5 lists further assets that have been identified and will be added at the first quarterly review.

## 2. Conventions

| Term | Meaning |
| --- | --- |
| Asset ID | AST-nnn. IDs are never reused. A retired asset keeps its ID with status "Retired" |
| Type | **Information:** the data itself. **Associated asset:** a system, service, credential or device that stores, processes or protects information |
| Owner | Accountable for the asset: approves classification, access and acceptable use (Annex A 5.9) |
| Custodian | Operates the asset day to day on the owner's behalf |
| Classification | Four levels defined in NSD-ISMS-008: **Public**, **Internal**, **Confidential**, **Restricted** (highest). Classification reflects the confidentiality rating: High = Restricted, Medium = Confidential |
| Inheritance rule | An associated asset takes the highest classification of the information it is designed to hold |
| C / I / A | Confidentiality, integrity and availability rated High, Medium or Low using the criteria in NSD-ISMS-009. Criticality tiers (Critical, High, Medium, Low) are recorded in NSD-ISMS-009 §6 |
| Owner roles | Only roles defined in charter §6 or the interested-party register are used |

**Classification levels** (summary; NSD-ISMS-008 is the master)

| Level | Meaning | Example |
| --- | --- | --- |
| Restricted | Disclosure would cause severe harm: regulatory breach, loss of customer trust, or compromise of the platform | Customer platform data, encryption keys |
| Confidential | Disclosure would cause significant harm to Northstar or a third party | Contracts, source code |
| Internal | For staff and contractors only; limited harm if disclosed | Internal procedures |
| Public | Approved for public release | Website content |

## 3. Asset inventory

| ID | Asset | Type | Location / hosting | Owner | Custodian | Classification |
| --- | --- | --- | --- | --- | --- | --- |
| AST-001 | Customer platform data (production databases) | Information | Azure UK regions; Azure EU region for EU customers | Head of Engineering | DevOps team | Restricted |
| AST-002 | Employee and contractor HR records (UK and EU) | Information | HR system [TBC]; restricted SharePoint site | HR Manager | IT Manager | Restricted |
| AST-003 | Financial and billing records | Information | Finance and billing systems [TBC] | Finance Manager | IT Manager | Confidential |
| AST-004 | Source code repositories | Information | Code repository [provider TBC] | Head of Engineering | DevOps team | Confidential |
| AST-005 | CI/CD pipelines and build configuration | Associated asset | CI/CD platform [provider TBC] | Head of Engineering | DevOps team | Confidential |
| AST-006 | Encryption keys and application secrets | Associated asset | Azure Key Vault | Head of Engineering | DevOps team | Restricted |
| AST-007 | SaaS production environment | Associated asset | Azure subscriptions, UK and EU regions | Head of Engineering | DevOps team / IT Operations | Restricted |
| AST-008 | Microsoft 365 tenant (email, SharePoint, Teams) | Associated asset | Microsoft cloud | IT Manager | IT Operations | Restricted |
| AST-009 | Identity directory (Entra ID) | Associated asset | Microsoft cloud | IT Manager | IT Operations | Restricted |
| AST-010 | Privileged administrator and break-glass credentials | Associated asset | Privileged access vault [TBC] | IT Manager | IT Operations | Restricted |
| AST-011 | Backups of platform and corporate data | Information | Azure Backup / backup provider [TBC], same region as source | IT Manager | IT Operations | Restricted |
| AST-012 | Security event logs | Information | Azure Monitor / SIEM [TBC] | GRC Analyst | IT Operations | Confidential |
| AST-013 | Customer support records | Information | Support ticketing system [TBC] | Customer Support Manager | Customer Support team | Confidential |
| AST-014 | Customer contracts and data processing agreements | Information | Restricted SharePoint site | Sales lead | Sales team | Confidential |
| AST-015 | Supplier and sub-processor contracts | Information | Restricted SharePoint site | Finance Manager | GRC Analyst | Confidential |
| AST-016 | Vulnerability scan and penetration test reports | Information | Restricted SharePoint site | GRC Analyst | IT Manager | Restricted |
| AST-017 | Incident and personal data breach records | Information | Restricted SharePoint site / ticketing | GRC Analyst | Data Protection lead | Restricted |
| AST-018 | Technical and architecture documentation (incl. data-flow diagrams) | Information | Engineering wiki / SharePoint | Head of Engineering | DevOps team | Confidential |
| AST-019 | Business continuity and disaster recovery plans | Information | SharePoint, plus offline copy | Managing Director | IT Manager | Confidential |
| AST-020 | Company endpoints (laptops and mobile devices) | Associated asset | UK office, UK homes, EU locations | IT Manager | Assigned user | Confidential |

AST-020 is Confidential, not Restricted, because the handling rules will prohibit storing Restricted data locally on endpoints. If that rule cannot be enforced, the classification rises to Restricted.

## 4. Security requirements

| ID | Personal data | C | I | A | Key security requirements | Links |
| --- | --- | --- | --- | --- | --- | --- |
| AST-001 | Yes: customers' users and data subjects | H | H | H | Encryption at rest and in transit; least-privilege access; EU data stays in the EU region; access logging; tested restore | INT-04, EXT-03; IP-01, IP-03, IP-09 |
| AST-002 | Yes: UK and EU staff | H | H | M | HR-only access; statutory retention per country; safeguards for UK–EU transfers | INT-07, EXT-09; IP-04, IP-05 |
| AST-003 | Limited: billing contacts | M | H | M | Finance-only access; approval for changes to payment details; statutory retention (to confirm) | INT-12; IP-07 |
| AST-004 | No | M | H | M | MFA on repository; branch protection; mandatory code review; secret scanning | INT-05; IP-01, IP-02 |
| AST-005 | No | M | H | M | Restricted pipeline access; separation between code approval and production deployment; build integrity checks | INT-05, EXT-08 |
| AST-006 | No | H | H | H | Stored only in Key Vault; rotation schedule; least privilege; every access logged | INT-04, INT-05 |
| AST-007 | Yes | H | H | H | Secure configuration baseline; network segmentation; monitoring and alerting; tested regional failover | INT-04, EXT-05; IP-01, IP-10 |
| AST-008 | Yes | H | H | M | Conditional access; sensitivity labels; data loss prevention; retention policies; controls on AI tools | INT-04, INT-13; IP-10 |
| AST-009 | Yes: staff identities | H | H | H | MFA for all users; conditional access; joiner/mover/leaver process; quarterly access reviews | INT-07; IP-04, IP-05 |
| AST-010 | No | H | H | H | Vaulted; MFA; break-glass use approved by the MD; every use logged and reviewed by the GRC Analyst | INT-01; IP-13 |
| AST-011 | Yes | H | H | H | Encrypted; immutable or offline copy; restore tested at least annually; same residency as the source | EXT-05; IP-01, IP-13 |
| AST-012 | Limited: user IDs, IP addresses | M | H | M | Protected against tampering; defined retention; admins cannot delete logs; independent review | INT-10; IP-08, IP-14 |
| AST-013 | Yes: customer contacts | M | M | M | Role-based access; no production data in attachments; defined retention | IP-01 |
| AST-014 | Limited: contact names | M | H | L | Sales and legal access only; version control; obligation tracking | EXT-06, EXT-07; IP-01, IP-03 |
| AST-015 | Limited: contact names | M | H | L | Restricted access; renewal and review tracking; sub-processor list kept current | EXT-08; IP-11, IP-12 |
| AST-016 | No | H | H | L | Need-to-know access; encrypted; shared only with remediation owners | INT-04; IP-02, IP-14 |
| AST-017 | Yes | H | H | M | Need-to-know access; evidence preserved; breach log supports 72-hour reporting | INT-10; IP-08, IP-09, IP-13 |
| AST-018 | No | M | M | L | Staff-only access; kept current with architecture changes | INT-06; IP-14 |
| AST-019 | Limited: contact lists | M | H | H | Available when primary systems are down; tested and updated annually | EXT-05, EXT-12; IP-01, IP-03 |
| AST-020 | Yes | M | M | M | Full-disk encryption; EDR; device management with remote wipe; patching; no local Restricted data | INT-08; IP-13 |

The **Links** column traces each asset to the context issues (NSD-ISMS-002) and interested parties (NSD-ISMS-003) that create its requirements. Risks for each asset will be recorded in the asset risk mapping (NSD-ISMS-010).

## 5. Identified but not yet registered

These in-scope assets were identified in this review and will be added at the first quarterly review:

- Staging, development and test environments (Scope §7).
- Marketing and prospect contact data, which has PECR implications (Scope §8).
- ISMS policies, records and audit evidence.
- Payroll system or outsourced payroll data (IP-12).
- Head office network and telecommunications services.

## 6. Ownership observations

| Owner | Assets owned |
| --- | --- |
| Head of Engineering | 6: AST-001, 004, 005, 006, 007, 018 |
| IT Manager | 5: AST-008, 009, 010, 011, 020 |
| GRC Analyst | 3: AST-012, 016, 017 |
| Finance Manager | 2: AST-003, 015 |
| HR Manager, Customer Support Manager, Sales lead, Managing Director | 1 each |

Points to resolve in the Asset Ownership Register (NSD-ISMS-007):

- **Concentration.** Engineering and IT own 11 of 20 assets, mostly Restricted ones. Ownership must have deputies, and the owners need time to do reviews (INT-01, INT-02).
- **Segregation of duties.** Security logs (AST-012) are owned by the GRC Analyst, not IT, so administrators do not control the record of their own actions. Privileged credentials (AST-010) are owned by the IT Manager, but their use is reviewed by the GRC Analyst.
- **Business ownership.** Customer platform data (AST-001) is owned by the Head of Engineering. The Data Protection lead should confirm this is right, since Northstar is the processor and the customer is the controller.

## 7. Fields held in the operational register

The working register will be a spreadsheet. It holds these extra fields for each asset:

| Field | Source |
| --- | --- |
| Lifecycle status (planned, active, retired) | Asset owner |
| Data subjects and processing purpose | Records of processing (Art. 30) |
| Retention period and disposal method | Retention schedule (Annex A 5.33, 8.10) |
| Supporting systems and suppliers | Supplier register (IP-10 to IP-12) |
| Linked risks and controls | Asset risk mapping (NSD-ISMS-010) and SoA |
| Last reviewed date and reviewer | Review process (NSD-ISMS-011) |

## 8. Responsibilities

**Asset owners** are accountable for:

- Approving the asset's classification.
- Defining acceptable use (Annex A 5.10).
- Authorising access and reviewing it at least quarterly for Restricted assets.
- Setting retention requirements with the Data Protection lead.
- Reporting significant changes, transfers or retirement of the asset.

**Custodians** are responsible for:

- Operating the controls the owner requires.
- Keeping the asset's records current.
- Reporting incidents and control failures to the owner.

**The GRC Analyst** maintains the register, coordinates reviews and reports owner coverage to the Steering Group as the measure for Obj 2.

## 9. Maintenance and review

- Restricted assets are reviewed quarterly. All other assets are reviewed every six months.
- The register is updated whenever an asset is introduced, changed, transferred, retired or disposed of.
- Changes are approved through the Asset Review and Approval Process (NSD-ISMS-011).
- A change to scope (NSD-ISMS-004) triggers a check of this register.

## 10. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the register and ownership assignments | Pending | |
| IT Manager | Validates technology assets | Pending | |
| Data Protection lead | Validates personal data assets | Pending | |
| Information Security / GRC Analyst | Maintains register | Prepared | |

---

*Portfolio note: All assets and assignments are fictional examples. Named roles are proposed business roles, not actual approvals.*
