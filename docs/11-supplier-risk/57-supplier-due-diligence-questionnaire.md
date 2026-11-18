# Northstar Digital Solutions Ltd — Supplier Security Due Diligence Questionnaire

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-057 |
| Version | 1.0 — Template |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 5.19–5.23 |
| Status | **Simulated template. No supplier has completed it** |
| Used by | [NSD-ISMS-056 Methodology](56-supplier-risk-assessment-methodology.md) §3–4 · results recorded in NSD-ISMS-058 |
| Owner | Information Security / GRC Analyst |
| Classification | Internal (blank template); Confidential once completed |

---

## 1. How the questionnaire is used

| Rule | Why |
| --- | --- |
| **Part A is completed by Northstar** before sending: service, data, access, tier | Northstar must know the service, data, access and tier before it asks the supplier anything |
| **Sections depend on the tier** (NSD-ISMS-055): Critical suppliers answer all of Part B; High suppliers answer the sections marked **H**; Standard suppliers receive no questionnaire | Proportionate effort (NSD-ISMS-026 §3) |
| **Every "Yes" needs an evidence reference,** or it is recorded as an unsupported claim and gets **no credit** (NSD-ISMS-056 §4) | A yes/no questionnaire mostly collects yeses |
| **Large cloud providers** (SUP-01, SUP-02) are not sent the questionnaire. Northstar maps their published certificates, SOC 2 reports and contract terms to the same questions and records the mapping | Such providers do not complete customer questionnaires; their independent assurance is stronger evidence anyway |
| **Knock-out questions (★)**: an unacceptable answer stops onboarding until a decision is made under NSD-ISMS-056 §8 | Some answers cannot be fixed by scoring |

**Answer options:** Yes, with evidence reference · Partly, with explanation · No · Not applicable, with reason.

## 2. Part A — Completed by Northstar

| # | Item |
| --- | --- |
| A1 | Supplier ID (NSD-ISMS-055), legal entity and security contact |
| A2 | Service; Northstar business owner |
| A3 | Northstar assets involved; highest classification of information |
| A4 | Access: none, user, privileged, or a route to production |
| A5 | Customer personal data processed? (sub-processor) · Northstar personal data processed? |
| A6 | BIA activities supported, and the RTO and RPO Northstar needs (NSD-ISMS-049, 052) |
| A7 | Supports services for financial services customers? (DORA terms) |
| A8 | Tier and reason; sections required |

## 3. Part B — Completed by the supplier

### B1 Assurance and governance (H)

| # | Question | Evidence expected |
| --- | --- | --- |
| B1.1 | Do you hold ISO/IEC 27001 certification? Give the certification body, certificate number, expiry date and **scope** | Certificate; Statement of Applicability |
| B1.2 | Does the scope cover the service and locations Northstar uses? | Scope statement |
| B1.3 | Do you have a SOC 2 report? Type I or **Type II**? Period covered? Any exceptions? | Full report under NDA; bridge letter for any gap since the period ended |
| B1.4 | What does your assurance report require **customers** to do (complementary controls)? | Report section |
| B1.5 | Who is accountable for information security? When was your last independent security assessment, and were its findings closed? | Organisation chart; summary of findings and status |

### B2 Access control (H)

| # | Question | Evidence expected |
| --- | --- | --- |
| B2.1 ★ | Is MFA required for **all** access to systems holding Northstar data, and for **all** administrator access? | Policy; configuration summary |
| B2.2 | Do administrators use separate accounts, with privileged access granted only when needed? | Privileged access procedure |
| B2.3 | How often are access rights to Northstar data reviewed? Date of the last review? | Review record |
| B2.4 | When staff leave, by when is their access removed? | Leaver procedure; recent example |
| B2.5 | **If you access Northstar systems:** do you use named accounts only, never shared ones? | List of named users |

### B3 Data protection (H)

| # | Question | Evidence expected |
| --- | --- | --- |
| B3.1 | What Northstar data will you hold, and for what purposes? | Data flow description |
| B3.2 ★ | Where is it stored, processed **and accessed for support?** Any transfer outside the UK or EU, and the transfer mechanism? | DPA; location list |
| B3.3 | Is data encrypted in transit and at rest? Who manages the keys? | Technical description |
| B3.4 ★ | Is Northstar data used for **any purpose other than providing the service,** including analytics or training AI models? | DPA clause |
| B3.5 | How, and how quickly, is data returned or deleted at the end of the contract? Do you confirm it in writing? | Deletion procedure |
| B3.6 | How do you help Northstar meet data subject requests and its own breach notification duties? | DPA; process |

### B4 Incident management (H)

| # | Question | Evidence expected |
| --- | --- | --- |
| B4.1 ★ | Will you notify Northstar of a security incident affecting its data or service **within 24 hours of discovery** (NSD-ISMS-026 §4)? | Contract clause |
| B4.2 | Who is the 24/7 security contact? | Contact details |
| B4.3 | How do you preserve evidence, and will you support Northstar's investigation? | Incident procedure |
| B4.4 | Have you had a security incident in the last 3 years that affected customer data? What changed afterwards? | Summary |

### B5 Continuity and recovery (Critical)

| # | Question | Evidence expected |
| --- | --- | --- |
| B5.1 | What RTO and RPO do you commit to for the service? *(Compared with Part A, A6)* | SLA |
| B5.2 | When were recovery and backup restoration last **tested,** and were the objectives met? | Test summary with dates and results |
| B5.3 | Are backups protected from deletion or ransomware? | Description |
| B5.4 | How do you tell customers about outages, and how quickly? | Status page; SLA |

### B6 Vulnerability, change and secure development (Critical)

| # | Question | Evidence expected |
| --- | --- | --- |
| B6.1 | How quickly are critical vulnerabilities fixed on internet-facing systems? | Standard; recent metrics |
| B6.2 | Is your service penetration tested independently? When last, and were the findings fixed? | Summary letter |
| B6.3 | **For software and platform suppliers:** how are code changes reviewed and dependencies checked? | Secure development procedure |
| B6.4 | How much notice do you give of changes that affect security, data location or features? | Contract or notice policy |

### B7 People (H)

| # | Question | Evidence expected |
| --- | --- | --- |
| B7.1 | Are staff with access to Northstar data screened before starting, as the law allows in each country? | Screening policy |
| B7.2 | Do they receive security training every year? | Completion rate |
| B7.3 | Are they bound by confidentiality? | Contract extract |

### B8 Physical security (Critical, where the supplier runs its own facilities)

| # | Question | Evidence expected |
| --- | --- | --- |
| B8.1 | Do you run your own data centres, or use a cloud provider? If a cloud provider, which one? | — If cloud-hosted, physical security is covered by **that** provider's assurance; record which |
| B8.2 | If your own: are the facilities covered by your certificate or SOC 2 report? | Scope |

### B9 Subcontractors and sub-processors (H)

| # | Question | Evidence expected |
| --- | --- | --- |
| B9.1 ★ | List the sub-processors that will process Northstar data, with locations | Sub-processor list |
| B9.2 | How do you assess their security, and do you pass on equivalent obligations? | Supplier management procedure |
| B9.3 ★ | Will you give advance notice of new sub-processors, long enough for Northstar to notify its own customers (NSD-ISMS-026 §5)? | Contract clause; notice period |

### B10 Contract terms (H)

Checked by Northstar against the contract, not answered by the supplier: the nine clauses in NSD-ISMS-026 §4, and **DORA terms** where A7 is yes (audit and access rights, incident notification, exit support, limits on subcontracting).

## 4. Declaration

> I confirm that I am authorised to answer for [supplier], that the answers and evidence are accurate and complete to the best of my knowledge, and that [supplier] will tell Northstar of any material change within the period in our agreement.

| Name | Position | Date |
| --- | --- | --- |
| | | |

## 5. Northstar review

| Step | Who |
| --- | --- |
| Check evidence for every "Yes"; apply the credit rule (056 §4); compare B5.1 with A6 | GRC Analyst |
| Any ★ answer unacceptable: stop and escalate under 056 §8 | GRC Analyst |
| Technical review of B2, B5 and B6 | IT Manager (corporate services) or Head of Engineering (platform and development suppliers) |
| Confirm the service facts in Part A | Business owner |
| Record the results | NSD-ISMS-058 |

---

*Portfolio disclaimer: Simulated questionnaire template. No supplier has completed or verified these responses.*
