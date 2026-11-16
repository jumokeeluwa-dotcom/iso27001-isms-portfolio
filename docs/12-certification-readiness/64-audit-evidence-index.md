# Northstar Digital Solutions Ltd — ISMS Audit Evidence Index

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-064 |
| Version | 0.3 — Simulated index |
| Standard | ISO/IEC 27001:2022 incl. Amendment 1:2024 |
| Status | **Simulated. The index points to portfolio records, which are themselves simulated. No real evidence has been collected, and no file is named here as if it existed** |
| Evidence as at | 30 September 2027 |
| Owner | Information Security / GRC Analyst (maintains the index). Each item is owned by the person who produces the record |
| Used by | Mock audits (NSD-ISMS-066, 067); readiness report (065); remediation tracker (068) |
| Classification | Confidential |

---

## 1. Purpose

The index lets an auditor trace each requirement to the evidence that shows it is met: **the document that says what should happen, the records that show it happening, and the tests that show it works.** For each item it gives the owner, the system the record comes from, the period it covers, and whether it exists.

## 2. Evidence types and status

| Evidence type | Shows | Example |
| --- | --- | --- |
| **D — Documented** | What should happen | Policy, procedure, register |
| **O — Operational** | That it happens | Access review record, leaver disable time, meeting minutes |
| **E — Effectiveness** | That it achieves its purpose | Restore test within RTO, audit re-test, KPI against target |

A requirement normally needs **D and O**; key controls need **E** as well. A document alone shows design, not operation.

| Status | Meaning |
| --- | --- |
| 🟩 Available | The record exists in the portfolio and covers the period |
| 🟨 Draft | The document exists but is **not approved** |
| 🟧 Partial or conflict | Some records exist; part is missing, or records contradict each other |
| 🟥 Missing | Required, but no record exists. **Not counted as evidence** |
| ⬜ Not yet due | The activity is scheduled after 30 Sep 2027 |

The draft marked internal audit, management review, KPIs and corrective actions as "templates only". The portfolio holds records of three of them in operation (AUD-03, the August dashboard, CA-01 to CA-03), so they are shown as **Available.** Understating evidence is as misleading as overstating it. **Management review is the exception:** its minutes and summary are blank templates (038, 040), so EVD-021 is Missing.

## 3. Evidence index — clauses

| ID | Requirement | Evidence | Type | Source / system of record | Period | Owner | Status | Gap → NSD-ISMS-068 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| EVD-001 | 4.1 Context (incl. climate) | Context register; planned review input (037) | D | 002 v0.3 | To Sep 2027 | GRC Analyst | 🟨 Draft | Approval |
| EVD-002 | 4.2 Interested parties | Requirements register | D | 003 | — | GRC Analyst | 🟧 Partial | Legal register missing (EVD-036) |
| EVD-003 | 4.3 Scope | Scope statement and MD approval | D | 004 v0.1 | — | MD | 🟨 Draft | **Approval: Stage 1 blocker** |
| EVD-004 | 5.1 Leadership | MD decisions on resources and objectives | O | MR-2027-01 minutes (038) | — | MD | 🟥 Missing | No review recorded; D-01 to D-08 are proposals (037, 039) |
| EVD-005 | 5.2 Policy; A 5.1 | Approved policy; staff acknowledgement | D, O | 022; acknowledgement records (KPI-20) | Q2 2027 | GRC Analyst | 🟧 **Conflict** | 93% acknowledged a policy with no approval record (061 gap 2) |
| EVD-006 | 5.3 Roles | Role assignments; owner acceptance | D, O | Charter §6; 007; 017 | — | MD | 🟧 Partial | Owner acceptance not recorded |
| EVD-007 | 6.1.2 Risk criteria | Approved acceptance criteria | D | 016 Part A | — | MD | 🟨 Draft | **Approval: scores provisional until then** |
| EVD-008 | 6.1.2, 8.2 Risk assessment | Risk register | O | 014 v0.3 | Dec 2026 | GRC Analyst | 🟧 Partial | R-21 not added; no reassessment since |
| EVD-009 | 6.1.3, 8.3 Treatment | Approved plan; progress | D, O, E | 015 (stated approved 1 Dec 2026); KPI-17 | To Aug 2027 | Risk owners | 🟧 Partial | Approval record not in portfolio; KPI-17 70% (Red) |
| EVD-010 | 6.1.3 SoA | Approved SoA; validation | D | 019 v0.3; 063 | — | GRC Analyst | 🟨 Draft | 45 controls unassessed; 5 Fail checks (063) |
| EVD-011 | 6.1.3(f) Risk acceptance | Acceptance and tolerance decisions | O | 016 §8; AR-01, AR-02 | — | Risk owners; MD | 🟥 Missing | No acceptance approved |
| EVD-012 | 6.2 Objectives | Objectives, measures, results | D, O, E | Charter Obj 1–9; 042; 044 | To Aug 2027 | GRC Analyst | 🟩 Available | Obj 1 (approved governance) missed |
| EVD-013 | 6.3 Planning changes | Change records for ISMS changes | O | 034 CA-03 "ISMS changes"; 045 §7 | 2027 | GRC Analyst | 🟧 Partial | No separate ISMS change log |
| EVD-014 | 7.1 Resources | Resource decisions | O | KPI-17; proposed decision D-04 (037) | To Aug 2027 | MD | 🟧 Partial | Need identified; no decision recorded |
| EVD-015 | 7.2 Competence | Competence requirements and records for ISMS roles | D, O | — | — | HR Manager | 🟥 Missing | **No competence records** |
| EVD-016 | 7.3 Awareness; A 6.3 | Training completion; phishing results | O, E | Training system (KPI-10); phishing tool (KPI-11) | Q1–Q2 2027 | HR Manager | 🟩 Available | 91.8% vs 95% target |
| EVD-017 | 7.4 Communication | What, when, with whom, how | D | — (027, 050 cover incidents and continuity only) | — | GRC Analyst | 🟥 Missing | Communication statement |
| EVD-018 | 7.5 Documented information | Version control, approval, access | D, O | Change logs in each document | — | GRC Analyst | 🟧 Partial | Approvals missing throughout |
| EVD-019 | 9.1 Monitoring | KPI register, plan, validated dashboard | D, O, E | 041–044 | To Aug 2027 | GRC Analyst | 🟩 Available | Procedure not approved |
| EVD-020 | 9.2 Internal audit | Programme; plans; checklists; reports | D, O | 030; AUD-03 (031–035) | Jun 2027 | MD (sponsor) | 🟧 Partial | **AUD-01, 02, 04 to 09: no records** |
| EVD-021 | 9.3 Management review | Inputs, minutes, decisions, actions | O | 037 (agenda); 038, 040 blank; 039 hypothetical | — | MD | 🟥 Missing | **No management review recorded** |
| EVD-022 | 10.1 Improvement | Improvement register | O | 047 | 2027 | GRC Analyst | 🟩 Available | — |
| EVD-023 | 10.2 Corrective action | Root causes, actions, effectiveness results | O, E | 034; 048 | 2027 | Action owners | 🟧 Partial | CA-02 not effective; RCA-01 open |

## 4. Evidence index — Annex A (key controls)

| ID | Control | Evidence | Type | Source / system of record | Period | Owner | Status | Gap → NSD-ISMS-068 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| EVD-024 | 5.9 Assets | Asset register; reviews | D, O | 006; 011 | — | GRC Analyst | 🟧 Partial | CRM missing |
| EVD-025 | 5.15, 5.18 Access reviews | Review records | O, E | Entra ID access reviews (KPI-02); AUD03-F02 | Q1–Q2 2027 | IT Manager | 🟩 Available | Show a gap: 80% recorded, Red twice |
| EVD-026 | 5.16, 6.5 Leavers | HR leaving dates against account disable times | O, E | HR system and Entra ID (KPI-01); WP-AUD03-05 | To Aug 2027 | HR Manager | 🟩 Available | RCA-01 open |
| EVD-027 | 8.2 Privileged access | PIM records; standing admin count | O, E | Entra PIM (KPI-04); AUD03-F03 | To Aug 2027 | IT Manager | 🟩 Available | Break-glass test records not linked |
| EVD-028 | 8.5 Authentication | MFA coverage report | O | Entra ID (KPI-03) | To Aug 2027 | IT Manager | 🟩 Available | 96%: 4 accounts without MFA |
| EVD-029 | 8.32, 5.3 Change and segregation | Deployment approvals | O, E | CI/CD records (KPI-07) | To Aug 2027 | Head of Engineering | 🟩 Available | Testing and emergency-change review not evidenced |
| EVD-030 | 8.8 Vulnerabilities | Scan and fix records; penetration test | O, E | Scanner (KPI-05); pen test report (AST-016) | To Aug 2027 | Head of Engineering | 🟧 Partial | **Annual penetration test report not in portfolio** |
| EVD-031 | 5.23, 8.9 Cloud configuration | Compliance score | O | Cloud security posture tool (KPI-06) | To Aug 2027 | Head of Engineering | 🟩 Available | Microsoft assurance not mapped |
| EVD-032 | 8.12 DLP | DLP events | O | DLP tool (KPI-16) | To Aug 2027 | IT Manager | 🟩 Available | CA-03 effectiveness pending |
| EVD-033 | 8.13 Backup | Backup job results | O | Backup service (KPI-08) | To Aug 2027 | IT Manager | 🟩 Available | Jobs do not prove recovery |
| EVD-034 | 8.13, 5.30 Restore tests | Restore test reports with measured times | E | 054; KPI-09 | Q2 2027 | IT Manager | 🟥 Missing | T-14.3 report missing; 1 of 4 Q2 tests no record; BRT-01 ⬜ due 12 Oct 2027 |
| EVD-035 | 5.29, 5.30, 8.14 Continuity | BIA, plans; failover test; exercise | D, E | 049–052; T-09.2; 053 | — | Head of Engineering | 🟥 Missing (tests) | Plans drafted; **failover test and T-18.1 exercise not done**; EX-01 ⬜ 8 Dec 2027 |
| EVD-036 | 5.31 Legal requirements | Legal register | D | NSD-ISMS-005 | — | Data Protection lead | 🟥 Missing | Proposed action MRA-2027-02 |
| EVD-037 | 5.24–5.28, 6.8 Incidents | Incident and breach records | O | Incident log; INC-2027-014; CA-03 | 2027 | GRC Analyst | 🟩 Available | One incident; no Severity 1 events (KPI-12, not evidence of readiness) |
| EVD-038 | 5.19–5.22 Suppliers | Supplier register; assessments; contracts | D, O | 055–060 | — | GRC Analyst | 🟥 Missing (assessments) | **No assessment records;** Q2 KPI-14 untraceable |

**Summary (38 items):** 🟩 Available 13 · 🟨 Draft 4 · 🟧 Partial or conflict 12 · 🟥 Missing 9. Clause evidence for **9.1 and 10.1 is the strongest;** management review, approvals, competence, legal requirements, continuity tests and supplier assessments are the weakest.

## 5. Evidence quality checks

The draft's checks are kept, with additions marked †.

| Check | What the reviewer confirms |
| --- | --- |
| Identity | Exact title, unique reference, version and approval status |
| Period | Date created and the period it covers. **Within the last 12 months** for operational and effectiveness evidence † |
| Source | Owner or system of record. **Populations come from the system of record,** not from a list prepared for the audit (for example, leavers from the HR system, accounts from Entra ID) † |
| Type | Supplier assertion, internal record, independent assurance, or a test observed directly |
| Completeness † | The population reconciles: the number of leavers in HR equals the number checked in Entra ID |
| Authenticity † | System exports with timestamps are preferred to screenshots; who generated the export and when |
| Limitations | Exceptions, gaps or missing records, stated rather than left out |
| Review | Who inspected it and when |

## 6. Naming and storage

- **Index IDs** (EVD-nnn) are permanent. **File names** use `NSD-EVD-[nnn]-[short description]-[record date]`, where the date is the **date of the record,** not the date it was filed.
- One evidence folder per EVD ID, in an access-controlled SharePoint location, classified at the level of its most sensitive content: **Restricted** where it holds personal data, such as leaver records.
- Personal data is minimised or redacted where the audit does not need it; the original is kept unchanged.
- **Auditors are suppliers.** The certification body and the external internal auditor (SUP-13) get named, read-only guest access to the evidence folders only, under NSD-ISMS-023 §10, removed when the audit ends.
- Evidence is kept for at least **3 years,** one certification cycle.

As the draft says: **an example file name is not evidence,** and no record may be created after the fact to fill a gap. A missing record stays missing and is tracked in NSD-ISMS-068.

## 7. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-060) | 25 evidence items; quality checks; naming convention; handling |
| 0.3 | **Correction:** management review MR-2027-01 is planned but unrecorded (038 and 040 blank; 039 hypothetical). EVD-004 and EVD-021 changed to Missing, EVD-014 to Partial; totals now 13 available, 4 draft, 12 partial, 9 missing. |
| 0.2 | Numbered NSD-ISMS-064. Owners changed to charter roles ("Senior Management", "Security Lead", "Procurement", "Internal Audit Lead" and "Operations Director" are not charter roles; "HR and IT" given one owner). **Statuses corrected from portfolio records:** internal audit, management review, KPIs and corrective actions marked Available, not "templates only". Evidence typed as documented, operational or effectiveness. Columns added for the system of record and period. Extended to 38 items across all clauses and key Annex A controls, including risk acceptance, communication, the penetration test and the legal register. Statuses Draft, Partial, Missing and Not yet due kept separate, with the KPI-20 conflict shown. Quality checks add the 12-month window, populations from systems of record, reconciliation and authenticity. Storage adds classification, redaction, auditor guest access and retention. |

---

*Portfolio disclaimer: Simulated evidence index. No real evidence has been collected, and no fictional record is presented as actual evidence.*
