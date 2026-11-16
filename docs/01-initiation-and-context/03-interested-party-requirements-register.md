# Northstar Digital Solutions Ltd — Interested-Party Requirements Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-003 |
| Version | 0.2 — Draft for review |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clause 4.2; Annex A 5.31) |
| Related documents | [NSD-ISMS-001 Project Charter](01-isms-project-charter.md) · [NSD-ISMS-002 Context Register](02-organisational-context-register.md) · [NSD-ISMS-004 Scope Statement](04-isms-scope-statement.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually, and on the triggers in section 6 |
| Classification | Internal — Simulated portfolio document |

---

## 1. Purpose

This register is the master record of interested parties for the ISMS. It meets the three parts of clause 4.2:

- **4.2(a)** identifies the interested parties relevant to the ISMS.
- **4.2(b)** records their relevant requirements, including legal, regulatory and contractual ones.
- **4.2(c)** decides which of those requirements the ISMS will address, and how.

Interested-party IDs (IP-xx) are used across all ISMS documents. Once issued, an ID is never renumbered.

## 2. Method

| Element | Approach |
| --- | --- |
| Inputs | Context register NSD-ISMS-002; customer contracts and data processing agreements; supplier contracts; insurance policy; legal review; interviews with the MD, IT Manager, HR and Sales (simulated) |
| Requirement source | Each requirement names where it comes from: law, contract, policy terms or stated expectation |
| 4.2(c) decision | **Yes:** addressed through ISMS processes and controls. **Partly:** some requirements addressed; the rest handled elsewhere. **No:** relevant to the business but handled outside the ISMS, with the owning process named |
| Traceability | Each party links to the context issues (INT/EXT) in NSD-ISMS-002 that make it relevant |

## 3. Interested-party register

| ID | Interested party | Relevant requirements | Source | Via ISMS? | How the ISMS addresses them | Context link | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |
| IP-01 | Customers (UK and EU) | Confidentiality, integrity and availability of their data; availability SLAs; breach notification within contract timescales; processor duties (Art. 28 GDPR); approval of sub-processors | Master services agreement, DPA, security schedule | Yes | Access control, encryption, incident management, BC/DR (Obj 8), contract obligation tracking, sub-processor list | EXT-03, EXT-06 | Sales lead / Data Protection lead |
| IP-02 | Prospective customers | Demonstrable security governance; accurate answers to security questionnaires; certification evidence | Tenders, questionnaires | Yes | Approved policy set; Statement of Applicability; certificate; questionnaire answer library reviewed by the GRC Analyst | EXT-06, EXT-13 | Sales lead / GRC Analyst |
| IP-03 | Regulated financial services customers | DORA ICT third-party contract terms (audit and access rights, incident notification, exit strategy, subcontracting limits); UK outsourcing expectations such as PRA SS2/21 | FS customer contracts (TBC) | Yes | Contract clause register; incident notification procedure; exit plan; supplier sub-contracting controls | EXT-07 | GRC Analyst |
| IP-04 | Employees (UK and EU) | Protection of their personal data; clear security responsibilities; safe remote working; lawful and proportionate monitoring | Employment contracts, UK GDPR / EU GDPR, local employment law | Yes | HR security procedures, employee privacy notice, awareness training, remote working policy | INT-07, INT-08, EXT-09 | HR Manager |
| IP-05 | Contractors and temporary workers | Defined access limits; confidentiality obligations; prompt onboarding and offboarding | Contractor agreements, NDAs | Yes | Contract terms, joiner/mover/leaver process, access reviews | INT-07 | HR Manager / IT Manager |
| IP-06 | Senior management / board | Visibility of risk; governance reporting; protection of reputation; evidence of compliance | Charter §6 | Yes | Risk register, Steering Group reporting, security KPIs, management review | INT-01, INT-03 | MD |
| IP-07 | Shareholders / owners | Protection of company value and reputation; due-diligence evidence | Shareholder agreement (TBC) | Partly | Governance reporting and risk management. Financial performance is outside the ISMS | INT-03 | MD |
| IP-08 | Information Commissioner's Office (ICO) | UK GDPR, DPA 2018 and PECR as amended by the Data (Use and Access) Act 2025; personal data breach reports within 72 hours; data protection fee | Legislation | Yes | Privacy governance, breach procedure, legal register, DSAR and complaints procedures | EXT-02 | Data Protection lead |
| IP-09 | EU data protection supervisory authorities | EU GDPR; rules on transfers between the UK and EU; lead authority or Art. 27 representative (to be determined) | Legislation | Yes | EU GDPR applicability assessment; transfer mechanism review; breach procedure covering EU authorities | EXT-03, EXT-04 | Data Protection lead |
| IP-10 | Microsoft (Azure and Microsoft 365) | Compliance with service terms and acceptable use; customer's side of the shared-responsibility model; secure administration of tenants and subscriptions | Microsoft customer agreement and DPA | Yes | Cloud security governance, configuration baselines, identity management, monitoring; review of Microsoft's own assurance reports | INT-04, EXT-05 | IT Manager |
| IP-11 | Other critical suppliers and sub-processors | Clear security requirements and responsibilities; confidentiality; agreed incident reporting | Supplier contracts | Yes | Supplier due diligence, security clauses, periodic reviews (Obj 9) | EXT-08 | GRC Analyst |
| IP-12 | Outsourced HR, payroll and MSP providers | Defined data sharing and access limits | Service agreements | Yes | Data sharing agreements, restricted access, supplier reviews | INT-12, EXT-08 | Finance Manager / HR Manager |
| IP-13 | Cyber insurance provider | Policy security conditions, such as MFA, backups and EDR; prompt incident notification | Insurance policy | Yes | Control monitoring against policy conditions; incident procedure includes insurer notification | EXT-10 | Finance Manager |
| IP-14 | Certification body | Objective evidence of conformity with ISO/IEC 27001:2022 | Certification contract | Yes | Documented information, internal audit, management review, audit support (Obj 10) | EXT-13 | GRC Analyst |
| IP-15 | Law enforcement and NCSC | Cooperation during incidents; reporting of cyber crime | Statutory and voluntary reporting routes | Partly | Incident procedure covers reporting and evidence preservation. Wider engagement is ad hoc | EXT-01 | IT Manager |
| IP-16 | Investors and customers (sustainability) | Climate-related disclosures | Investor and customer requests | No | Handled by the sustainability process. Climate resilience risks are covered by NSD-ISMS-002 §5 | EXT-12 | MD |
| IP-17 | Business and integration partners | Secure exchange of business and customer information; secure API integration | Partner agreements (TBC) | Yes | Information sharing agreements, API access controls, access restrictions | EXT-08 | Sales lead |

IP-17 is new in this register. Confirm that Northstar has business or integration partners. If it has none, mark the ID as retired rather than reusing it.

## 4. Legal, regulatory and contractual obligations (summary)

This is an initial applicability assessment, not a legal opinion. Detailed provisions, evidence and owners will move to the planned Legal, Regulatory and Contractual Requirements Register (NSD-ISMS-005, Annex A 5.31).

| Obligation | Applies? | Basis for Northstar | ISMS response | Owner |
| --- | --- | --- | --- | --- |
| UK GDPR and DPA 2018 | Yes | UK controller (staff, finance, marketing) and processor (customer platform data) | Privacy governance; technical and organisational measures; records of processing | Data Protection lead |
| Data (Use and Access) Act 2025 | Yes | Amends UK GDPR, DPA 2018 and PECR. The main data protection changes came into force on 5 February 2026 ([RPC](https://www.rpclegal.com/snapshots/data-protection/spring-2026/the-data-use-and-access-act-2025-commencement-update/)) | Update DSAR, cookie and complaints procedures; track the ICO's planned change to the Information Commission | Data Protection lead |
| EU GDPR | Yes | EU-based personnel, EU-hosted data and processing for EU customers | Determine lead supervisory authority or Art. 27 representative; Art. 28 terms with customers | Data Protection lead |
| UK–EU data transfers | Yes | Personal data moves between UK and EU staff, systems and customers | Confirm the transfer mechanism; monitor the EU's adequacy decision for the UK | Data Protection lead |
| PECR (as amended) | Yes, to be scoped | Website cookies and electronic marketing | Cookie and marketing compliance review | Marketing lead / Data Protection lead |
| DORA (EU) | Contractual | Applies to FS customers, not to Northstar directly; obligations flow down through contracts | Contract clause register; exit and incident terms | GRC Analyst |
| EU NIS2 Directive | To be assessed | May apply if Northstar's SaaS counts as a cloud computing service offered in the EU | Legal applicability assessment | Data Protection lead / GRC Analyst |
| Cyber Security and Resilience (NIS) Bill (UK) | Not yet law | Expands UK NIS rules, including to managed service providers. Lords Report Stage concluded on 26 October 2026 ([ISACA](https://www.isaca.org/resources/news-and-trends/isaca-now-blog/2026/the-uks-cyber-security-and-resilience-nis-bill-five-key-takeaways-from-lords-report-stage)) | Monitor; assess applicability once enacted | GRC Analyst |
| Computer Misuse Act 1990 | Yes | Supports prosecution of attacks; sets limits on security testing | Authorisation process for penetration tests | IT Manager |
| Employment and monitoring law (UK and EU countries) | Yes | Staff screening, monitoring and contract terms | HR security procedures reviewed per country | HR Manager |
| Customer contracts | Yes | Security schedules, SLAs, audit rights | Contract obligation tracking | Sales lead / GRC Analyst |
| Supplier agreements | Yes | Security, confidentiality and availability terms | Supplier management | GRC Analyst |

## 5. How the ISMS addresses the requirements

| ISMS process | Main Annex A controls | Interested parties served |
| --- | --- | --- |
| Information security policies | 5.1 | All |
| Information security risk management | Clauses 6.1, 8.2, 8.3 | IP-01, IP-06, IP-14 |
| Identity and access management | 5.15–5.18, 8.2, 8.5 | IP-01, IP-04, IP-05, IP-10, IP-13 |
| Asset management | 5.9–5.13 | IP-01, IP-06, IP-14 |
| Cloud and supplier security management | 5.19–5.23 | IP-03, IP-10, IP-11, IP-12, IP-17 |
| Secure development | 8.25–8.29 | IP-01, IP-02, IP-03 |
| Incident management | 5.24–5.28, 6.8 | IP-01, IP-03, IP-08, IP-09, IP-13, IP-15 |
| Business continuity and ICT readiness | 5.29, 5.30, 8.13, 8.14 | IP-01, IP-03 |
| Privacy and legal compliance | 5.31–5.34 | IP-01, IP-04, IP-08, IP-09 |
| Security awareness and training | 6.3 | IP-04, IP-05, IP-13 |
| Internal audit and management review | 5.35; clauses 9.2, 9.3 | IP-06, IP-14 |

Final control selection follows risk treatment and is recorded in the Statement of Applicability (clause 6.1.3).

## 6. Monitoring and review

The GRC Analyst maintains the register and reviews it with each party's owner. Reviews happen annually, before management review, and when:

- A new customer, supplier or partner relationship is established, especially in financial services.
- New legal or regulatory obligations arise, or a monitored bill becomes law.
- New services or products are introduced.
- Customer contract requirements change.
- Northstar starts operating in a new country.
- A significant security incident occurs.

These triggers match the context register (NSD-ISMS-002 §7), and both registers are reviewed together.

## 7. Evidence to retain

| Evidence | Interested parties | Owner |
| --- | --- | --- |
| Customer contracts, security schedules and DPAs | IP-01, IP-03 | Sales lead |
| Completed security questionnaires | IP-02 | GRC Analyst |
| Supplier and partner contracts, sub-processor list | IP-10, IP-11, IP-12, IP-17 | GRC Analyst |
| Microsoft assurance reports (ISO 27001 certificate, SOC 2) | IP-10 | IT Manager |
| Privacy notices, records of processing, DPIAs | IP-04, IP-08, IP-09 | Data Protection lead |
| Breach log and regulator notifications | IP-08, IP-09 | Data Protection lead |
| Insurance policy security conditions | IP-13 | Finance Manager |
| Steering Group and management review minutes | IP-06, IP-07 | GRC Analyst |
| Internal audit reports and certification audit records | IP-14 | GRC Analyst |

## 8. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves business commitments and 4.2(c) decisions | Pending | |
| Data Protection lead | Validates legal and regulatory obligations | Pending | |
| IT Manager | Validates technology requirements | Pending | |
| Information Security / GRC Analyst | Maintains register | Prepared | |

## 9. Change log

| Version | Change |
| --- | --- |
| 1.0 (portfolio draft) | First draft: 14 parties and 6 legal or contractual obligations |
| 0.1 | Renumbered as a draft pending approval. IDs aligned with charter v0.2 (IP-01 to IP-16), and IP-17 Business partners added. Microsoft Azure and Microsoft 365 merged into one party, IP-10. EU customers separated from EU regulators. Added regulated FS customers, outsourced HR/payroll/MSP, law enforcement/NCSC and sustainability. Added source, 4.2(c) decision, context link and owner columns. Removed "if certification is pursued", since certification is the charter goal. Changed EU GDPR from "potentially applicable" to applicable. Added DUAA 2025, UK–EU transfers, DORA, NIS2, the Cyber Security and Resilience Bill, the Computer Misuse Act and employment law. Mapped ISMS processes to Annex A controls. Gave each piece of evidence an owner. |
| 0.2 | Linked to the scope statement NSD-ISMS-004. The planned legal register is renumbered NSD-ISMS-005. |

---

*Portfolio note: Stakeholders and requirements are fictional assumptions. A real implementation would validate them against documentary evidence and legal advice. Legislative status checked on 15 November 2026.*
