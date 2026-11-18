# Northstar Digital Solutions Ltd — Information Classification and Handling Standard

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-008 |
| Version | 1.0 — Draft for approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (Annex A 5.10, 5.12, 5.13, 5.14, 7.10, 7.14, 8.10, 8.11, 8.12) |
| Related documents | [NSD-ISMS-006 Asset Register](06-information-asset-register.md) · [NSD-ISMS-007 Ownership Register](07-asset-ownership-register.md) · [NSD-ISMS-004 Scope](../01-initiation-and-context/04-isms-scope-statement.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Applies to | All employees, contractors and suppliers handling Northstar or customer information, in the UK and EU |
| Review frequency | Annually, and after a related incident or regulatory change |
| Classification | Internal |

---

## 1. Purpose

This standard defines four classification levels and the mandatory handling rules for each. It replaces the provisional levels used in NSD-ISMS-006.

Classification describes **confidentiality**: the harm if information is disclosed to the wrong people. Integrity and availability needs are recorded separately for each asset in NSD-ISMS-006 and assessed under the asset valuation methodology (NSD-ISMS-009).

## 2. Classification levels

| Level | Label colour | Definition: harm if disclosed | Examples at Northstar |
| --- | --- | --- | --- |
| **Restricted** | Red | **Severe:** reportable personal data breach, breach of customer contract, compromise of the platform, or serious loss of customer trust | Customer platform data; HR records and payroll bank details; encryption keys and secrets; privileged credentials; vulnerability and penetration test reports; incident and breach records; backups |
| **Confidential** | Amber | **Significant:** commercial, contractual or reputational harm, without a regulatory breach | Customer and supplier contracts; financial and billing records; source code; support tickets; architecture diagrams; business continuity plans; security event logs |
| **Internal** | Blue | **Limited:** minor embarrassment or inconvenience | Internal procedures; staff directory; general operational documentation; internal announcements |
| **Public** | Green | **None:** formally approved for release | Website content; approved marketing material; published policies and press releases |

**Note on security reports.** Vulnerability scan and penetration test reports are **Restricted**, because they describe how to attack Northstar. A high-level assurance summary written for customers, with findings removed, is **Confidential**.

## 3. How to classify

### 3.1 Decision steps

Asset owners answer these questions in order and stop at the first "Yes":

1. Does it contain customer platform data, credentials, keys, or details of unfixed vulnerabilities? → **Restricted**
2. Does it contain personal data listed as Restricted in section 3.3, or would disclosure be reportable to a regulator or customer? → **Restricted**
3. Would disclosure cause significant commercial, contractual or reputational harm? → **Confidential**
4. Has it been formally approved for public release (section 6)? → **Public**
5. Otherwise → **Internal**

### 3.2 Rules

| Rule | Requirement |
| --- | --- |
| Link to asset ratings | An asset with a High confidentiality rating in NSD-ISMS-006 is Restricted. Medium means Confidential, and Low means Internal or Public |
| Inheritance | A system, service, device or backup takes the highest classification of the information it is designed to hold |
| Aggregation | A collection can be more sensitive than its parts, so the owner classifies the whole. For example, a full staff export with home addresses is Restricted even if single entries are Internal |
| Default | Unlabelled information is treated as **Internal**. Unlabelled information containing personal or customer data is treated as **Confidential** at minimum |
| Customer data | Data that customers put into the platform is always **Restricted**, whatever label the customer uses |
| When in doubt | Apply the higher level and ask the asset owner |
| Over-classification | Avoid it. Unnecessary Restricted labels reduce the protection of truly Restricted information |

### 3.3 Personal data

| Level | Personal data |
| --- | --- |
| Restricted | Customer platform data; HR, payroll and bank details; identity documents; special category data such as health or diversity data; bulk personal data exports; breach records |
| Confidential | Business contact data in contracts and CRM; customer support tickets; prospect and marketing data |
| Internal | Staff names, work emails and job titles in the company directory |

The Data Protection lead confirms the classification of any new personal data set.

### 3.4 Information received from others

Information received from customers, suppliers or partners is handled at the equivalent or a higher level:

| External marking | Northstar level |
| --- | --- |
| "Strictly confidential", "Secret", "Restricted" or equivalent | Restricted |
| "Confidential" or "Commercial in confidence" | Confidential |
| No marking but contains personal or commercial data | Confidential at minimum |
| Unclear | Restricted until the owner decides |

## 4. Handling rules

These rules are mandatory. Where a rule cannot be met, use the exceptions process in section 8.

| Activity | Internal | Confidential | Restricted |
| --- | --- | --- | --- |
| **Who may access** | Employees and contractors | Named roles with a business need | Named individuals approved by the owner; access reviewed quarterly |
| **Storage** | Approved company services (Microsoft 365, platform) | Approved locations with access groups; never personal devices or personal cloud accounts | Approved Restricted locations only: platform databases in the correct Azure region, Restricted SharePoint sites, Key Vault, privileged access vault. **No local copies on endpoints** |
| **Labelling** | "Internal" label, the default | "Confidential" sensitivity label | "Restricted" sensitivity label, with encryption applied automatically |
| **Internal email and chat** | Permitted | Permitted to people with a need | Do not attach. Share a link to the Restricted location instead |
| **External sharing** | Permitted for normal business; owner approval otherwise | Contract or NDA in place; encrypted; owner approves | Prohibited unless the owner **and** the Data Protection lead approve; encrypted and logged. Customer data goes only to that customer |
| **Transmission** | TLS-protected company services | TLS internally; encrypted email or secure share externally | Encrypted end to end through approved channels only |
| **Generative AI tools** | Approved company tools only | Approved enterprise tools with contractual data protection only | **Prohibited** (INT-13) |
| **Development and test environments** | Permitted | Masked or synthetic data only | **Never copied**: use synthetic or masked data (Annex A 8.11, 8.33) |
| **Removable media** | Company-encrypted devices | Company-encrypted devices, with owner approval | **Prohibited** |
| **Printing** | Permitted | Only when needed; collect immediately | Prohibited unless the owner approves |
| **Suppliers and sub-processors** | Under contract | Contract with confidentiality and security clauses | Approved sub-processor with a DPA; customer approval where customer data is involved |
| **Monitoring** | Not required | Access logged where the system supports it | Access logged and reviewed; DLP alerts investigated |
| **Disposal** | Normal deletion; paper in confidential waste | Secure deletion; paper shredded | Secure deletion, with crypto-erasure or a destruction record for media and cloud stores (Annex A 7.14, 8.10) |
| **Loss or suspected disclosure** | Report to IT Operations | Report immediately as a security incident | Report immediately: this may be a personal data breach with a 72-hour reporting deadline |

**Public** information needs no handling controls once published. Before publication it is handled as Internal and approved under section 6.

## 5. Labelling

| Information type | How it is labelled |
| --- | --- |
| Documents and emails in Microsoft 365 | Microsoft Purview sensitivity labels. The default label is **Internal**, and Restricted labels apply encryption automatically (INT-14) |
| Visible marking | Header or footer text, e.g. "RESTRICTED — NORTHSTAR DIGITAL SOLUTIONS". Public material carries no marking |
| Systems, databases and repositories | Individual records cannot be labelled, so the classification is recorded in NSD-ISMS-006 and shown in the system description or login banner |
| Paper and offline copies | Marked on every page |
| Customer data in the platform | Covered by the platform's classification (AST-001), not labelled record by record |

Purview labels and data loss prevention rules are configured by IT Operations. The IT Manager owns the configuration (AST-008).

## 6. Responsibilities

| Role | Responsibility |
| --- | --- |
| Asset owners | Classify their assets, approve reclassification, approve exceptions within their authority |
| Data Protection lead | Confirms the classification of personal data; co-approves external sharing of Restricted data |
| Marketing / Sales lead | With the asset owner, approves information for Public release after checking it for sensitive content |
| IT Manager and custodians | Enforce technical controls: labels, encryption, DLP, access control |
| GRC Analyst | Maintains this standard, provides guidance, monitors compliance and reports to the Steering Group |
| All staff and contractors | Handle information according to its classification and report mishandling |

## 7. Reclassification

| Trigger | Example |
| --- | --- |
| Publication | A product sheet is approved for the website: Internal → Public |
| Change in sensitivity over time | A vulnerability report after all findings are fixed: Restricted → Confidential |
| Aggregation | Records combined into a bulk export: Confidential → Restricted |
| Contract, regulatory or incident change | A new customer contract requires stricter handling |

- **Upgrading:** anyone may handle information at a higher level straight away. The owner confirms within 5 working days.
- **Downgrading:** only the owner may approve it. The Data Protection lead also approves if personal data is involved.
- Every reclassification of a registered asset is recorded in NSD-ISMS-006.

## 8. Exceptions

1. The requester submits the exception to the GRC Analyst, with the business reason and compensating controls.
2. The GRC Analyst assesses the risk.
3. The asset owner approves exceptions for Confidential information. The Managing Director approves exceptions for Restricted information.
4. Exceptions last at most 12 months and are recorded in the exceptions log.

## 9. Compliance

- Classification and handling are covered in induction and annual awareness training (Obj 5).
- DLP alerts and access logs for Restricted locations are reviewed monthly.
- The GRC Analyst runs quarterly spot checks on labelling and storage locations.
- Deliberate or repeated breaches of this standard are handled as security incidents and may lead to disciplinary action.

## 10. Current asset classification

Classifications in NSD-ISMS-006 v1.0, checked against this standard:

| Level | Assets | Count |
| --- | --- | --- |
| Restricted | AST-001, 002, 006, 007, 008, 009, 010, 011, 016, 017 | 10 |
| Confidential | AST-003, 004, 005, 012, 013, 014, 015, 018, 019, 020 | 10 |
| Internal | None yet registered | 0 |
| Public | None yet registered | 0 |

The check found one mismatch. Source code (AST-004) was Confidential but had a High confidentiality rating. It stays **Confidential**: secrets are kept out of the repositories by secret scanning and held separately as AST-006 (Restricted). Its confidentiality rating was corrected to Medium in NSD-ISMS-006 v1.0.

No Internal or Public assets are registered yet, because the first 20 are the highest-value assets. Internal assets will appear when the section 5 items in NSD-ISMS-006 are added.

## 11. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the standard | Pending | |
| Data Protection lead | Validates personal data rules | Pending | |
| IT Manager | Validates technical controls | Pending | |
| Information Security / GRC Analyst | Prepared the standard | Prepared | |

---

*Portfolio note: This is a proposed classification standard, not an approved company policy.*
