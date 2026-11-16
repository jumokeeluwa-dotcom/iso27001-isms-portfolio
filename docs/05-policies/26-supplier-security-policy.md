# Northstar Digital Solutions Ltd — Supplier Security Policy

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-026 |
| Version | 0.3 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (Annex A 5.19, 5.20, 5.21, 5.22, 5.23) |
| Parent policy | [NSD-ISMS-022 Information Security Policy](22-information-security-policy.md) |
| Policy owner | Finance Manager (owns supplier contracts, AST-015, and risk R-16) |
| Supporting role | Information Security / GRC Analyst (supplier security assessments) |
| Approver | Managing Director |
| Review frequency | Annually |
| Classification | Internal |

---

## 1. Purpose

Information security risks from suppliers are identified, assessed, written into contracts, monitored and closed down when the relationship ends.

## 2. Scope

The policy covers every supplier that:

- accesses, processes, stores or transmits Northstar or customer information;
- has access to Northstar systems;
- supports in-scope services.

This includes cloud providers, sub-processors, outsourced HR, payroll and IT services, development tool providers and contractors' companies (IP-10, IP-11, IP-12, IP-17).

## 3. Supplier tiers

Every supplier is given a tier before onboarding. The tier sets how deeply it is assessed and how often it is reviewed. Where a fact that decides the tier is unknown, the higher tier applies until it is confirmed. The method is set out in NSD-ISMS-056 §3.

| Tier | Criteria | Examples | Assessment before onboarding | Review |
| --- | --- | --- | --- | --- |
| **Critical** | Processes customer data; has privileged or production access; or supports a BIA activity with an RTO of 4 hours or less (A1–A3) with no workaround | Microsoft (Azure, Microsoft 365); code repository and CI/CD provider; sub-processors | ISO 27001 certificate or SOC 2 report reviewed, **plus** a security questionnaire; DPA in place | **Annually** |
| **High** | Not Critical, and holds Restricted or Confidential information, processes Northstar personal data, or has user-level access to Northstar systems | Payroll and HR providers; MSP | Questionnaire, plus certificate where available | Every 2 years |
| **Standard** | No access to systems or Confidential data | Office services | Contract terms only | At renewal |

Supplier concentration risk, such as reliance on Microsoft (EXT-05), is recorded in the risk register and the BC plan.

## 4. Contract requirements

Contracts with Critical and High suppliers must include:

1. confidentiality obligations;
2. security responsibilities, including the shared-responsibility split for cloud services;
3. a **data processing agreement** under Article 28 GDPR, where personal data is processed;
4. access limits and compliance with NSD-ISMS-023;
5. **reporting security incidents to Northstar within 24 hours of discovery,** so Northstar can meet its own duties to customers and regulators;
6. control over subcontracting and sub-processors, including advance notice of changes;
7. business continuity and recovery commitments;
8. audit or assurance rights;
9. secure return or deletion of information at exit, with written confirmation.

**Financial services customers (IP-03).** Suppliers that support services for these customers must also accept terms that let Northstar meet DORA obligations passed down from them: audit and access rights, incident notification and exit support.

## 5. Sub-processors

1. Northstar keeps an up-to-date **sub-processor list**, available to customers.
2. New sub-processors are notified to customers, or approved by them, as each customer's DPA requires, **before** they process customer data.
3. Sub-processors must keep EU customer data in the EU unless a lawful transfer mechanism is in place (R-02).

## 6. Supplier access

Supplier access to Northstar systems follows NSD-ISMS-023 §10: an internal sponsor, MFA, least privilege, **90-day expiry**, monitoring and removal at contract end.

## 7. Ongoing monitoring

For Critical suppliers, the annual review checks:

- current certificates or audit reports, including any exceptions they contain;
- incidents and service performance;
- changes to the service or to sub-processors;
- continuity and recovery assurance.

The GRC Analyst keeps the **supplier register**, holding each supplier's tier, assessments and review dates. The target is **100% of Critical suppliers assessed within the last 12 months** (Obj 9).

## 8. Cloud services

Cloud services are assessed for shared responsibilities, data location, access management, resilience, contract terms and assurance evidence (Annex A 5.23). Northstar's own configuration of cloud services falls under NSD-ISMS-029.

## 9. Software supply chain

Open-source components and development tools are covered by NSD-ISMS-029: dependency scanning, version pinning and pipeline controls (R-07, Annex A 5.21).

## 10. Supplier incidents

When a supplier reports an incident, Northstar assesses it under NSD-ISMS-027, covering the business, customer, privacy and regulatory impact. This includes whether Northstar, as a processor, must notify its customers.

## 11. Exit

When a supplier is replaced or the contract ends, the sponsor confirms that:

- all access has been removed (the same day);
- Northstar data has been returned or deleted, with written confirmation;
- the asset and supplier registers have been updated.

## 12. Exceptions and measures

Exceptions follow NSD-ISMS-008 §8.

| Measure | Target |
| --- | --- |
| Critical suppliers assessed in the last 12 months | 100% |
| Critical and High contracts containing the section 4 clauses | 100% |
| Guest accounts within their 90-day expiry | 100% |

## 13. Related controls and risks

Annex A 5.19–5.23 · Risks R-02, R-07, R-16 · Actions T-16.1, T-16.2

## 14. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-023) | First draft |
| 0.2 | Numbered NSD-ISMS-026. Owner changed from "Procurement Manager" (not a role at Northstar) to the Finance Manager, with the GRC Analyst running assessments; approver changed to the MD. "Proportionate" and "as appropriate" replaced with supplier tiers that set assessment depth and review frequency. Contract clauses made mandatory for Critical and High suppliers, including 24-hour incident reporting and DPAs. Added sub-processor rules, DORA flow-down, the supplier register and Obj 9 target, 90-day access expiry and the software supply chain link. |
| 0.3 | §3 tier criteria aligned with NSD-ISMS-056: Critical adds production access and BIA dependency; High adds Restricted information and user-level access, closing the gap found in the supplier register (NSD-ISMS-055, gap 5). Rule added that unknown facts mean the higher tier. |

---

*Portfolio note: Draft only. This is not an approved or implemented policy.*
