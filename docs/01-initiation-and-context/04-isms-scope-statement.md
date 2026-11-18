# Northstar Digital Solutions Ltd — ISMS Scope Statement

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-004 |
| Version | 1.0 — Draft for management approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clause 4.3) |
| Related documents | [NSD-ISMS-001 Project Charter](01-isms-project-charter.md) · [NSD-ISMS-002 Context Register](02-organisational-context-register.md) · [NSD-ISMS-003 Interested-Party Register](03-interested-party-requirements-register.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Classification | Internal — Simulated portfolio document |

---

## 1. Purpose

This document sets the boundaries and applicability of Northstar's ISMS (clause 4.3). It is the master scope record. The charter (NSD-ISMS-001 §4) summarises it, and the certificate wording will be taken from section 3.

Scope sections are cited elsewhere as **Scope §n**.

## 2. How the scope was determined

Clause 4.3 requires the scope to take account of three inputs. Each one is traced below.

| Clause 4.3 input | Source | Effect on scope |
| --- | --- | --- |
| (a) Internal and external issues | [NSD-ISMS-002](02-organisational-context-register.md) | EU presence (INT-08, EXT-03) brings EU personnel into scope. Secure development (INT-05) brings code repositories and CI/CD into scope. Finance data (INT-12) brings finance systems into scope |
| (b) Interested-party requirements | [NSD-ISMS-003](03-interested-party-requirements-register.md) | Customer and FS-customer requirements (IP-01, IP-03) mean the whole platform lifecycle must be in scope. GDPR (IP-08, IP-09) requires all personal data processing to be covered |
| (c) Interfaces and dependencies | Section 9 | Shared-responsibility boundaries with Microsoft (IP-10) and other suppliers (IP-11, IP-12, IP-17) |

## 3. Scope statement

> *The Information Security Management System of Northstar Digital Solutions Ltd covers the development, operation, support and sale of its [product name] SaaS platform provided to business customers in the UK and Europe. It includes the people, processes, information and technology at the UK head office [address], UK home-based working and EU-based personnel, together with the Microsoft Azure (UK and EU regions) and Microsoft 365 environments managed by Northstar. This is in accordance with the Statement of Applicability version [x], dated [date].*

Items in square brackets must be confirmed before approval (section 11).

## 4. Organisation covered

| Item | Detail |
| --- | --- |
| Legal entity | Northstar Digital Solutions Ltd (company number TBC) |
| Group structure | No subsidiaries or other legal entities (to be confirmed) |
| Size | About 85 personnel, including contractors |
| Services | B2B SaaS platform(s) for UK and European customers [product names TBC] |
| GDPR role | Processor for customer platform data; controller for employee, finance and marketing data |

## 5. Organisational boundaries

All functions are in scope. No function is excluded because it is not an IT function.

| Function | Status | Why it is in scope |
| --- | --- | --- |
| Executive / senior management | Included | Governance, accountability, risk acceptance |
| Information security / GRC | Included | ISMS governance and compliance |
| Software engineering and DevOps | Included | Builds and deploys the platform; holds source code and secrets |
| IT operations | Included | Operates Azure, Microsoft 365, endpoints and identity |
| Customer support | Included | Accesses customer data and accounts |
| Sales and marketing | Included | Handles customer contracts, prospect data and electronic marketing (PECR) |
| Human resources | Included | Employee data; joiner, mover and leaver process for UK and EU staff |
| Finance | Included | Financial data, billing and payroll systems (INT-12) |
| Procurement | Included | Supplier selection, contracts and oversight |
| Contractors and temporary staff | Included | Same access and obligations as employees for the work they do |

## 6. Physical and geographical boundaries

| Location | Status | Notes |
| --- | --- | --- |
| UK head office [address TBC] | Included | Only premises Northstar controls |
| UK home working | Included | Covered by remote-working and endpoint controls; home networks are an interface (section 9) |
| EU-based personnel [countries TBC] | Included | Home or co-working locations; local employment and data protection law applies (EXT-03, EXT-09) |
| Azure UK regions | Dependency | Northstar manages its subscriptions; Microsoft controls the datacentres |
| Azure EU region [TBC] | Dependency | Hosts EU customer data; same responsibility split as the UK regions |

Cloud hosting sites are dependencies, not premises Northstar controls. Northstar's configuration of them is fully in scope (section 7).

## 7. Technology boundaries

| Environment | Status | What is in scope for Northstar |
| --- | --- | --- |
| SaaS platform: production | Included | Application, data, configuration, monitoring |
| SaaS platform: staging, development and test | Included | Must not hold unprotected production data |
| Azure subscriptions (UK and EU regions) | Included | Identity, network rules, configuration, encryption keys, workloads |
| Microsoft 365 tenant | Included | Tenant configuration, user access, retention, data loss prevention |
| Identity and access management (Entra ID) | Included | Authentication, privileged access, access reviews |
| Code repositories and CI/CD pipelines [provider TBC] | Included | Access, branch protection, secrets management |
| Backup and recovery | Included | All backups of in-scope data and systems |
| Security monitoring and logging | Included | All tools used to monitor in-scope systems, in-house or outsourced |
| Company endpoints | Included | Laptops and desktops issued to staff and contractors |
| Mobile devices with access to company data | Included | Managed through mobile device or app management |
| Finance, billing and payroll systems | Included | Systems holding in-scope financial and employee data |

The scope does not use qualifiers such as "where used" or "where supporting", because an auditor would ask which systems they mean. Anything that holds or protects in-scope information is in scope.

## 8. Information covered

- Customer personal and business data, in UK and EU regions.
- Prospect and marketing contact data.
- Employee and contractor personal data, UK and EU.
- Financial and commercial information.
- Source code, build pipelines and software development records.
- System configuration and architecture information.
- Credentials, secrets, encryption keys and identity data.
- Contracts, business records and operational documentation.
- Security logs, incident records and audit evidence.

Individual assets and their owners are recorded in the asset register (project phase 2, Obj 2).

## 9. Interfaces and dependencies

| Interface | Northstar responsibility | External responsibility | Party |
| --- | --- | --- | --- |
| Microsoft Azure | Identity, configuration, network rules, data, keys, workload security | Physical datacentres, hypervisor, platform services | IP-10 |
| Microsoft 365 | Tenant configuration, user access, retention, DLP | Service infrastructure | IP-10 |
| Code repository / CI/CD provider [TBC] | Access, branch protection, secrets | Platform security | IP-11 |
| Security monitoring or backup providers [TBC] | Configuration, access granted, alert response | Their own service security | IP-11 |
| Outsourced HR, payroll or MSP [TBC] | Contract, data shared, access granted | Their own control environment | IP-12 |
| Business and integration partners [TBC] | API access, information sharing agreements | Their own systems | IP-17 |
| Customers | Platform security commitments in contracts | Customers' own user access and data entered | IP-01, IP-03 |
| Telecommunications providers | Resilient connectivity at the head office | Network service delivery | IP-11 |
| Home and co-working networks | Endpoint controls, VPN or Zero Trust access | The network itself | — |

These interfaces will be shown on architecture and data-flow diagrams, which are required evidence before approval (section 11).

## 10. Exclusions and boundary decisions

| Area | Decision | Justification |
| --- | --- | --- |
| Customers' own IT environments and users | Outside the boundary | Northstar does not operate them; responsibilities are set by the shared-responsibility terms in customer contracts |
| Suppliers' internal corporate environments | Outside the boundary | Addressed through supplier due diligence, contracts and assurance (Annex A 5.19–5.22) |
| Microsoft datacentre physical operations | Outside the boundary | Microsoft's responsibility; assurance taken from its ISO 27001 certificate and SOC 2 reports (Annex A 5.23) |
| [Any legacy product or other entity] | To be confirmed | Remove this row if nothing is excluded |

These are boundary decisions, not exemptions from ISO/IEC 27001 requirements. The risks from these areas are still assessed. No exclusion removes anything that affects Northstar's ability to protect customer information.

## 11. Items to confirm before approval

The scope cannot be approved until these are confirmed. The full evidence list is in the charter (NSD-ISMS-001 §9).

- [ ] Product names for the scope statement
- [ ] UK head office address
- [ ] EU countries where personnel are based
- [ ] Azure EU region used for EU customer data
- [ ] Code repository, CI/CD, monitoring and backup providers
- [ ] Whether any outsourced HR, payroll or MSP provider is used
- [ ] Whether business or integration partners exist (IP-17)
- [ ] Group structure and any excluded products or entities
- [ ] Architecture and data-flow diagrams showing the boundaries above

## 12. Review and change management

The scope is reviewed at least annually, alongside NSD-ISMS-002 and NSD-ISMS-003, and when:

- A merger, acquisition or new legal entity occurs.
- A new service or product is launched.
- A new office, country or business unit is added.
- The cloud architecture or hosting regions change materially.
- A critical supplier changes.
- Legal or contractual obligations change materially.

A scope change is proposed by the GRC Analyst, reviewed by the ISMS Steering Group and approved by the Managing Director. Approved changes update the Statement of Applicability and are reported to the certification body.

## 13. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Final approval | Pending | |
| IT Manager | Technology boundary validation | Pending | |
| Data Protection lead | Personal data and location validation | Pending | |
| Information Security / GRC Analyst | Document preparation | Prepared | |

---

*Important: This scope is a simulated baseline for professional development. It is not an approved or certified ISMS scope.*
