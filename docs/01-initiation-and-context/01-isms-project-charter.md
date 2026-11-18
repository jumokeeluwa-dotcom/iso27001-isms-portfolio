# Northstar Digital Solutions Ltd — ISMS Project Charter

## 0. Document control

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-001 |
| Version | 1.0 — Draft for senior management review |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 |
| Related documents | [NSD-ISMS-002 Organisational Context Register](02-organisational-context-register.md) · [NSD-ISMS-003 Interested-Party Requirements Register](03-interested-party-requirements-register.md) · [NSD-ISMS-004 ISMS Scope Statement](04-isms-scope-statement.md) |
| Owner | Information Security / GRC Analyst |
| Executive sponsor | Managing Director |
| Classification | Internal — Simulated portfolio document |

## 1. Purpose and business drivers

Northstar will establish, implement, maintain and continually improve an ISMS, and achieve ISO/IEC 27001:2022 certification for its SaaS platform within 12 months of charter approval.

The ISMS protects the confidentiality, integrity and availability of customer, employee and financial information. It also gives customers and regulators evidence that Northstar manages information security risk.

**Business drivers** (to be confirmed by management, see section 9):

- Customer and tender requirements for ISO 27001 certification or equivalent assurance.
- Growing volume of customer security questionnaires and due-diligence requests.
- UK GDPR and EU GDPR obligations as a processor of customer personal data.
- Contractual flow-down from regulated customers, such as financial services firms under DORA.
- Cyber insurance requirements.
- Reliance on Microsoft Azure and Microsoft 365 for all customer-facing services.

## 2. ISMS objectives

Each objective has a measure, a target and an owner, as clause 6.2 requires. Targets are proposals for management to confirm.

| # | Objective | Measure | Target | Owner |
| --- | --- | --- | --- | --- |
| Obj 1 | Approved governance in place | Policy and scope approved by MD | Month 2 | MD |
| Obj 2 | Complete asset inventory | In-scope assets with a named owner | 100% by month 3 | IT Manager |
| Obj 3 | Risk managed within appetite | High risks with an approved treatment plan | 100% by month 5 | Risk owners |
| Obj 4 | Controls determined by risk | SoA justified per control and approved | Month 5 | GRC Analyst |
| Obj 5 | Staff security awareness | Staff and contractors completing training | 95% annually | HR / GRC Analyst |
| Obj 6 | Privileged access controlled | Privileged accounts with MFA and quarterly review | 100% | IT Manager |
| Obj 7 | Vulnerabilities fixed on time | Critical vulnerabilities fixed within 14 days | 95% | IT Operations |
| Obj 8 | Service resilience proven | Business continuity and DR test within RTO | 1 test per year | IT Manager |
| Obj 9 | Suppliers assured | Critical suppliers with a current security assessment | 100% | Procurement / GRC Analyst |
| Obj 10 | Audit readiness | Major nonconformities at Stage 2 audit | Zero | GRC Analyst |

## 3. Organisation profile

Northstar is a fictional UK SaaS provider with about 85 personnel, a small IT and security function, and customers across the UK and Europe.

| Characteristic | Detail |
| --- | --- |
| Headquarters | One UK office (location to be confirmed) |
| Working model | Hybrid: office-based and home-based staff in the UK |
| EU presence | EU-based employees and/or contractors (countries to be confirmed) |
| Hosting | Microsoft Azure: UK regions for UK customers, an EU region for EU customers |
| Productivity | Microsoft 365 (Entra ID, Exchange Online, SharePoint, Teams) |
| Data processed | Customer data (including personal data), employee data, financial data |
| GDPR role | Processor for customer data in the platform; controller for employee, finance and marketing data |
| Security function | Small IT team plus one Information Security / GRC Analyst |

The small team affects the design. Some people will both operate and monitor controls, so the risk register records segregation of duties, and internal audit is outsourced (section 6).

## 4. ISMS scope

The scope is defined in the [ISMS Scope Statement (NSD-ISMS-004)](04-isms-scope-statement.md), which is the master record. In summary, it covers:

- **Services:** development, operation, support and sale of the SaaS platform [product names TBC].
- **Locations:** the UK head office, UK home working and EU-based personnel.
- **Functions:** all functions, including Sales and Marketing, HR, Finance and contractors.
- **Technology:** Northstar-managed Azure subscriptions (UK and EU regions), Microsoft 365, identity, code repositories and CI/CD, endpoints, mobile devices, and finance systems.
- **Boundaries:** Microsoft datacentres, suppliers' internal environments and customers' own environments are outside the boundary. Their risks are still managed through the interfaces in NSD-ISMS-004 §9.

## 5. Context and interested parties

### 5.1 Internal and external issues (clause 4.1)

Internal and external issues are recorded in the [Organisational Context Register (NSD-ISMS-002)](02-organisational-context-register.md). It holds 28 issues, including opportunities, with significance ratings and links to this charter.

The High-significance themes are:

- Resourcing and management commitment.
- Cloud and platform security, including secure development.
- Asset visibility and incident response.
- UK and EU legal and contractual obligations.
- Third-party risk and the market demand for certification.

**Climate change (Amendment 1:2024)** is judged relevant. Extreme weather can affect office access, staff availability and Azure regional availability. The register's section 5 gives the detailed assessment.

### 5.2 Interested parties (clause 4.2)

Interested parties, their requirements and the clause 4.2(c) decisions are recorded in the [Interested-Party Requirements Register (NSD-ISMS-003)](03-interested-party-requirements-register.md). It lists 17 parties (IP-01 to IP-17). Sixteen have requirements addressed fully or partly through the ISMS, and one (sustainability disclosures) is handled outside it.

The parties with the most influence on scope and controls are:

- **Customers and prospective customers (IP-01, IP-02):** processor duties, SLAs and certification evidence.
- **Regulated financial services customers (IP-03):** DORA terms passed down through contracts.
- **ICO and EU supervisory authorities (IP-08, IP-09):** UK GDPR as amended by the Data (Use and Access) Act 2025, and EU GDPR.
- **Microsoft (IP-10):** the shared-responsibility model for Azure and Microsoft 365.

NSD-ISMS-003 section 4 also gives an initial summary of legal and contractual obligations. A full Legal, Regulatory and Contractual Requirements Register (NSD-ISMS-005, Annex A 5.31) is a separate phase 1 deliverable.

## 6. Governance and responsibilities

The Managing Director is the accountable executive sponsor (clause 5.1). A monthly ISMS Steering Group oversees delivery.

| Role | Key responsibilities |
| --- | --- |
| Managing Director (sponsor) | Approves policy, scope, objectives, risk acceptance criteria and resources; chairs management review |
| ISMS Steering Group (MD, IT Manager, Head of Engineering, HR, Finance, GRC Analyst) | Monthly progress and risk review; approves residual risks within appetite |
| Information Security / GRC Analyst | Coordinates the ISMS; maintains risk, asset, compliance and improvement registers; drafts SoA; reports to the Steering Group |
| Risk owners (department heads) | Own named risks; approve treatment plans and accept residual risk |
| Asset owners | Classify their assets and approve access |
| IT Manager / IT Operations | Implement and operate technical controls; provide evidence; lead incident and vulnerability response |
| Data Protection lead (DPO if required) | GDPR compliance, ROPA, DPIAs, breach reporting to the ICO and EU authorities |
| EU representative / EU lead [TBC] | Local employment and data protection matters for EU personnel |
| Internal auditor (outsourced or peer-exchange) | Independent internal audits under clause 9.2 |
| All personnel | Follow policies, complete training, report incidents |

**Segregation of duties.** The GRC Analyst designs the ISMS and must not audit it. IT Operations runs controls, and their effectiveness is checked by the GRC Analyst or the internal auditor. Where one person must cover conflicting duties, the conflict and its compensating control (such as MD review) go in the risk register.

## 7. Deliverables, milestones and success criteria

The project runs in five phases over about 12 months from approval. Each phase ends with a Steering Group gate.

| Phase | Months | Deliverables | Gate |
| --- | --- | --- | --- |
| 1. Initiate and scope | 1–2 | Approved charter; context register (NSD-ISMS-002); interested-party register (NSD-ISMS-003); scope statement (NSD-ISMS-004); legal and contractual requirements register (NSD-ISMS-005); information security policy | MD signs scope and policy |
| 2. Assess risk | 2–5 | Asset register (NSD-ISMS-006) and related asset documents (007–011); risk methodology and acceptance criteria; risk register; risk treatment plan; Statement of Applicability | Risk owners approve treatment; MD approves SoA |
| 3. Implement | 4–9 | Topic policies and procedures; supplier assessments; awareness training; BC/DR plan and test; control evidence | Controls operating for at least 3 months |
| 4. Check | 7–10 | Internal audit programme (NSD-ISMS-030): audits in months 7–9; management review in month 10; corrective action log | All major internal findings closed |
| 5. Certify | 10–12 | Stage 1 and Stage 2 audits; continual improvement register | Certificate issued |

**Success criteria**

- Scope and policy approved by the MD by the end of month 2.
- Every in-scope high risk has an owner and an approved treatment plan.
- Objective targets in section 2 met or explained at management review.
- Independent internal audit completed with no open major findings.
- Certification achieved with zero major nonconformities.

## 8. Resources, assumptions and project risks

### 8.1 Resources requested

Management is asked to commit the following. Figures are placeholders until the budget is set.

| Resource | Request |
| --- | --- |
| GRC Analyst | Full-time on the project |
| IT Operations | About 20% of one engineer's time |
| Department heads | About 2 days per quarter each for risk workshops and reviews |
| Outsourced internal audit | About 12 days for cycle 1 (NSD-ISMS-030 §5) |
| Certification body | Stage 1 and Stage 2 audit fees |
| Tooling | GRC register or tool; awareness training platform |

### 8.2 Assumptions

- Northstar has one UK head office plus UK and EU home-based workers.
- EU customer data is hosted in an Azure EU region; UK data in Azure UK regions.
- Northstar acts as a processor for customer platform data.
- No subsidiaries or non-UK legal entities are in the group (to be confirmed).

### 8.3 Project risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Small team pulled onto operational work | Milestones slip | Ring-fenced time agreed by the MD |
| Single point of knowledge in GRC Analyst | Project stalls if absent | Documented registers; deputy named in Steering Group |
| Unknown EU employment and data transfer rules | Gaps in compliance register | Early legal review of EU personnel arrangements |
| Weak control evidence from cloud platforms | Audit findings | Agree evidence sources (Azure Policy, Defender, Entra logs) in phase 2 |
| Scope creep from customer requests | Delay | Changes to scope go through the Steering Group |

## 9. Evidence required before scope approval

The scope (NSD-ISMS-004) is approved only after management provides the evidence below.

- [ ] Organisation chart, headcount by location and a list of contractors, including EU-based personnel and their countries
- [ ] Product and service catalogue with named platforms
- [ ] Top customer contracts: security clauses, SLAs, certification demands, DORA terms
- [ ] Architecture and data-flow diagrams, including UK/EU data residency
- [ ] Azure subscription and region inventory; Microsoft 365 tenant overview
- [ ] Supplier and sub-processor list with criticality
- [ ] Records of processing activities (Art. 30) and any DPIAs
- [ ] Existing policies, previous audits, pen test reports and incident history
- [ ] Current business continuity and DR arrangements
- [ ] Business strategy and risk appetite statement
- [ ] Confirmed budget and resource commitment (section 8.1)
- [ ] Confirmation of any legal entities, subsidiaries or excluded products

## 10. Approval

| Role | Name | Decision | Date |
| --- | --- | --- | --- |
| Managing Director (sponsor) | Simulated role | Pending | |
| IT Manager | Simulated role | Pending | |
| Information Security / GRC Analyst | Portfolio owner | Prepared | |

---

*This is a simulated implementation document for professional development. It does not represent an actual approved company ISMS or certification.*
