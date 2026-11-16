# ISO/IEC 27001:2022 ISMS Portfolio — Northstar Digital Solutions Ltd

A simulated, end-to-end build of an Information Security Management System (ISMS) for a fictional UK SaaS company, aligned to **ISO/IEC 27001:2022 including Amendment 1:2024**. It runs from project charter to mock certification audit: **67 documents across 12 milestones**.

> **Simulated work.** Northstar Digital Solutions Ltd is fictional. Every record, finding, figure and decision is a training example. Nothing here represents a real organisation, a real audit or a real certification.

## The scenario

| | |
| --- | --- |
| Organisation | B2B SaaS provider, about 85 people |
| Locations | UK head office; hybrid UK staff; EU-based personnel |
| Technology | Microsoft Azure (UK and EU regions), Microsoft 365, Entra ID |
| Customers | UK and EU businesses, including regulated financial services (DORA flow-down) |
| Security function | A small IT team and one GRC Analyst |
| Legal context | UK GDPR, Data Protection Act 2018 as amended by the Data (Use and Access) Act 2025, EU GDPR, customer contracts and DPAs |

## Milestones

| # | Milestone | Documents | What it covers |
| --- | --- | --- | --- |
| 1 | [Initiation and context](docs/01-initiation-and-context/) | 001–004 | Charter, context (incl. climate change), interested parties, scope |
| 2 | [Information asset management](docs/02-asset-management/) | 006–011 | Asset register, ownership, classification, valuation, asset–risk mapping |
| 3 | [Risk assessment and treatment](docs/03-risk-management/) | 012–017 | Methodology, 5×5 matrix, risk register, treatment plan, acceptance criteria |
| 4 | [Controls and SoA](docs/04-controls-and-soa/) | 018–021 | SoA method, Statement of Applicability, risk–control mapping, evidence checklist |
| 5 | [Policies](docs/05-policies/) | 022–029 | Eight topic policies |
| 6 | [Internal audit](docs/06-internal-audit/) | 030–035 | Audit programme and a complete worked audit (AUD-03, identity and access) |
| 7 | [Management review](docs/07-management-review/) | 036–040 | Procedure, agenda and inputs, minutes template, actions, summary |
| 8 | [Monitoring and measurement](docs/08-monitoring-and-measurement/) | 041–044 | 21 KPIs, measurement plan, validated dashboard |
| 9 | [Improvement](docs/09-improvement/) | 045–048 | Continual improvement, corrective action, improvement register, root cause analysis |
| 10 | [Business continuity](docs/10-business-continuity/) | 049–054 | BIA, BCP, DRP, recovery objectives, incident exercise, restore test |
| 11 | [Supplier risk](docs/11-supplier-risk/) | 055–060 | Supplier register, risk method, questionnaire, assessments, review, assurance report |
| 12 | [Certification readiness](docs/12-certification-readiness/) | 061–068 | Gap assessment, Annex A readiness, SoA validation, evidence index, readiness report, mock Stage 1 and 2, remediation tracker |

Each folder has its own index, with links to the Markdown document and the Word version.

**[Portfolio summary (one page)](career/portfolio-summary.md)** · [Word version](career/ISO27001-Analyst-Portfolio-Summary.docx)

## If you only have ten minutes

| Read | Why |
| --- | --- |
| [001 ISMS Project Charter](docs/01-initiation-and-context/01-isms-project-charter.md) | Objectives, roles and governance everything else hangs from |
| [014 Risk Register](docs/03-risk-management/14-risk-register.md) | 20 risk scenarios with inherent, current and target ratings |
| [019 Statement of Applicability](docs/04-controls-and-soa/19-statement-of-applicability.md) | Risk-driven control selection with evidence-based statuses |
| [035 Internal Audit Report AUD-03](docs/06-internal-audit/35-internal-audit-report-aud03.md) | A full worked audit: sampling, findings and grading |
| [048 Root Cause Analysis RCA-01](docs/09-improvement/48-root-cause-analysis-report-rca01.md) | Testing hypotheses rather than stopping at "human error" |
| [065 Certification Readiness Report](docs/12-certification-readiness/65-certification-readiness-report.md) | The overall conclusion and the evidence behind it |
| [066 Mock Stage 1 Audit](docs/12-certification-readiness/66-mock-stage1-audit.md) | An independent check that found what the self-assessment missed |

## Where the ISMS stands

The portfolio ends with an honest conclusion. **Northstar is not ready for a Stage 1 certification audit:**

- 0 of 25 clause requirements and 0 of 93 Annex A controls fully ready;
- core documents (scope, policy, risk criteria, SoA) not yet approved;
- no management review recorded, and 8 of 9 planned internal audits without records;
- recovery, failover and supplier assurance not yet evidenced.

It also shows what **is** working: a validated KPI dashboard, a worked internal audit, and corrective actions with root cause analysis. All gaps are tracked to owners and dates in the [remediation tracker (068)](docs/12-certification-readiness/68-remediation-tracker.md).

## How the work was done

These principles run through every document:

- **Missing records are never counted as success,** and "no events" is never reported as 100%.
- **Each item lives in one register only,** with one accountable owner, so it has one status.
- **No one verifies their own work.** The GRC Analyst coordinates but never accepts risk or verifies its own actions.
- **Controls come from risk treatment and** are then compared with Annex A (clause 6.1.3). Annex A is not used as a checklist.
- **Correction, corrective action and effectiveness verification are kept separate.**
- **Drafts are challenged before they are accepted.** Every document ends with a change log recording what was found and fixed.

**Examples of judgement calls you can trace in the change logs:**

- A separate 3×3 supplier risk scale was replaced with the organisation's 5×5 matrix, so all risks stay comparable (056).
- A supplier KPI reported as 80% was reset to 0 of 7 when its records could not be found (058, 060).
- A clause 10.2 mapping borrowed from ISO 9001 was found and corrected (034).
- A management review treated as held was found to have no minutes, and every affected document was corrected (061–067).
- A mock auditor found that KPI validation had passed three unsupported results (066).

## Repository structure

```
README.md
career/                             portfolio summary (.md and .docx)
docs/
  01-initiation-and-context/        README.md, 001–004 (.md and .docx)
  02-asset-management/              006–011
  03-risk-management/               012–017
  04-controls-and-soa/              018–021
  05-policies/                      022–029
  06-internal-audit/                030–035
  07-management-review/             036–040
  08-monitoring-and-measurement/    041–044
  09-improvement/                   045–048
  10-business-continuity/           049–054
  11-supplier-risk/                 055–060
  12-certification-readiness/       061–068
```

## Conventions

| Item | Convention |
| --- | --- |
| Document IDs | NSD-ISMS-001 to 068. **005 (legal register) is deliberately unwritten:** it is a recorded gap |
| Roles | Charter roles only: MD, IT Manager, Head of Engineering, HR Manager, Finance Manager, Data Protection lead, GRC Analyst, Sales lead, Customer Support Manager |
| Risk bands | Low 1–4 · Medium 5–9 · High 10–15 · Very High 16–25 (5×5 matrix) |
| SoA statuses | Implemented · Partially implemented · Planned · Not implemented · To be assessed. Applicability is Yes or No only |
| Evidence types | Documented · Operational · Effectiveness |
| Classification | Restricted · Confidential · Internal · Public |
| Word versions | A4 landscape; footer shows document, classification, "Simulated" and page number |

## Standards and frameworks referenced

ISO/IEC 27001:2022 and Amendment 1:2024 · ISO/IEC 27005:2022 (risk terms) · ISO 22301 (continuity terms) · UK GDPR, EU GDPR · DORA (contractual flow-down from financial services customers).

## About

Prepared as a professional development portfolio by **Jumoke Eluwa** · [LinkedIn](https://www.linkedin.com/in/jumokeeluwa/)

*All content is simulated for learning and demonstration. It does not represent an actual approved ISMS, audit or certification.*
