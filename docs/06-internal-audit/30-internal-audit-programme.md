# Northstar Digital Solutions Ltd — Internal Audit Programme

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-030 |
| Version | 1.0 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clause 9.2; Annex A 5.35); guidance from ISO 19011 |
| Related documents | [NSD-ISMS-001 Charter](../01-initiation-and-context/01-isms-project-charter.md) · [NSD-ISMS-014 Risk Register](../03-risk-management/14-risk-register.md) · [NSD-ISMS-019 SoA](../04-controls-and-soa/19-statement-of-applicability.md) · [NSD-ISMS-021 Evidence Checklist](../04-controls-and-soa/21-control-evidence-checklist.md) · Policies NSD-ISMS-022 to 029 |
| Programme manager | Information Security / GRC Analyst (scheduling and logistics only, **not an auditor**) |
| Approver | Managing Director |
| Programme period | Cycle 1: June to August 2027 (charter months 7–9), before management review and Stage 1 |
| Classification | Internal. Audit reports are Confidential |

---

## 1. Purpose

This programme sets out what will be audited, when, by whom, against which criteria and with what resources, so that Northstar meets clause 9.2. It gives management an independent view of whether the ISMS:

- **conforms** to ISO/IEC 27001:2022 and to Northstar's own requirements;
- is **effectively implemented and maintained**.

## 2. Objectives

1. Assess conformity with clauses 4 to 10 of ISO/IEC 27001:2022.
2. Assess compliance with Northstar's policies (NSD-ISMS-022 to 029).
3. Test whether applicable controls in the SoA are operating effectively, by re-performing the tests in NSD-ISMS-021.
4. Identify nonconformities, weaknesses and opportunities for improvement.
5. Verify that corrective actions are implemented and effective.
6. Provide independent audit results as an input to management review (clause 9.3).

## 3. Independence

**The GRC Analyst designed and maintains most of the ISMS, so cannot audit any part of it.** Their role here is limited to scheduling, logistics and record keeping.

| Arrangement | Detail |
| --- | --- |
| Auditor | An **external auditor** holding an ISO/IEC 27001 Lead Auditor qualification, as planned in charter §6 |
| Independence check | Before each audit, the auditor confirms in writing that they have had no involvement in designing or operating the area being audited |
| Reporting line | The auditor reports directly to the MD and the Steering Group, not through the GRC Analyst |
| Peer auditors (later cycles) | Northstar staff trained in auditing may audit areas outside their own responsibility. Example: the Finance Manager may audit incident management, but not supplier security |

## 4. Risk-based priorities

Audit priority follows the risk register and the SoA:

| Priority | Rule |
| --- | --- |
| **Critical** | The audit area treats a **Very High** current risk: R-06, R-12, R-14 or R-19 |
| **High** | The area treats High risks, or covers clauses essential for certification |
| **Medium** | Other areas |

Within each audit, the auditor focuses on:

- controls that are **Partially implemented** or **To be assessed** in the SoA;
- the controls Northstar relies on most (8.5, 8.2, 8.15, 8.16 and 5.3; NSD-ISMS-020 §2);
- areas with past findings or recent incidents.

## 5. Cycle 1 schedule

Cycle 1 runs after treatment actions are complete (NSD-ISMS-015: by 1 March 2027) and after controls have operated for about 3 months (charter phase 3 gate). It finishes before management review and the Stage 1 audit in September 2027.

| Ref | Audit area | Scope: clauses and Annex A | Main risks | Priority | Month | Auditor days | Lead auditees |
| --- | --- | --- | --- | --- | --- | --- | --- |
| AUD-01 | ISMS governance, context, scope, leadership and support | Clauses 4, 5, 6.2, 7; A 5.1–5.4, 5.31, 5.37 | — | High | Jun 2027 | 1 | MD, GRC Analyst |
| AUD-02 | Risk assessment, treatment and SoA | Clauses 6.1, 8.1–8.3 | All | High | Jun 2027 | 1 | GRC Analyst, risk owners |
| AUD-03 | Identity and access management | A 5.15–5.18, 6.5, 8.2, 8.3, 8.5 | **R-12**, R-01, R-11, R-13 | **Critical** | Jun 2027 | 1.5 | IT Manager, HR Manager |
| AUD-04 | Platform security: secure development, change, vulnerability, configuration, logging and monitoring | A 8.4, 8.8, 8.9, 8.15, 8.16, 8.24–8.32 | **R-06**, R-05, R-07, R-08, R-17 | **Critical** | Jul 2027 | 1.5 | Head of Engineering |
| AUD-05 | Asset management, classification and data protection (incl. DLP and AI use) | A 5.9–5.14, 5.33, 5.34, 8.10–8.12 | **R-19**, R-02, R-03 | **Critical** | Jul 2027 | 1 | GRC Analyst, Data Protection lead, IT Manager |
| AUD-06 | Supplier and cloud security | A 5.19–5.23 | R-16, R-02 | High | Jul 2027 | 1 | Finance Manager, Head of Engineering |
| AUD-07 | Incident management | A 5.24–5.28, 6.8 | R-18 | High | Jul 2027 | 1 | GRC Analyst, Data Protection lead |
| AUD-08 | Backup, recovery and business continuity, **including observing a restore or failover test** | A 5.29, 5.30, 8.13, 8.14 | **R-14**, R-09 | **Critical** | Aug 2027 | 1 | IT Manager, Head of Engineering, MD |
| AUD-09 | People, physical security and acceptable use | A 6.1–6.4, 6.6, 6.7; 7.1–7.14; 5.10; 8.1, 8.7 | R-10, R-20, R-04 | High | Aug 2027 | 0.5 | HR Manager, IT Manager |
| AUD-10 | Performance evaluation and improvement, plus follow-up of AUD-01 to 09 findings | Clauses 9.1, 9.3, 10 | — | High | Aug 2027 | 1 | GRC Analyst, MD |

**Resources.** Cycle 1 needs about **10.5 auditor days on site, or about 12 days including planning and reporting.** Charter §8.1 budgeted 5–7 days, so the MD is asked to approve the higher figure (charter v1.0).

## 6. Coverage

Cycle 1 covers **every clause from 4 to 10 and every applicable Annex A control,** as certification requires before Stage 1.

| Area | Audits |
| --- | --- |
| Clauses 4, 5, 7 | AUD-01 |
| Clause 6 | AUD-01 (6.2), AUD-02 (6.1) |
| Clause 8 | AUD-02 |
| Clauses 9, 10 | AUD-10 |
| Annex A organisational controls (5.x) | AUD-01, 03, 05, 06, 07, 08, 09 |
| Annex A people controls (6.x) | AUD-03, 07, 09 |
| Annex A physical controls (7.x) | AUD-09 (head office only, NSD-ISMS-004) |
| Annex A technological controls (8.x) | AUD-03, 04, 05, 08, 09 |

The GRC Analyst keeps a **coverage matrix** of each applicable SoA control against the audit that covers it. Any gap is added to the nearest audit before the cycle starts.

**Later cycles.** After certification:

- clauses 4 to 10 are audited every year;
- Annex A areas with **Very High or High** risks, or with previous findings, are audited every year;
- all other applicable controls are audited **at least once in each 3-year certification cycle**.

## 7. Audit criteria and methods

**Criteria:**

- ISO/IEC 27001:2022;
- the SoA (NSD-ISMS-019);
- policies NSD-ISMS-022 to 029 and their standards and procedures;
- legal and contractual requirements (NSD-ISMS-003, NSD-ISMS-005).

**Methods:**

- reviewing documents and records;
- interviewing management, owners and staff;
- observing processes, including live restore and failover tests;
- **re-performing the effectiveness tests in NSD-ISMS-021**, using its sample sizes (§4.3);
- inspecting configurations and logs, with authorisation and read-only access.

Evidence that the auditor re-performs counts more than evidence the auditee provides (NSD-ISMS-021 §4.1).

## 8. Findings

| Grade | Definition | Corrective action deadline |
| --- | --- | --- |
| **Major nonconformity** | A requirement is not met at all, or there is a systemic failure that puts the ISMS outcomes at risk | Correction and corrective action plan within **10 working days**. Closed and verified **before Stage 2** |
| **Minor nonconformity** | A single or isolated lapse against a requirement | Plan within 20 working days; closed within **90 days** |
| **Observation** | Not yet a nonconformity, but could become one | Owner decides on action; reviewed at the next audit |
| **Opportunity for improvement** | Good practice suggestion | Optional |

Each finding states:

- the requirement;
- the evidence;
- why the evidence does not meet the requirement.

## 9. Conducting each audit

1. The auditor sends the **audit plan** (scope, criteria, schedule, samples requested) **2 weeks before** the audit.
2. An **opening meeting** confirms the scope and logistics.
3. Fieldwork: evidence collection and sampling.
4. A **closing meeting** presents the findings. Disagreements are recorded.
5. The **report** is issued within **10 working days**, to the auditees, the MD and the Steering Group.

## 10. Reports

Each audit report contains:

- objectives, scope and criteria;
- dates, auditor and auditees;
- the auditor's independence confirmation;
- a summary of work performed;
- evidence reviewed and samples tested, with the population source;
- findings by grade;
- an audit conclusion on conformity and effectiveness;
- the corrective actions required.

## 11. Follow-up

1. Findings are recorded in the **corrective action register** (clause 10.2), with an owner and due date.
2. Owners record:
    - the **correction** (fixing the immediate issue);
    - the **root cause**;
    - the **corrective action** (preventing it happening again).
3. **The auditor verifies** completion and effectiveness. The GRC Analyst does not verify findings in areas they designed.
4. Findings that affect a risk or control are reflected in NSD-ISMS-014 and NSD-ISMS-019.
5. Audit results and corrective action status are a required input to **management review** (clause 9.3), in September 2027.

## 12. Records

| Record | Classification | Retention |
| --- | --- | --- |
| Approved programme and coverage matrix | Internal | 3 years |
| Audit plans, checklists and working papers | Confidential | 3 years |
| Evidence and sampling records | Confidential | 3 years |
| Audit reports and findings register | Confidential | 3 years |
| Corrective action and closure evidence | Confidential | 3 years after closure |
| Auditor independence and competence records | Internal | 3 years |

## 13. Programme measures

| Measure | Target |
| --- | --- |
| Audits completed as scheduled | 100% before management review |
| Applicable SoA controls covered in cycle 1 | 100% |
| Major nonconformities open at Stage 2 | 0 (Obj 10) |
| Corrective actions closed by their due date | 90% or higher |

## 14. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the programme and auditor resources | Pending | |
| ISMS Steering Group | Reviews coverage and priorities | Pending | |
| Information Security / GRC Analyst | Programme manager | Prepared | |

---

*Portfolio note: Simulated programme for a fictional organisation.*
