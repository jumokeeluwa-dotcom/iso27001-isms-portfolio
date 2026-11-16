# Northstar Digital Solutions Ltd — Risk Acceptance Criteria and Approval Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-016 |
| Version | 0.2 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 6.1.2(a)(1), 6.1.3(f), 8.3) |
| Related documents | [NSD-ISMS-012 Methodology](12-risk-assessment-methodology.md) · [NSD-ISMS-013 Scoring Matrix](13-risk-scoring-matrix.md) · [NSD-ISMS-014 Risk Register](14-risk-register.md) · [NSD-ISMS-015 Treatment Plan](15-risk-treatment-plan.md) |
| Criteria owner | Managing Director |
| Register owner | Information Security / GRC Analyst (maintains records; **does not accept risk**) |
| Review frequency | Criteria: annually and when the business strategy changes. Register: at each Steering Group meeting |
| Classification | Confidential |

---

## 1. Purpose

This document has two parts:

- **Part A — Acceptance criteria.** The risk appetite, who may accept each band of risk, for how long, and the risks that cannot be accepted at all (clause 6.1.2(a)(1)).
- **Part B — Approval register.** Every acceptance decision, proposed or granted, for the risks in NSD-ISMS-014 (clause 6.1.3(f)).

Part A must be approved by the MD before the scores in NSD-ISMS-014 stop being provisional. Clause 6.1.2(a) requires the criteria to come first.

**Core principle.** The GRC Analyst coordinates, records and advises, and never accepts risk on behalf of the business. Risk owners propose and justify decisions. Authorised management approves them under Part A.

## Part A — Acceptance criteria

## 2. Risk appetite

| Area | Appetite | What this means |
| --- | --- | --- |
| Confidentiality of customer data | **Low** | Risks of a reportable breach must be treated to Medium or below. Very High is never tolerated beyond the interim period in section 5 |
| Legal, regulatory and contractual compliance | **Very low** | Known non-compliance cannot be accepted (section 4) |
| Platform availability | **Moderate** | Short disruption within the 4-hour RTO is tolerable. Disruption beyond the RTO must be treated |
| Integrity of code, finance and security evidence | **Low** | Risks that could ship malicious code, allow fraud or destroy evidence are treated as a priority |
| Internal operations and productivity | **Moderate** | Proportionate controls; some residual risk accepted to keep the business running |

## 3. Authority to accept

Authority follows the band of the **residual risk being accepted** (NSD-ISMS-013).

| Band | Who may accept | Maximum acceptance period | Conditions | Review |
| --- | --- | --- | --- | --- |
| 🟥 Very High (16–25) | **MD only**, in writing, and only in exceptional circumstances | 3 months, renewable once | Compensating controls mandatory; treatment plan in progress; Steering Group informed | Monthly |
| 🟧 High (10–15) | **ISMS Steering Group** (chaired by the MD) | 6 months | Written justification; compensating controls or a dated treatment path | Quarterly |
| 🟨 Medium (5–9) | **Risk owner**; Steering Group informed | 12 months | Written justification | Six-monthly |
| 🟩 Low (1–4) | **Risk owner** | 12 months | Recorded in the register | Annually |

**Additional rules**

1. **Severe impact.** If the accepted risk has impact 5, the **MD must approve**, whatever the band (NSD-ISMS-013 §5).
2. **Personal data.** If a risk involves personal data, the Data Protection lead is consulted before acceptance and their view is recorded.
3. **GRC-owned risks.** Risks owned by the GRC Analyst (currently R-15) are accepted by the Steering Group, never by the GRC Analyst.
4. **No splitting.** A risk owner may not split a risk into smaller ones to bring each within their own authority.
5. **No self-approval of delays.** If acceptance is needed because a treatment action is late, the acceptance cannot be approved by that action's owner.

## 4. Risks that cannot be accepted

Internal risk acceptance cannot waive an external obligation. The following are **not acceptable at any level**. They must be treated, or the activity stopped:

| Category | Example in the register |
| --- | --- |
| Known breach of data protection law | EU personal data processed outside the permitted region without a lawful transfer mechanism (R-02) |
| Known breach of a customer contract or DPA | Missing the customer breach-notification timescale (R-18) |
| A control mandated by contract, insurance or certification that is knowingly absent | Insurer-required MFA not enforced (R-11) |

**Narrow exception.** A time-limited remediation period may be approved jointly by the MD and the Data Protection lead. For contractual obligations, the affected customer must agree in writing. This is a remediation period, not an acceptance: the risk stays open, and the plan to close it is tracked.

## 5. Decision statuses

| Status | Meaning |
| --- | --- |
| **In treatment** | Treatment approved and in progress. The current residual risk is **tolerated temporarily** by the authority for its band, until the treatment due date |
| **Target accepted (conditional)** | The risk owner and authority accept the target residual risk. The acceptance takes effect only once the GRC Analyst has verified the treatment and the risk has been re-scored |
| **Accepted** | The current residual risk is accepted without further treatment, within its expiry date |
| **Not acceptable** | Falls under section 4; must be treated |
| **Expired** | Past its expiry date or invalidated. Reassess within 10 working days; until then it is reported as an unaccepted risk |

**Temporary tolerance of Very High risks.** While treatment is in progress, a Very High risk is tolerated only with the MD's written acknowledgement. It must have dated interim controls and a monthly review (NSD-ISMS-013 §4).

## 6. What invalidates an acceptance

An acceptance ends before its expiry date if:

- a related incident or near miss occurs;
- new threat intelligence raises likelihood, such as an actively exploited vulnerability;
- a compensating control or condition fails or is removed;
- the asset, its data or its customers change materially, for example a new regulated FS customer (IP-03);
- a legal, regulatory or contractual requirement changes (NSD-ISMS-003).

The GRC Analyst flags invalidated acceptances to the risk owner and the Steering Group within 5 working days.

## 7. Acceptance principles

1. Only the authority named in section 3 may approve an acceptance.
2. Every acceptance complies with these criteria and is recorded in Part B.
3. Very High and High risks are escalated as section 3 requires. They are not held at risk-owner level.
4. Acceptance does not close a risk. Accepted risks stay in the register and are reviewed.
5. Every acceptance has an expiry date. There are no open-ended acceptances.
6. Changes in threat, vulnerability, impact or control effectiveness can end an acceptance (section 6).
7. Legal, regulatory and contractual obligations cannot be waived by internal acceptance (section 4).

## Part B — Approval register

## 8. Current position

**No risk has been accepted.** All 20 risks are **In treatment** under NSD-ISMS-015. The table below records who must approve each interim tolerance and target acceptance.

| Risk | Current | Status | Interim tolerance approved by | Target | Target acceptance authority | Next review |
| --- | --- | --- | --- | --- | --- | --- |
| R-06 | 🟥 20 | In treatment | MD (written; Very High) | 🟨 8 | Risk owner (Head of Engineering) | Monthly |
| R-12 | 🟥 16 | In treatment | MD (written; Very High) | 🟨 8 | Risk owner (HR Manager); DP lead consulted | Monthly |
| R-14 | 🟥 20 | In treatment | MD (written; Very High) | 🟨 6 | Risk owner (IT Manager) | Monthly |
| R-19 | 🟥 16 | In treatment | MD (written; Very High) | 🟨 8 | Risk owner (Managing Director); DP lead consulted | Monthly |
| R-01 | 🟧 15 | In treatment | Steering Group; MD (impact 5) | 🟨 8 | Risk owner (Head of Engineering); DP lead consulted | Quarterly |
| R-07 | 🟧 15 | In treatment | Steering Group; MD (impact 5) | 🟧 10 | **Steering Group with MD** (High, impact 5): see record AR-01 | Quarterly |
| R-08 | 🟧 15 | In treatment | Steering Group; MD (impact 5) | 🟨 8 | Risk owner (Head of Engineering) | Quarterly |
| R-09 | 🟧 10 | In treatment | Steering Group; MD (impact 5) | 🟨 6 | Risk owner (Head of Engineering) | Quarterly |
| R-13 | 🟧 15 | In treatment | Steering Group; MD (impact 5) | 🟧 10 | **Steering Group with MD** (High, impact 5): see record AR-02 | Quarterly |
| R-16 | 🟧 15 | In treatment | Steering Group; MD (impact 5) | 🟨 8 | Risk owner (Finance Manager) | Quarterly |
| R-17 | 🟧 15 | In treatment | Steering Group; MD (impact 5) | 🟨 8 | Risk owner (Head of Engineering) | Quarterly |
| R-02 | 🟧 12 | **Not acceptable** at the current level (section 4) | MD and DP lead (remediation period) | 🟩 4 | Risk owner (Data Protection lead) | Quarterly |
| R-03 | 🟧 12 | In treatment | Steering Group | 🟨 8 | Risk owner (HR Manager); DP lead consulted | Quarterly |
| R-04 | 🟧 12 | In treatment | Steering Group | 🟨 6 | Risk owner (Finance Manager) | Quarterly |
| R-05 | 🟧 12 | In treatment | Steering Group | 🟨 8 | Risk owner (Head of Engineering) | Quarterly |
| R-10 | 🟧 12 | In treatment | Steering Group | 🟨 8 | Risk owner (IT Manager) | Quarterly |
| R-11 | 🟧 12 | **Not acceptable** at the current level if MFA is insurer-required (section 4) | MD (remediation period) | 🟨 8 | Risk owner (IT Manager) | Quarterly |
| R-15 | 🟧 12 | In treatment | Steering Group | 🟩 4 | **Steering Group** (GRC-owned) | Quarterly |
| R-18 | 🟧 12 | **Not acceptable** at the current level: customer notification duties (section 4) | MD and DP lead (remediation period) | 🟩 4 | Risk owner (Data Protection lead) | Quarterly |
| R-20 | 🟨 8 | In treatment | Risk owner | 🟩 4 | Risk owner (IT Manager) | Six-monthly |

**Summary of approvals needed when the plan is approved**

- **MD:** written interim tolerance for the 4 Very High risks; interim approval for the 7 High risks with impact 5; remediation periods for R-02, R-11 and R-18.
- **Steering Group with MD:** conditional acceptance of the High targets for R-07 and R-13.
- **Steering Group:** interim tolerance for the other High risks; target acceptance for GRC-owned R-15.
- **Risk owners:** conditional acceptance of the 17 Medium and Low targets.

## 9. Individual acceptance records

Records are created for every risk proposed for acceptance at High or above. Both current records are **proposed, not granted**.

### AR-01 — R-07: CI/CD supply-chain compromise

| Field | Entry |
| --- | --- |
| Risk | R-07: a compromised third-party dependency or build tool injects malicious code into a release shipped to all customers |
| Score being accepted | **Target residual** 2 × 5 = 10, High (current 3 × 5 = 15) |
| Risk owner | Head of Engineering |
| Proposed decision | Target accepted (conditional) |
| Reason for acceptance | Once T-07.1 and T-07.2 are done, the remaining exposure comes from upstream open-source and vendor tooling that Northstar does not control. Impact stays 5 because one malicious release would reach every customer |
| Why further treatment is not proportionate now | Further reduction needs reproducible builds and software bill of materials (SBOM) verification across all dependencies, estimated at several months of DevOps effort. That would compete with the P1 actions (NSD-ISMS-015 §5) |
| Consequences and affected parties | Customers (IP-01, IP-03); possible notification to regulators (IP-08, IP-09); reputation |
| Compensating controls | Deployments approved by a second person (T-07.2); WAF and monitoring (T-17.2, T-01.2); incident procedure (T-18.1) |
| Conditions | 1. T-07.1 and T-07.2 verified. 2. An SBOM roadmap brought to the Steering Group by June 2027. 3. Dependency alerts reviewed weekly |
| Approval authority | ISMS Steering Group with MD approval (High; impact 5) |
| Data Protection lead | Consulted: customer personal data could be exposed |
| Approval date | Pending |
| Expiry | 6 months from approval |
| Reassessment triggers | A major supply-chain incident in the sector; a new regulated FS customer (DORA, IP-03); a failed condition |

### AR-02 — R-13: Privileged credential compromise

| Field | Entry |
| --- | --- |
| Risk | R-13: administrator credentials are stolen or misused, giving full control of Azure or Microsoft 365 |
| Score being accepted | **Target residual** 2 × 5 = 10, High (current 3 × 5 = 15) |
| Risk owner | IT Manager |
| Proposed decision | Target accepted (conditional) |
| Reason for acceptance | With just-in-time access (T-13.1) and monitored break-glass accounts (T-13.2), likelihood falls to Unlikely. Impact stays 5 because a successful administrator compromise still gives full control |
| Why further treatment is not proportionate now | Further reduction would need dedicated privileged-access workstations and 24/7 monitoring of administrator activity. Neither is affordable for an 85-person company in this cycle |
| Consequences and affected parties | Every customer (IP-01) and employee (IP-04); regulators (IP-08, IP-09); insurer (IP-13) |
| Compensating controls | Phishing-resistant MFA for administrators (T-10.1); immutable backups (T-14.1); separate backup administrator role (T-14.2); immutable logs (T-15.1) |
| Conditions | 1. T-13.1 and T-13.2 verified. 2. Monthly review of privileged role activations. 3. Quarterly break-glass test passed |
| Approval authority | ISMS Steering Group with MD approval (High; impact 5) |
| Data Protection lead | Consulted |
| Approval date | Pending |
| Expiry | 6 months from approval |
| Reassessment triggers | Any privileged account incident; a change of identity platform; a failed condition |

### 9.1 Record template

Each record contains these fields:

- Risk ID and scenario.
- Score being accepted, current or target, with L, I and band.
- Risk owner.
- Proposed decision.
- Reason for acceptance.
- Why further treatment is not proportionate.
- Consequences and affected parties.
- Compensating controls.
- Conditions.
- Approval authority, and the Data Protection lead's view.
- Approval date.
- Expiry.
- Reassessment triggers.

## 10. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves Part A criteria and appetite; grants MD-level decisions in Part B | Pending | |
| ISMS Steering Group | Reviews the criteria; decides Steering Group items in Part B | Pending | |
| Data Protection lead | Validates section 4 and the personal data rules | Pending | |
| Information Security / GRC Analyst | Prepared and maintains the register; **no acceptance authority** | Prepared | |

## 11. Change log

| Version | Change |
| --- | --- |
| 0.2 | Risk owners updated to match NSD-ISMS-017: R-02 and R-18 to the Data Protection lead, R-12 to the HR Manager, R-19 to the MD. GRC-owned risks are now R-15 only. |
| 0.1 (portfolio draft, as NSD-ISMS-014) | Approval register for 10 risks, all "Senior Management"; field list and seven principles |
| 0.1 | Numbered NSD-ISMS-016, the number reserved in NSD-ISMS-012; retitled to include the criteria. Added Part A: risk appetite, authority by band, maximum periods, the Severe-impact and personal data rules, GRC-owned risks, non-acceptable risks, decision statuses and invalidation triggers. Part B aligned with the NSD-ISMS-014 IDs and scores and extended to all 20 risks, separating interim tolerance from target acceptance. Added full acceptance records for R-07 and R-13. Principle 5 changed from "where appropriate" to "always time-limited". "Senior Management" replaced by named authorities. |

---

*Portfolio note: No risk acceptance has been granted. All entries are proposed decisions for a fictional organisation.*
