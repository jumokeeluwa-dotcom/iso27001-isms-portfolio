# Northstar Digital Solutions Ltd — Third-Party Security Review Procedure

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-059 |
| Version | 0.2 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 5.19–5.23, 5.24, 5.26 |
| Parent policy | [NSD-ISMS-026 Supplier Security Policy](../05-policies/26-supplier-security-policy.md) |
| Related documents | [055 Register](55-supplier-register.md) · [056 Methodology](56-supplier-risk-assessment-methodology.md) · [057 Questionnaire](57-supplier-due-diligence-questionnaire.md) · [058 Assessments](58-supplier-security-assessment-register.md) · [NSD-ISMS-027 Incident Management](../05-policies/27-incident-management-policy.md) · [NSD-ISMS-023 §10](../05-policies/23-access-control-policy.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review | Annually, and after any supplier incident affecting Northstar |
| Classification | Internal |

---

## 1. Purpose and scope

This procedure covers what happens **after** a supplier is onboarded: continuous monitoring, scheduled reviews, supplier incidents, changes and exit. Onboarding assessment is covered by NSD-ISMS-056.

It applies to every supplier in NSD-ISMS-055, including cloud providers, managed service providers, contractor agencies and sub-processors.

## 2. Responsibilities

| Role | Responsibility |
| --- | --- |
| **Business owner** (one per supplier, NSD-ISMS-055) | Confirms service needs; tells the GRC Analyst about changes and concerns **within 10 working days**; evaluates service performance; leads exit |
| **Information Security / GRC Analyst** | Keeps 055 and 058; runs reviews; checks assurance evidence; tracks findings; escalates. **Does not accept risk** |
| **Finance Manager** | Owner of NSD-ISMS-026, KPI-14 and R-16; contracts and renewals (AST-015); the paid-supplier list used for reconciliation |
| **IT Manager** | Technical review of corporate IT suppliers; supplier guest accounts and their monitoring (NSD-ISMS-023 §10) |
| **Head of Engineering** | Technical review of platform and development suppliers (SUP-01, SUP-09) |
| **Data Protection lead** | DPAs; sub-processor list and customer notices (026 §5); transfer mechanisms |
| **Managing Director** | Decisions under NSD-ISMS-056 §8; approves exit of a Critical supplier |

"Procurement Manager" and "Security Lead" in the draft are not charter roles; their duties are shared as above.

## 3. Continuous monitoring

Between scheduled reviews, these signals are checked, so problems are found when they happen rather than at the next annual review.

| Signal | Check | Who | Frequency |
| --- | --- | --- | --- |
| Certificate or report expiry | Expiry dates tracked; new evidence requested **60 days before** expiry | GRC Analyst | Monthly |
| Supplier accounts in Northstar systems | Guest accounts: MFA on, within the 90-day expiry, owned by a registered supplier (R-16) | IT Manager | Quarterly reconciliation; sign-in alerts continuous |
| Unregistered suppliers | Finance's paid-supplier list compared with NSD-ISMS-055 | GRC Analyst, with the Finance Manager | Quarterly |
| Service performance | Outages and SLA reports for Critical suppliers, compared with BIA needs | Business owner | Monthly |
| Sub-processor change notices | Received, recorded and passed to the Data Protection lead **on the day** | Business owner | As received |
| Adverse news | Breaches, enforcement, acquisitions involving Critical suppliers | GRC Analyst | Monthly |

## 4. Scheduled reviews

Frequencies are set by **NSD-ISMS-026 §3,** not by this procedure. The draft proposed different intervals, including an annual review for High suppliers and Medium and Low tiers that the policy does not have. Two documents with different schedules would make one of them wrong.

| Tier | Full review |
| --- | --- |
| Critical | Annually |
| High | Every 2 years |
| Standard | At renewal |

Event-driven reassessment follows NSD-ISMS-056 §9.

**A scheduled review covers:**

1. Assurance evidence renewed and checked: scope, period, exceptions (056 §4).
2. Findings and conditions from the last assessment: closed with evidence?
3. Access: is it still needed, and still the minimum?
4. Data and locations: any changes; sub-processors current and notified to customers.
5. Incidents and performance since the last review.
6. Contract: the 026 §4 clauses present; renewal date; DORA terms where relevant.
7. Continuity: does the supplier's RTO still meet the BIA and NSD-ISMS-052?
8. Tier still correct (NSD-ISMS-056 §3).

The result is recorded in NSD-ISMS-058 and the review date in NSD-ISMS-055.

## 5. Supplier incidents

A supplier incident is handled under NSD-ISMS-027, with these supplier-specific steps.

| Step | Action | Time |
| --- | --- | --- |
| 1 | Record **when the supplier became aware and when it told Northstar.** Notice later than 24 hours is a contract issue and is recorded as a finding | On receipt |
| 2 | Report through the security channel. Northstar's **own** clock starts here: as a processor, Northstar must notify affected customers without undue delay (027 §8) | Immediately |
| 3 | Triage: which Northstar data, systems and customers are affected? | 027 §5 timescales |
| 4 | Contain on Northstar's side: disable the supplier's accounts; rotate any secrets the supplier held (for example, pipeline secrets with SUP-09) | As triage decides |
| 5 | Breach assessment if personal data may be affected | Within 24 hours (027 §8) |
| 6 | Obtain the supplier's root cause and remediation, and check that they are complete | Within 10 working days of closure |
| 7 | Reassess the supplier (056 §9) and update the related risks | Within 10 working days of closure |

## 6. Supplier changes

| Change | Action | Before it takes effect? |
| --- | --- | --- |
| New sub-processor for customer data | Data Protection lead notifies customers, or obtains their approval, as each DPA requires (026 §5) | **Yes:** the sub-processor must not process customer data first |
| New data location or transfer outside the UK or EU | Transfer mechanism confirmed (R-02) | Yes |
| New or wider access to Northstar systems | Approved under NSD-ISMS-023 §10; tier reviewed | Yes |
| Change of ownership, merger or acquisition | Reassessment | Within 20 working days (056 §9) |
| Change to service or security arrangements | Reassessment proportionate to the change | Yes, where it affects data, access or resilience |

## 7. Exit

| Step | Evidence | Time |
| --- | --- | --- |
| Remove all supplier access and accounts | Entra ID and system records | **On the last day** (026 §11) |
| Rotate secrets and keys the supplier knew or held | Rotation log | On the last day |
| Remove integrations and API connections | Configuration record | On the last day |
| Return or delete Northstar data | **Written confirmation** from the supplier | Within the contract period |
| Remove from the customer-facing sub-processor list, if listed | Updated list | At exit |
| Update NSD-ISMS-055 (status Exited) and the asset register | Register entries | Within 5 working days |
| Exit of a Critical supplier: transition completed without loss of service or data | Transition record; MD approval | As planned |

Contractor agencies (SUP-15) follow the same steps for each contractor, together with the leaver controls examined in RCA-01 (NSD-ISMS-048).

## 8. Measures

| Measure | Target |
| --- | --- |
| Critical suppliers assessed in the last 12 months (KPI-14) | 100% |
| Supplier incidents notified to Northstar within 24 hours | 100% |
| Sub-processors notified to customers before processing | 100% |
| Exits with written deletion confirmation | 100% |
| Guest accounts linked to a registered supplier and within expiry | 100% |

## 9. Records

Assessments, reviews, assurance documents, contracts, incident records and exit evidence are kept for **3 years after the relationship ends,** or longer where the contract requires it. They are classified Confidential.

## 10. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-055) | Review procedure with responsibilities, frequencies, incidents, changes and exit |
| 0.2 | Numbered NSD-ISMS-059. One owner (the GRC Analyst); approver changed to the MD. Responsibilities mapped to charter roles: "Procurement Manager" duties to the Finance Manager and GRC Analyst, "Security Lead" duties to the IT Manager and Head of Engineering; Data Protection lead added. **Review frequencies taken from NSD-ISMS-026 §3,** instead of a second, different schedule. Added continuous monitoring signals, including guest account and paid-supplier reconciliations. Supplier incidents linked to NSD-ISMS-027, recording when the supplier became aware and starting Northstar's own processor clock. Changes: sub-processors and transfers approved **before** they take effect. Exit with timings, secret rotation and removal from the sub-processor list. Measures and retention added; "periodically" replaced with an annual review. |

---

*Portfolio disclaimer: Simulated draft only. It does not demonstrate actual supplier monitoring or approval.*
