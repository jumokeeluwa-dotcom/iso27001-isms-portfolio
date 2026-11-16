# Northstar Digital Solutions Ltd — Supplier Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-055 |
| Version | 0.2 — Simulated records |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 5.19–5.23 |
| Status | **Simulated. Suppliers named "Fictional … Ltd" are invented. Where the asset register shows a provider as "TBC", this register does the same rather than invent one. No contract review or assessment is represented** |
| Position as at | 30 September 2027 |
| Policy | [NSD-ISMS-026 Supplier Security Policy](../05-policies/26-supplier-security-policy.md): tiers (§3), contract terms (§4), sub-processors (§5) |
| Related records | Assessments: NSD-ISMS-058 · Risks: [NSD-ISMS-014](../03-risk-management/14-risk-register.md) (R-16, R-02, R-07) · Contracts: AST-015 · KPI-14 |
| Register owner | Information Security / GRC Analyst (NSD-ISMS-026 §7) |
| Classification | Confidential |

---

## 1. Purpose

This is the master list of every supplier within the scope of NSD-ISMS-026: who they are, what they do, which Northstar information and systems they touch, and how critical they are. It is the source of the KPI-14 denominator (the number of Critical suppliers), so an error in tiering is an error in the KPI.

**One register per item:** assessment results live in NSD-ISMS-058, supplier risks in NSD-ISMS-014, and contracts in AST-015. This register points to them.

## 2. Supplier inventory

| ID | Supplier | Service | Assets (NSD-ISMS-006) | Information and access | Highest class. | Sub-processor of customer data? | Locations |
| --- | --- | --- | --- | --- | --- | --- | --- |
| SUP-01 | Microsoft | Azure: hosting, Key Vault, Backup, Monitor | AST-001, 006, 007, 011, 012 | Customer data (UK and EU); production environment | Restricted | **Yes** | UK and EU regions as configured; Microsoft support access locations to be confirmed from the DPA |
| SUP-02 | Microsoft | Microsoft 365 and Entra ID | AST-008, 009 | Staff email and files; identity for **all** access, including administrators | Restricted | **To confirm:** customer personal data may arrive in support email | To be confirmed for the tenant |
| SUP-03 | Fictional Payroll Services Ltd | Payroll | Part of AST-002 | Employees' salary and bank details | Restricted | No | To be confirmed |
| SUP-04 | Fictional IT Support Ltd | Managed IT support (MSP) | AST-008, 009, 020 | Support access to corporate systems through guest accounts (R-16). **Whether it holds administrator roles is not recorded** | Restricted | No | To be confirmed |
| SUP-05 | Fictional Payment Services Ltd | Payment processing for Northstar's billing | AST-003 | Customer billing contacts and transactions; card data handled by the provider | Confidential | No: Northstar is the controller | To be confirmed |
| SUP-06 | Fictional CRM Solutions Ltd | Customer relationship management | **Not in the asset register** | Customer and prospect contacts (personal data) | Confidential | No: Northstar is the controller | To be confirmed |
| SUP-07 | Fictional Security Monitoring Ltd | Managed security monitoring | AST-012 | Read access to security logs across Azure and Microsoft 365. Logs contain user IDs and IP addresses, including customers' users | Confidential | **To confirm** | To be confirmed |
| SUP-08 | Fictional Recruitment Services Ltd | Recruitment | — | Applicants' personal data | Confidential | No | To be confirmed |
| SUP-09 | Code repository and CI/CD provider [TBC] | Source control and build pipelines | AST-004, 005 | Source code; pipeline secrets; **deploys to production** | Restricted (secrets) | To confirm: should be No, if customer data never enters repositories | To be confirmed |
| SUP-10 | Support ticketing provider [TBC] | Customer support system | AST-013 | Customer tickets, which can contain customers' personal data and screenshots | Confidential | **Likely yes** | To be confirmed |
| SUP-11 | HR system provider [TBC] | HR records | AST-002 | HR records; the leaving date that triggers automated account removal (T-12.3) | Restricted | No | To be confirmed |
| SUP-12 | Finance and billing system provider [TBC] | Accounting and billing | AST-003 | Financial and billing records | Confidential | No | To be confirmed |
| SUP-13 | External internal auditor (NSD-ISMS-030) | ISO/IEC 27001 internal audit | AST-016, 017 (as evidence) | Read access to audit evidence, including Restricted records | Restricted | No | UK |
| SUP-14 | Penetration testing provider [TBC] | Annual platform penetration test (NSD-ISMS-029) | AST-007, 016 | Test access to the platform; produces Restricted reports | Restricted | To confirm: testing may expose customer data | To be confirmed |
| SUP-15 | Contractor agencies [TBC] | Contract staff | Per contractor | Contractor accounts, sometimes with production access (see RCA-01) | Depends on role | Depends on role | UK and EU |
| SUP-16 | Incident response provider, through the cyber insurer's panel [TBC] | Forensics in a serious incident (NSD-ISMS-051 §3) | All, when engaged | Full access to evidence and systems during an incident | Restricted | Yes, when engaged | To be confirmed |

## 3. Tier and ownership

Tiers follow NSD-ISMS-026 §3: **Critical** (processes customer data, has privileged access, or the platform depends on it), **High** (Northstar personal data or Confidential information) and **Standard.** The draft's Medium and Low tiers are not in the policy, so they are not used.

**Rule for unknowns:** where a fact that decides the tier is not yet known, the supplier is treated at the **higher** tier until it is confirmed. Under-tiering a supplier means under-assessing it.

| ID | Tier | Reason | Draft tier | Business owner | Review (026 §3) |
| --- | --- | --- | --- | --- | --- |
| SUP-01 | **Critical** | Customer data; the platform depends on it | Critical | Head of Engineering | Annually |
| SUP-02 | **Critical** | Identity for all privileged access; named Critical in 026 §3 | High | IT Manager | Annually |
| SUP-03 | High | Northstar personal data | High | HR Manager | Every 2 years |
| SUP-04 | **Critical (provisional)** | Critical if it holds any administrator role; High if not. **To confirm** | High | IT Manager | Annually until confirmed |
| SUP-05 | High | Confidential and personal data | High | Finance Manager | Every 2 years |
| SUP-06 | **High** | Personal data | Medium | Sales lead | Every 2 years |
| SUP-07 | **Critical** | Broad access to security telemetry; incident response (BIA A3) depends on it; may see customer data | High | GRC Analyst | Annually |
| SUP-08 | **High** | Personal data | Medium | HR Manager | Every 2 years |
| SUP-09 | **Critical** | Deploys to production, so it is a privileged route into the platform; named Critical in 026 §3 | Not listed | Head of Engineering | Annually |
| SUP-10 | **Critical** | Likely processes customer data | Not listed | Customer Support Manager | Annually |
| SUP-11 | High | Personal data | Not listed | HR Manager | Every 2 years |
| SUP-12 | High | Confidential information | Not listed | Finance Manager | Every 2 years |
| SUP-13 | High | Restricted information (see gap 5) | Not listed | Managing Director | Every 2 years |
| SUP-14 | High | Restricted information (see gap 5) | Not listed | GRC Analyst | Before each engagement |
| SUP-15 | High; **Critical** for any agency whose contractors have production or privileged access | By access | Not listed | HR Manager | By tier |
| SUP-16 | **Critical** | Full access when engaged. Assessed **before** an incident, because there is no time during one | Not listed | GRC Analyst | Annually |

**Result:** 7 Critical suppliers (one provisional), against 1 in the draft and 5 in the Q2 2027 KPI count; 9 High.

## 4. Gaps this register found

| # | Gap | Why it matters | Route |
| --- | --- | --- | --- |
| 1 | The draft listed **one** Critical supplier. The Q2 2027 dashboard counted **five** (KPI-14: 4 of 5 assessed). The policy's own criteria give **seven** | KPI-14 has been measured against an incomplete list. From Q3 2027 it is reported against the new count, with the change explained, **not compared like for like** with Q2. Which five suppliers were counted, and their assessment records, are not in the portfolio (see NSD-ISMS-058 §2) | NSD-ISMS-044 note; KPI owner (Finance Manager) |
| 2 | Eight suppliers that the asset register already relies on were not listed | Unlisted suppliers are never assessed | Added (SUP-09 to SUP-16) |
| 3 | The CRM (SUP-06) holds customer contacts but is **not in the asset register** | An unregistered asset has no owner, classification or risk assessment | NSD-ISMS-006 update (asset owner: Sales lead) |
| 4 | SUP-02, 07, 09, 10 and 14 may process customer personal data | NSD-ISMS-026 §5 requires each sub-processor to be on the customer-facing list, and customers notified **before** it processes their data. If any already does and is not listed, a requirement is not met | Data Protection lead confirms; **possible nonconformity** (NSD-ISMS-034) if confirmed |
| 5 | The tier criteria do not cover suppliers holding **Restricted** Northstar information that is not personal data, such as penetration test reports | SUP-13 and SUP-14 were placed in High by judgement, not by rule | Criteria to be refined in NSD-ISMS-056, then NSD-ISMS-026 updated |
| 6 | Two Critical services come from one supplier (SUP-01, SUP-02) | Concentration risk (EXT-05): one supplier failure affects platform, identity and email together | Recorded in R-09 and the BIA; exit and concentration assessed in NSD-ISMS-056 |
| 7 | Contractor agencies (SUP-15) were not treated as suppliers | Contractor access is the subject of AUD03-F01 and RCA-01 | Agencies brought into supplier assessment by access tier |

## 5. Fields held for each supplier

The tables above summarise. The full record holds:

| Field | Notes |
| --- | --- |
| Legal entity, contacts, security contact | The security contact is used for incident reports (026 §4.5) |
| Service, assets, business owner | **One** business owner |
| Information and access | Type: none, user, or privileged; system and data |
| Highest classification | From NSD-ISMS-008 |
| Sub-processor of customer data? | Yes / No / To confirm; date added to the customer-facing list |
| Processing and support locations; transfer mechanism | For any transfer outside the UK or EU, the mechanism (R-02) |
| Supports services for financial services customers? | If yes, DORA terms apply (026 §4; IP-03) |
| Tier and reason | Reviewed whenever access or data changes |
| Contract and DPA | Reference in AST-015; dates; whether the 026 §4 clauses are present |
| Assessment | Latest result and next date: **held in NSD-ISMS-058** |
| Related risks | IDs in NSD-ISMS-014 |
| Concentration and substitutability | How hard it would be to replace the supplier |
| Exit plan | Required for Critical suppliers |
| Status | Proposed, Active, Exiting or Exited (with the 026 §11 confirmation) |

## 6. Keeping it complete

| Check | Who | When |
| --- | --- | --- |
| A new supplier is recorded and tiered **before** it gets access or data | Business owner, with the GRC Analyst | Before onboarding |
| Changes to service, access, data, location or sub-processors | Business owner | Within 10 working days of the change |
| **Reconciliation against Finance's list of paid suppliers,** to find suppliers no one registered (as happened with SUP-06) | GRC Analyst, with the Finance Manager | Quarterly |
| **Reconciliation against Entra ID guest accounts,** so every external account belongs to a registered supplier (R-16) | IT Manager | Quarterly |
| Full register review: tiers, owners, status | GRC Analyst | Quarterly, before KPI-14 is calculated |
| Exit confirmed (026 §11) | Business owner | At contract end |

Reconciling against other records is what makes the register complete. Relying on people to report new suppliers misses the ones they never thought of as suppliers.

## 7. Statement of Applicability

The register supports Annex A **5.19** (supplier relationships), **5.21** (ICT supply chain), **5.22** (monitoring) and **5.23** (cloud services). The SoA currently shows 5.19, 5.20 and 5.22 as **To be assessed,** and 5.21 as "likely applicable" in Wave 2. The SoA entries, with applicability, justification and status, are updated **at the end of this milestone,** once assessment evidence exists (NSD-ISMS-058). The register alone shows that suppliers are listed, not that they are managed.

## 8. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| ISMS Steering Group | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-051) | Eight fictional suppliers with an initial criticality |
| 0.2 | Numbered NSD-ISMS-055. Register owner changed to the GRC Analyst (NSD-ISMS-026 §7); "Procurement Manager" is not a charter role. Business owners mapped to charter roles: "Sales Director" became the Sales lead, "Security Lead" the GRC Analyst. Tiers aligned with NSD-ISMS-026 (Critical, High, Standard), with a rule to treat unknowns at the higher tier. **Re-tiering:** Microsoft 365, the MSSP (SUP-07) and, provisionally, the MSP (SUP-04) raised to Critical; CRM and recruitment raised to High. **Eight suppliers added** that the asset register already relies on, including the code pipeline, the ticketing system, contractor agencies and the incident response provider. Columns added for assets, classification, sub-processor status and location. Seven gaps recorded and routed, including a CRM missing from the asset register and possibly unlisted sub-processors. Reconciliations against Finance and Entra ID replace "reviewed periodically". SoA impact noted. |

---

*Portfolio disclaimer: All supplier entries are fictional or unconfirmed. No actual supplier assessment, contract review or approval is represented.*
