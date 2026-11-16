# Northstar Digital Solutions Ltd — Information Asset Valuation Methodology

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-009 |
| Version | 0.1 — Draft for approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 6.1.2, 8.2; Annex A 5.9, 5.12, 5.30) |
| Related documents | [NSD-ISMS-006 Asset Register](06-information-asset-register.md) · [NSD-ISMS-007 Ownership](07-asset-ownership-register.md) · [NSD-ISMS-008 Classification](08-information-classification-scheme.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually, and whenever the risk acceptance criteria change |
| Classification | Internal |

---

## 1. Purpose

This methodology defines how each asset's confidentiality, integrity and availability (C, I, A) requirements are rated, and how those ratings combine into a criticality tier.

The results are used to:

- Set the classification. The confidentiality rating maps to the NSD-ISMS-008 levels.
- Rank assets for risk assessment. Ratings supply the impact values in the asset risk mapping (NSD-ISMS-010).
- Prioritise controls, monitoring and recovery, including business continuity targets (Obj 8).

Valuation measures how much an asset matters. It is not a risk assessment: it says nothing about likelihood or existing controls.

## 2. Rating scale

| Rating | Score | Meaning |
| --- | --- | --- |
| High (H) | 3 | Severe harm: regulatory breach, contract breach, serious customer impact or significant financial loss |
| Medium (M) | 2 | Significant but manageable harm, recoverable within normal management action |
| Low (L) | 1 | Minor harm, absorbed in day-to-day operations |

NSD-ISMS-006 records ratings as H, M or L. The scores are used only to explain the criticality rules.

## 3. Impact criteria

Rate each dimension by the **worst credible outcome** across the five impact areas. The highest area sets the rating.

| Impact area | High | Medium | Low |
| --- | --- | --- | --- |
| Legal and regulatory | Reportable personal data breach; regulatory action likely (ICO, EU authorities) | Non-compliance that needs correction but is not reportable | No legal effect |
| Customer and contractual | SLA breach or contract breach for multiple customers; customer could terminate | Single customer affected; service credits or a complaint | No customer notices |
| Financial (illustrative, for MD approval) | Over £100,000 | £10,000 – £100,000 | Under £10,000 |
| Operational | Platform or a core business process stops | Business process degraded, with a workaround | Minor inconvenience |
| Reputational | National or trade press coverage; loss of certification or tenders | Concern from several customers or partners | Contained internally |

The financial thresholds are placeholders sized for an 85-person SaaS company. They must match the risk acceptance criteria that the MD approves in project phase 2 (charter §7).

### 3.1 Questions for each dimension

| Dimension | Question | High if… | Medium if… | Low if… |
| --- | --- | --- | --- | --- |
| **Confidentiality** | What happens if the wrong people see it? | Matches NSD-ISMS-008 Restricted criteria | Matches Confidential criteria | Internal or Public |
| **Integrity** | What happens if it is changed without authorisation or detection? | Corrupts customer data, financial records or payments, legal commitments, or security evidence and controls (logs, keys, credentials, plans) | Disrupts a process or needs significant correction | Easily spotted and corrected |
| **Availability** | How long can Northstar operate without it? | Needed within **4 hours**: an outage stops the platform, breaches SLAs or prevents incident response | Tolerable for **4 hours to 2 working days** | Tolerable for **more than 2 working days** |

## 4. Rating rules

1. **Rate the inherent value.** Ignore existing controls: a well-protected asset can still be High value.
2. **Rate each dimension separately.** Do not average them.
3. **Confidentiality must match classification.** H = Restricted, M = Confidential, L = Internal or Public (NSD-ISMS-008 §3.2).
4. **Dependency rule.** A supporting asset is rated at least as high as the assets that depend on it. For example, Entra ID is High for availability because nobody, including administrators, can reach the platform without it.
5. **Aggregation.** Rate a collection by its combined impact, not by its single entries.
6. **Personal data.** The Data Protection lead confirms the confidentiality rating of any asset containing personal data.

## 5. Criticality tiers

Taking the highest rating as the overall value ranks nearly every important asset as High, so it cannot separate priorities. Criticality is set by **how many** dimensions are High:

| Tier | Rule | What it drives |
| --- | --- | --- |
| **Critical** | Two or three dimensions rated High | Assessed first in risk assessment; included in BC/DR recovery plans; continuous monitoring; valuation confirmed at every quarterly attestation |
| **High** | Exactly one dimension rated High | Risk-assessed in phase 2; access reviewed and monitored according to classification |
| **Medium** | Highest rating is Medium | Standard controls; valuation reviewed annually |
| **Low** | All dimensions Low | Baseline controls; valuation reviewed annually |

**Indicative recovery targets** by availability rating, to be confirmed through business impact analysis for the BC/DR plans (AST-019):

| Availability | Recovery time objective (RTO) | Recovery point objective (RPO) |
| --- | --- | --- |
| High | 4 hours or less | 1 hour or less |
| Medium | 2 working days or less | 24 hours or less |
| Low | 5 working days or less | 1 week or less |

## 6. Valuation of the 20 registered assets

Ratings are taken from NSD-ISMS-006 v0.2 and validated against the criteria in section 3.

| ID | Asset | C | I | A | Tier | Main reason for the highest ratings |
| --- | --- | --- | --- | --- | --- | --- |
| AST-001 | Customer platform data | H | H | H | Critical | Reportable breach; corrupted customer records; platform stops |
| AST-002 | Employee and contractor HR records | H | H | M | Critical | Personal and bank data; payroll and legal records |
| AST-006 | Encryption keys and application secrets | H | H | H | Critical | Platform compromise; platform cannot run without them |
| AST-007 | SaaS production environment | H | H | H | Critical | Holds AST-001; outage breaches SLAs |
| AST-008 | Microsoft 365 tenant | H | H | M | Critical | Holds Restricted HR and incident files (inheritance) |
| AST-009 | Identity directory (Entra ID) | H | H | H | Critical | Access to everything; dependency rule |
| AST-010 | Privileged and break-glass credentials | H | H | H | Critical | Full control; needed during incidents |
| AST-011 | Backups | H | H | H | Critical | Full copy of Restricted data; needed to recover |
| AST-016 | Vulnerability and penetration test reports | H | H | L | Critical | A guide for attackers; altering them could hide unfixed vulnerabilities |
| AST-017 | Incident and breach records | H | H | M | Critical | Breach evidence; supports 72-hour reporting |
| AST-019 | Business continuity and DR plans | M | H | H | Critical | Wrong steps during a disaster; needed when systems are down |
| AST-003 | Financial and billing records | M | H | M | High | Altered payments or billing |
| AST-004 | Source code repositories | M | H | M | High | Tampered code reaches customers; secrets held separately |
| AST-005 | CI/CD pipelines | M | H | M | High | A compromised pipeline can ship malicious code |
| AST-012 | Security event logs | M | H | M | High | Evidence must be trustworthy |
| AST-014 | Customer contracts and DPAs | M | H | L | High | Legal commitments |
| AST-015 | Supplier and sub-processor contracts | M | H | L | High | Legal commitments |
| AST-013 | Customer support records | M | M | M | Medium | Contact data; a support outage has a workaround |
| AST-018 | Technical and architecture documentation | M | M | L | Medium | Useful to attackers but not decisive |
| AST-020 | Company endpoints | M | M | M | Medium | No Restricted data stored locally (NSD-ISMS-008) |

**Result:** 11 Critical, 6 High, 3 Medium and 0 Low. The register so far holds only the 20 highest-value assets, so a top-heavy result is expected. The Medium and Low tiers will fill as the items in NSD-ISMS-006 §5 are added.

### 6.1 Differences from the 1.0 draft, and how they were resolved

| Asset | 1.0 draft | Resolved | Reason |
| --- | --- | --- | --- |
| Microsoft 365 | C2 I2 A3 | H H M | Holds Restricted files (inheritance rule). An email outage of under 2 working days has workarounds |
| Azure / production environment | C2 I3 A3 | H H H | Hosts customer platform data |
| Source code | C2 I3 A3 | M H M | Deployments can wait up to 2 working days; the live platform keeps running |
| Customer support records | C3 I2 A2 | M M M | Support tickets are Confidential under NSD-ISMS-008 §3.3 |
| Vulnerability reports | C3 I2 A2 | H H L | Altering a report could hide an unfixed vulnerability (integrity); the reports aren't needed urgently (availability) |
| Security policies, development docs, network diagrams | Rated | Removed or merged | Matches the NSD-ISMS-006 asset list |

## 7. Valuation process

1. The **GRC Analyst** prepares draft ratings using the criteria in section 3.
2. The **asset owner** reviews them with the custodian and challenges or confirms each rating.
3. The **Data Protection lead** confirms confidentiality ratings for personal data.
4. The **owner** approves, and the ratings are recorded in NSD-ISMS-006.
5. The **Steering Group** reviews the tier distribution and any disputed ratings.

## 8. Review

| Trigger | Action |
| --- | --- |
| Quarterly ownership attestation (NSD-ISMS-007) | Owners confirm valuations of Critical assets |
| Annual review | All valuations confirmed |
| Material change to the asset, its data, its process or its supporting technology | Revalue before the change goes live |
| Change to the risk acceptance criteria or financial thresholds | Recheck all ratings |
| Security incident involving the asset | Revalue as part of lessons learned |

## 9. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the method and financial thresholds | Pending | |
| Data Protection lead | Validates personal data ratings | Pending | |
| Asset owners | Confirm the valuation of their assets | Pending | |
| Information Security / GRC Analyst | Prepared the methodology | Prepared | |

## 10. Change log

| Version | Change |
| --- | --- |
| 1.0 (portfolio draft) | First draft: 1–3 scale; criticality equal to the highest rating |
| 0.1 | Renumbered from NSD-ISMS-008 to NSD-ISMS-009, since 008 is the classification standard. Aligned the scale with the H/M/L ratings in NSD-ISMS-006. Added impact criteria across five impact areas, with illustrative financial thresholds. Added time-based availability bands and indicative RTO/RPO targets. Linked confidentiality to the NSD-ISMS-008 classification. Added rules for inherent value, dependencies and aggregation. Replaced "highest rating" criticality with tiers based on the number of High ratings. Revalued all 20 assets using the NSD-ISMS-006 list and recorded the differences from the draft. Added the valuation process and review triggers. |

---

*Portfolio note: Ratings and thresholds are illustrative. A real implementation would validate them through business impact discussions and the risk assessment.*
