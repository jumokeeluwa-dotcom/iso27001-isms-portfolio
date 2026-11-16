# Northstar Digital Solutions Ltd — ISMS Monitoring and Measurement Procedure

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-041 |
| Version | 0.2 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 6.2, 9.1) |
| Related documents | NSD-ISMS-042 KPI Register · NSD-ISMS-043 Monitoring and Measurement Plan · NSD-ISMS-044 Performance Dashboard · [NSD-ISMS-021 Evidence Checklist](../04-controls-and-soa/21-control-evidence-checklist.md) · [NSD-ISMS-036 Management Review](../07-management-review/36-management-review-procedure.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually, and when objectives or KPI definitions change |
| Classification | Internal |

---

## 1. Purpose

This procedure defines how Northstar monitors, measures, analyses and evaluates:

- its **information security performance**: are controls working?
- the **effectiveness of the ISMS**: are objectives met and risks reduced? (clause 9.1)

It is about whether security arrangements **work**, not whether policies exist.

## 2. Scope

The procedure covers:

- the information security objectives (charter Obj 1–10);
- risk treatment progress;
- the effectiveness of SoA controls;
- incidents;
- access management;
- suppliers;
- audit findings and corrective actions;
- the ISMS processes themselves.

## 3. A single source of measures

Measures already appear in several ISMS documents. To prevent different definitions of the same measure:

1. **The KPI register (NSD-ISMS-042) is the only place a measure is defined:** its calculation, source, target and thresholds.
2. Other documents **refer to the KPI ID** and do not redefine it. This applies to the charter objectives, the policy measures sections (NSD-ISMS-023 to 029 §12), the audit programme (NSD-ISMS-030 §13), the corrective action register (NSD-ISMS-034 §7) and the management review documents.
3. Where an existing document's measure differs from the register, the register wins, and the other document is corrected at its next revision.

## 4. Types of measure

| Type | Purpose | Example |
| --- | --- | --- |
| **Objective measure** | Tracks a charter objective (clause 6.2) | Obj 5: training completion of 95% or higher |
| **Control effectiveness (KPI)** | Shows whether a control achieves its outcome. Based on the NSD-ISMS-021 tests | Leavers disabled by the end of the last working day |
| **Risk indicator (KRI)** | An early warning that a risk is rising | Critical vulnerabilities older than 14 days |
| **Process measure** | Shows whether ISMS processes run on time | Audits completed as scheduled; corrective actions closed on time |

**Selection rules**

- Every measure links to an objective, a risk or an SoA control. **A measure that informs no decision is not kept.**
- Use a mix of leading measures (early warnings) and lagging measures (outcomes).
- The register holds **about 20 KPIs at most.** Fewer measures, reviewed properly, beat many measures that nobody reads.

## 5. Clause 9.1 requirements and how they are met

| Clause 9.1 | How Northstar defines it | Recorded in |
| --- | --- | --- |
| (a) What is monitored and measured | Each KPI, linked to an objective, risk or control | NSD-ISMS-042 |
| (b) Methods that give valid results | Calculation, population, data source and validation rules (section 6). Results must be **comparable and reproducible** | NSD-ISMS-042 |
| (c) When monitoring and measurement happen | Collection frequency for each KPI | NSD-ISMS-043 |
| (d) Who monitors and measures | **Data owner:** the control owner who provides the figure | NSD-ISMS-042, 043 |
| (e) When results are analysed and evaluated | Monthly at the Steering Group; quarterly trend review; annually at management review | NSD-ISMS-043 |
| (f) Who analyses and evaluates | **The GRC Analyst analyses; the Steering Group and the MD evaluate.** A data owner does not evaluate their own results | NSD-ISMS-043, 044 |
| Documented information as evidence | Source extracts, the dashboard and the evaluation records | Section 10 |

## 6. Making results valid

1. **Precise definition.** Every KPI states its numerator, denominator, population, exclusions, period and data cut-off. "MFA coverage" becomes: *accounts with MFA or a managed identity, divided by all enabled accounts in Entra ID, at the last day of the month*.
2. **System sources first.** System-generated reports are preferred to spreadsheets or statements (NSD-ISMS-021 §4.1). The source report is kept.
3. **Validation.** Each quarter, the GRC Analyst re-performs the calculation for a sample of KPIs from the source data. Internal audit (AUD-10) tests the accuracy of KPI data each year.
4. **Labelling limits.** Where data is incomplete or not validated, the result is labelled **"Unvalidated"** and is not shown as confirmed performance.
5. **Stable definitions.** Changing a KPI's definition is version-controlled and approved by the Steering Group. The dashboard notes where a change breaks the trend.

## 7. Ratings

The ratings are the same as in NSD-ISMS-040 §3, so all reports use one scale:

| Rating | Meaning |
| --- | --- |
| **Green** | Target met, or on plan |
| **Amber** | Below target but within an agreed recovery plan, or less than 10% off target |
| **Red** | Off target with no recovery plan, 10% or more off target, or a hard limit breached |
| **Unvalidated** | The data could not be validated. Treated as Amber until validated |

Some KPIs have a **hard limit**, where any miss is Red. Examples: a legal notification deadline missed, or a leaver's account used after leaving.

## 8. Analysis and evaluation

Each period's results are compared with:

- objective targets and KPI thresholds;
- previous periods (trends over at least 3 periods where data exists);
- the risk register: does a result change a risk's likelihood or the credit given to a control?
- audit findings and incidents;
- contractual and legal requirements, such as SLAs and notification deadlines.

**Investigation is required** for any Red result, any Amber result for two periods in a row, any worsening trend over three periods, and any unexpected change.

## 9. Escalation

| Trigger | Action | Timescale |
| --- | --- | --- |
| A KPI turns **Red** | The KPI owner investigates and reports the cause and a recovery plan | Within 10 working days |
| Red for **two periods in a row**, or an Amber recovery plan missed | Reported to the Steering Group; assessed as a possible nonconformity and, if so, entered in NSD-ISMS-034 | Next Steering Group |
| A **hard limit** breached, or a KPI linked to a **Very High** risk or a legal or contractual duty goes Red | Escalated to the MD; treated as an incident where relevant (NSD-ISMS-027) | Within 2 working days |
| An effectiveness KPI fails | The SoA status drops (NSD-ISMS-021 §3), and linked risks are re-scored (NSD-ISMS-014) | Next risk review |
| Objective off track at the quarterly review | The objective owner proposes recovery or a target change, for MD decision | Next management review, or sooner |

## 10. Responsibilities

| Role | Responsibility |
| --- | --- |
| Managing Director | Evaluates significant trends; decides on objective changes, resources and priorities |
| ISMS Steering Group | Monthly evaluation of the dashboard; approves KPI definition changes; decides on escalations |
| Information Security / GRC Analyst | Maintains NSD-ISMS-042 and 043; collects and **analyses** results; validates data; prepares NSD-ISMS-044; escalates |
| IT Manager | Data owner for corporate IT, identity, endpoints, backups and Microsoft 365 KPIs |
| Head of Engineering | Data owner for platform, vulnerability, change and cloud configuration KPIs |
| HR Manager | Data owner for training, joiner, mover and leaver KPIs |
| Finance Manager | Data owner for supplier KPIs |
| Data Protection lead | Data owner for breach and data protection KPIs |
| Internal auditor | Tests KPI data accuracy each year (AUD-10) |

## 11. Records

| Record | Classification | Retention |
| --- | --- | --- |
| KPI register and monitoring plan (versioned) | Internal | 3 years |
| Source reports and system extracts | Confidential | 3 years |
| Dashboards and reports | Confidential (they show weaknesses) | 3 years |
| Analysis, validation and evaluation records; escalations | Confidential | 3 years |

## 12. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-037) | First draft |
| 0.2 | Numbered NSD-ISMS-041; 037 to 040 are management review documents. Approver changed to the MD. Added a single-source rule making the KPI register the only place a measure is defined. Defined measure types and selection rules. Mapped clause 9.1(a)–(f), separating **who monitors** (data owners) from **who analyses** (the GRC Analyst) and **who evaluates** (the Steering Group and MD). Added validation rules (precise definitions, system sources, quarterly re-performance, annual audit, the "Unvalidated" label), Red/Amber/Green ratings consistent with NSD-ISMS-040, hard limits, investigation triggers and an escalation table with timescales and links to corrective action, the SoA and risk re-scoring. "Department Managers" replaced with named data owners, including the Head of Engineering and Data Protection lead. The draft's six elements and its principle on unvalidated results are kept. |

---

*Portfolio disclaimer: Simulated procedure. It has not been approved or implemented by a real organisation.*
