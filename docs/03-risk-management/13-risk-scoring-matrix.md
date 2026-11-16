# Northstar Digital Solutions Ltd — Likelihood and Impact Scoring Matrix

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-013 |
| Version | 0.1 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clause 6.1.2(a), (b), (d)) |
| Related documents | [NSD-ISMS-009 Valuation](../02-asset-management/09-asset-valuation-methodology.md) · [NSD-ISMS-010 Risk Mapping](../02-asset-management/10-asset-risk-mapping.md) · [NSD-ISMS-012 Methodology](12-risk-assessment-methodology.md) · NSD-ISMS-016 Risk Acceptance Criteria (planned) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually, with the methodology; and when the financial thresholds or risk appetite change |
| Classification | Internal |

---

## 1. Purpose

This matrix defines the likelihood and impact scores (1–5) used in every risk assessment under NSD-ISMS-012, and the four risk bands the scores produce.

It has to be approved **before** the risk register (NSD-ISMS-014) is scored. Clause 6.1.2(a) requires the criteria to exist before they are applied.

The thresholds are sized for Northstar: an 85-person UK SaaS provider, with customer data in Azure UK and EU regions, processing data for UK and EU business customers. They are proposals for MD approval, not universal ISO 27001 values.

## 2. Likelihood scale

Likelihood is the chance that **the whole scenario**, including its consequence, happens **within the next 12 months**.

| Score | Rating | Probability in 12 months | Frequency guide | Evidence indicators at Northstar |
| --- | --- | --- | --- | --- |
| 5 | Almost certain | Over 80% | More than once a year | Has happened at Northstar in the last 12 months, or is happening now |
| 4 | Likely | 50–80% | About once every 1–2 years | Has happened at Northstar or at similar SaaS firms recently; active threat intelligence; exposure is internet-facing |
| 3 | Possible | 20–50% | About once every 2–5 years | Known in the sector; attacker needs moderate skill or some insider knowledge |
| 2 | Unlikely | 5–20% | About once every 5–10 years | Rare in the sector; needs significant skill, access or an unusual combination of events |
| 1 | Rare | Under 5% | Less than once in 10 years | No known precedent; would need exceptional circumstances |

**Scoring rules**

- **Score the scenario, not the threat attempt.** Phishing emails arrive every day, but this does not make "phishing leads to a reportable breach" Almost certain. Score the full chain.
- **Controls are not part of the scale.** For **inherent** risk, score as if the scenario's specific controls did not exist. For **current residual** risk, reduce the score only for controls that pass the control credit rule (NSD-ISMS-012 §5, Step 3). The 1.0 draft defined Rare as "strong preventative measures", which mixed the two, so that wording is removed.
- **If torn between two scores,** take the higher and record Low confidence.

## 3. Impact scale

Impact is scored on the **worst credible** consequence. Assess every category; **the highest category sets the score**.

| Score | Rating | Financial (illustrative) | Data compromise | Service availability | Legal and regulatory | Customer and contractual | Reputational |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 5 | Severe | Over £500,000 | Several customers' data, more than 10,000 people, or special category data | Platform down more than 24 hours, or data loss beyond the RPO | Regulatory investigation or enforcement likely | Several customers terminate, or a key customer or tender is lost | National press; ISO 27001 certificate suspended |
| 4 | Major | £100,000 – £500,000 | A reportable breach affecting one or a few customers, up to 10,000 people | Platform down 4–24 hours; SLA breached | Reportable breach (ICO, EU authority, or customer as controller) | SLA breach for several customers; contract at risk | Trade press; customers escalate due-diligence questions |
| 3 | Moderate | £10,000 – £100,000 | One customer's data, or personal data of fewer than 100 people; unlikely to be reportable | Platform degraded, or a core internal service down for 1–2 working days | Non-compliance needing correction; not reportable | One customer: service credits or a formal complaint | Concern from a few customers or partners |
| 2 | Minor | £5,000 – £10,000 | Internal data only; no personal or customer data | Non-critical service down for less than 1 working day | Internal policy breach | One customer notices; informal complaint | Contained internally |
| 1 | Insignificant | Under £5,000 | No data compromised | Less than 1 hour; no customer notices | None | None | None |

**How the scale lines up with the other documents**

| Document | Alignment |
| --- | --- |
| Asset valuation (NSD-ISMS-009) | Its High, Medium and Low bands map to impact 4–5, 3 and 1–2. The £10k and £100k thresholds are the same |
| Recovery targets (NSD-ISMS-009 §5) | An outage beyond the 4-hour RTO for High-availability assets is impact 4 or above |
| Interested parties (NSD-ISMS-003) | Breach reporting covers the ICO and EU authorities (IP-08, IP-09). Northstar, as processor, must notify customers (IP-01) |
| Classification (NSD-ISMS-008) | Disclosure of Restricted data usually scores 4 or above; Confidential data usually 3 |

The financial thresholds are placeholders for the MD to approve. They must match the risk acceptance criteria (NSD-ISMS-016).

## 4. Risk score and bands

**Risk score = Likelihood × Impact** (range 1–25)

| Band | Score | Required response | Review (NSD-ISMS-012 §9) |
| --- | --- | --- | --- |
| 🟥 Very High | 16–25 | Escalate to the MD within 2 working days; treatment plan within 10 working days; any retention decision is the MD's alone | Monthly |
| 🟧 High | 10–15 | Treatment plan within 30 days; reported to the Steering Group | Quarterly |
| 🟨 Medium | 5–9 | Risk owner decides on treatment or acceptance | Six-monthly |
| 🟩 Low | 1–4 | Can be accepted and monitored by the risk owner | Annually |

Who may accept each band, and for how long, is set in NSD-ISMS-016. The responses above are the minimum actions for each band.

## 5. Heat map

Impact runs down the side, and likelihood runs along the top. Each cell shows the score and its band.

| Impact \ Likelihood | 1 Rare | 2 Unlikely | 3 Possible | 4 Likely | 5 Almost certain |
| --- | --- | --- | --- | --- | --- |
| 5 Severe | 🟨 5 · Medium | 🟧 10 · High | 🟧 15 · High | 🟥 20 · Very High | 🟥 25 · Very High |
| 4 Major | 🟩 4 · Low | 🟨 8 · Medium | 🟧 12 · High | 🟥 16 · Very High | 🟥 20 · Very High |
| 3 Moderate | 🟩 3 · Low | 🟨 6 · Medium | 🟨 9 · Medium | 🟧 12 · High | 🟧 15 · High |
| 2 Minor | 🟩 2 · Low | 🟩 4 · Low | 🟨 6 · Medium | 🟨 8 · Medium | 🟧 10 · High |
| 1 Insignificant | 🟩 1 · Low | 🟩 2 · Low | 🟩 3 · Low | 🟩 4 · Low | 🟨 5 · Medium |

**Severe impact needs a closer look.** A Severe scenario scores only Medium (5) when Rare, but it could still threaten the business. Any scenario with impact 5 is therefore reported to the Steering Group, whatever its band, and the MD decides whether to treat it.

## 6. Worked examples

These use NSD-ISMS-010 scenarios to show how the rules work. They are illustrative; the final scores are set in NSD-ISMS-014.

| Scenario | Rating | L | I | Score | Band | Reasoning |
| --- | --- | --- | --- | --- | --- | --- |
| ARM-13: account takeover through password attacks | Inherent | 5 | 4 | 20 | 🟥 Very High | Password spraying against Microsoft 365 is constant. Takeover of a staff account with access to Restricted data is a reportable breach |
| | Current residual | 3 | 4 | 12 | 🟧 High | MFA for staff is tested and effective, which lowers likelihood. Service accounts are excluded from MFA, so the control is only partially effective: partial credit |
| | Target residual | 2 | 4 | 8 | 🟨 Medium | MFA or managed identities extended to service accounts; legacy authentication blocked |
| ARM-10: Azure regional outage | Inherent | 2 | 5 | 10 | 🟧 High | Regional outages are rare, but the platform would be down for more than 24 hours |
| | Current residual | 2 | 5 | 10 | 🟧 High | A failover design exists on paper but has never been tested: **no credit** |
| | Target residual | 2 | 3 | 6 | 🟨 Medium | Tested failover to the paired region keeps recovery within the 4-hour RTO. Here the treatment reduces **impact**, not likelihood |
| ARM-04: payment fraud through altered bank details | Inherent | 4 | 3 | 12 | 🟧 High | Business email compromise targeting finance teams is common. A typical loss is £10k–£100k |
| | Current residual | 4 | 3 | 12 | 🟧 High | Dual approval is in the finance procedure but has never been tested: **no credit** |
| | Target residual | 2 | 3 | 6 | 🟨 Medium | Call-back verification for bank detail changes, enforced in the finance system and tested |

The examples show three things the matrix is designed to capture:

- Controls without evidence do not lower a score.
- Some treatments reduce impact rather than likelihood.
- A Critical asset does not automatically mean a Very High risk: the Azure outage scores High.

## 7. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the scales, financial thresholds and bands | Pending | |
| ISMS Steering Group | Reviews for consistency with the risk appetite | Pending | |
| Data Protection lead | Validates the data compromise and regulatory categories | Pending | |
| Information Security / GRC Analyst | Prepared the matrix | Prepared | |

## 8. Change log

| Version | Change |
| --- | --- |
| 1.0 (portfolio draft) | Illustrative 5×5 matrix; bands Low 1–4, Medium 5–9, High 10–16, Critical 17–25 |
| 0.1 | Numbered NSD-ISMS-013. Top band renamed from Critical to **Very High**, so it isn't confused with the asset "Critical" tier in NSD-ISMS-009. Score 16 (Likely × Major) moved from High to Very High, matching NSD-ISMS-012. Likelihood defined by probability, frequency and Northstar evidence over 12 months; control wording removed from the scale. Impact defined across six categories, with financial thresholds aligned to NSD-ISMS-009 and availability aligned to the 4-hour RTO. Added required responses per band, the Severe-impact reporting rule and three worked examples showing control credit. |

---

*Portfolio note: Thresholds are proposals for the simulated organisation and require management approval.*
