# Northstar Digital Solutions Ltd — Information Security Risk Assessment Methodology

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-012 |
| Version | 1.0 — Draft for approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 6.1.1, 6.1.2, 6.1.3, 8.2, 8.3) |
| Related documents | [NSD-ISMS-002 Context](../01-initiation-and-context/02-organisational-context-register.md) · [NSD-ISMS-003 Interested Parties](../01-initiation-and-context/03-interested-party-requirements-register.md) · [NSD-ISMS-004 Scope](../01-initiation-and-context/04-isms-scope-statement.md) · [NSD-ISMS-009 Valuation](../02-asset-management/09-asset-valuation-methodology.md) · [NSD-ISMS-010 Risk Mapping](../02-asset-management/10-asset-risk-mapping.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually, and when the acceptance criteria change |
| Classification | Internal |

---

## 1. Purpose

This methodology defines how Northstar identifies, analyses, evaluates and treats information security risks. It covers the confidentiality, integrity and availability of information inside the ISMS scope (NSD-ISMS-004).

Clause 6.1.2(b) requires repeated assessments to give **consistent, valid and comparable results**. Every rule below is designed so that two assessors would reach the same score for the same scenario.

**Asset criticality is not risk.** A Critical asset (NSD-ISMS-009) does not automatically carry a high risk. Risk depends on a credible scenario, its likelihood, its consequence, and how well existing controls work. Criticality decides the **order** of assessment, not the score.

## 2. Milestone documents

| Ref | Document | Role |
| --- | --- | --- |
| NSD-ISMS-012 | Risk Assessment Methodology (this document) | Process and rules |
| NSD-ISMS-013 | Likelihood and Impact Scoring Matrix | Definitions of scores 1–5 and risk bands |
| NSD-ISMS-014 | Risk Register | 20 scenarios with inherent, current and target ratings |
| NSD-ISMS-015 | Risk Treatment Plan | Actions, owners, dates, evidence |
| NSD-ISMS-016 | Risk Acceptance Criteria | Thresholds and who may accept each level |
| NSD-ISMS-017 | Risk Ownership Register | Risk owners, authority and review duties |

**Approval order.** Clause 6.1.2(a) requires the acceptance criteria to be set before risks are assessed. NSD-ISMS-013 and NSD-ISMS-016 must therefore be approved by the MD **before** the scores in NSD-ISMS-014 are finalised.

## 3. Roles

| Role | Responsibility |
| --- | --- |
| Managing Director | Approves this methodology, the scoring matrix and the acceptance criteria; accepts risks above the Steering Group's authority |
| ISMS Steering Group | Reviews the risk register; challenges scores; accepts risks within its delegated authority (NSD-ISMS-016) |
| Risk owner | Accountable for the risk and the treatment decision. Must have the authority and budget to act (clause 6.1.2(c)(2)) |
| Asset owner | Provides asset knowledge. Often, but not always, the risk owner |
| Control owner / custodian | Provides evidence that existing controls work; delivers treatment actions |
| Information Security / GRC Analyst | Facilitates assessments, checks consistency, maintains records. **Does not accept risk** |
| Data Protection lead | Assesses impact for scenarios involving personal data |

## 4. When assessments happen

| Trigger | Scope |
| --- | --- |
| Annual full assessment | All risks, before management review |
| Significant change: a new system, supplier, location, product or architecture change | Affected risks, **before** the change goes live |
| Significant incident or near miss | Related risks, as part of lessons learned |
| New threat intelligence, e.g. an NCSC advisory relevant to Azure or Microsoft 365 | Related risks |
| Change in legal, regulatory or contractual requirements (NSD-ISMS-003) | Related risks |
| Audit finding, penetration test or vulnerability trend showing a change in risk | Related risks |
| Scheduled reviews by risk band | See section 9 |

The annual assessment is a fixed commitment approved with this methodology. It is not "subject to management approval".

## 5. Process

### Step 1 — Identify risks

Risks are identified from three sources, so that risks without a clear asset are not missed:

| Source | Finds |
| --- | --- |
| Asset-based: NSD-ISMS-010 scenarios | Risks to registered assets (ARM-01 to ARM-26) |
| Context and requirements: NSD-ISMS-002, 003 | Risks from external issues, legal duties and contracts |
| Process and supplier review | Risks in business processes, outsourced services and change activity |

Every risk is written as a scenario using this template:

> **[Threat source]** exploits **[vulnerability or control gap]** in **[asset, process or service]**, causing **[event]**, resulting in **[consequence]**.

*Example:* An external attacker uses a phishing email to steal a Microsoft 365 password where MFA is not enforced. They gain access to SharePoint, and Restricted HR files are disclosed, resulting in a reportable personal data breach.

Labels such as "ransomware" or "weak passwords" are not risks and are rejected at review.

### Step 2 — Analyse risks

| Element | Rule |
| --- | --- |
| Assessment period | Likelihood is the chance of the scenario happening **within 12 months** |
| Likelihood | Scored 1–5 using the frequency and evidence criteria in NSD-ISMS-013 |
| Impact | Scored 1–5 using NSD-ISMS-013, across confidentiality, integrity, availability, legal, contractual, financial and reputational effects. The **worst credible** consequence sets the score |
| Link to asset valuation | The asset's rating for the affected dimension (NSD-ISMS-009) is the starting point: High = 4 or 5, Medium = 3, Low = 1 or 2. The assessor may score differently if the scenario affects only part of the asset, but must give a reason |
| Evidence and confidence | Each score records its evidence and a confidence level: **High** (tested or measured), **Medium** (documented but untested), **Low** (assumption) |

### Step 3 — Rate the risk three times

| Rating | Meaning | Used for |
| --- | --- | --- |
| **Inherent** | Likelihood and impact if none of the specific controls for this scenario existed | Shows how much the controls are worth; sets priority for control monitoring |
| **Current residual** | Likelihood and impact with existing controls, **credited only as far as evidence supports** | Compared with the acceptance criteria |
| **Target residual** | Expected rating once the treatment plan is delivered | Approved by the risk owner with the treatment plan |

**Control credit rule.** Existing controls reduce the current residual score only according to their tested effectiveness:

| Control status | Credit given |
| --- | --- |
| Effective: tested with evidence in the last 12 months | Full reduction |
| Partially effective: in place, but with gaps or exceptions found | Partial reduction; the assessor explains it |
| Not tested: exists on paper or is said to exist | **No reduction** until tested |
| Not in place | None |

This rule stops policies that only exist on paper from lowering a risk score, which is a common audit finding.

### Step 4 — Evaluate risks

**Risk score = Likelihood × Impact**, giving a range of 1–25. Scores fall into four bands, defined in NSD-ISMS-013:

| Band | Score range |
| --- | --- |
| Very High | 16–25 |
| High | 10–15 |
| Medium | 5–9 |
| Low | 1–4 |

The current residual band is compared with the acceptance criteria (NSD-ISMS-016), which state:

- which bands can be accepted without treatment;
- who may accept each band;
- the maximum period an acceptance lasts.

Risks are then ranked by current residual score, with asset criticality (NSD-ISMS-009) breaking ties.

### Step 5 — Treat risks

| Option | When it is used | Note |
| --- | --- | --- |
| **Modify** (also called mitigate) | Implement or improve controls that reduce likelihood or impact | Most common option. Term from ISO/IEC 27005:2022 |
| **Avoid** | Stop or change the activity | E.g. withdraw a feature that cannot be secured |
| **Share** | Transfer part of the impact through contract or insurance | Accountability for customer data stays with Northstar |
| **Retain** | Accept the risk knowingly | Needs authorisation under NSD-ISMS-016 |

For risks being modified, the controls are determined from the scenario first, then compared with Annex A to check that no necessary control has been missed (clause 6.1.3(b)–(c)). The Statement of Applicability records each Annex A control as included or excluded, with the justification and implementation status (clause 6.1.3(d)).

### Step 6 — Approve, monitor and review

- Risk owners approve the treatment plan and accept the target residual risk (clause 6.1.3(f)).
- Actions are tracked in NSD-ISMS-015 until evidence of implementation is filed.
- When an action is completed, the risk is re-scored using the control credit rule.

## 6. Treatment plan contents

Each treatment entry in NSD-ISMS-015 records:

- Risk reference.
- Treatment option.
- Control or action, with its Annex A reference.
- Action owner.
- Target date.
- Resources needed.
- Status.
- Evidence of implementation.
- Target residual score.
- Risk-owner approval and, where required, management approval.

## 7. Risk acceptance

- Only the authority named in NSD-ISMS-016 for the risk's band may accept it.
- Each acceptance records the reason, any conditions, the expiry date and the next review date.
- An acceptance lapses at its expiry date or when circumstances change materially, whichever comes first.
- The GRC Analyst may recommend acceptance but never grants it.

## 8. Quality checks

Before risks go to the Steering Group, the GRC Analyst checks that:

- [ ] Every risk is a full scenario, not a label
- [ ] Every score has evidence and a confidence level
- [ ] No control without test evidence has reduced a score
- [ ] Impact scores that differ from the asset valuation have a recorded reason
- [ ] Every risk has an owner with real authority and budget
- [ ] Scores are consistent across similar scenarios. Each annual assessment includes a calibration session where owners compare their scores side by side

## 9. Monitoring and review

| Current residual band | Risk owner review |
| --- | --- |
| Very High | Monthly, until reduced |
| High | Quarterly |
| Medium | Six-monthly |
| Low | Annually |

The GRC Analyst reports these to each Steering Group meeting, and as input to management review (clause 9.3):

- the risk profile by band;
- overdue treatments;
- expiring acceptances;
- changes since the last report.

## 10. Records

| Record | Classification | Retention |
| --- | --- | --- |
| Risk register (NSD-ISMS-014) and change history | Confidential: it shows where Northstar is weak | 3 years |
| Treatment plan and implementation evidence | Confidential | 3 years after closure |
| Acceptance decisions | Confidential | 3 years after expiry |
| Assessment workshop notes and calibration records | Internal | 3 years |

These records are the documented information required by clauses 8.2 and 8.3.

## 11. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the methodology | Pending | |
| ISMS Steering Group | Reviews the methodology | Pending | |
| Information Security / GRC Analyst | Prepared the methodology | Prepared | |

---

*Portfolio note: This is a fictional draft, not an approved company procedure.*
