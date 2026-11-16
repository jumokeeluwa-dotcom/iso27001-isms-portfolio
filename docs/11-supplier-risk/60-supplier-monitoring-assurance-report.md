# Northstar Digital Solutions Ltd — Supplier Monitoring and Assurance Report, Q3 2027

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-060 |
| Version | 0.2 — Simulated report |
| Period | 1 July – 30 September 2027 |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 5.19–5.23; clauses 9.1, 9.3 |
| Status | **Simulated. Every statement is taken from earlier portfolio records. No supplier evidence has been reviewed, and nothing is shown as assured without a record** |
| Sources | [055 Register](55-supplier-register.md) · [058 Assessments](58-supplier-security-assessment-register.md) · [NSD-ISMS-044 Dashboard](../08-monitoring-and-measurement/44-performance-dashboard.md) · [NSD-ISMS-014](../03-risk-management/14-risk-register.md) · [NSD-ISMS-049 BIA](../10-business-continuity/49-business-impact-analysis.md) |
| Prepared by | Information Security / GRC Analyst |
| For | ISMS Steering Group, October 2027; summary to the next management review (input 9.3.2(c)) |
| Classification | Confidential |

---

## 1. Summary

**Northstar cannot currently show assurance over any of its seven Critical suppliers.**

The supplier register built this quarter found 7 Critical suppliers (one provisional), against 5 in the Q2 KPI. No assessment records for any of them are in the portfolio. The Q2 figure of "4 of 5 assessed" cannot be traced to evidence, and missing records are not counted as success.

Three matters need decisions this month: the **assessment plan and the time it needs**, **interim restriction of the IT support provider's access**, and **confirmation of sub-processors** that may be processing customer data without customers having been told.

## 2. Monitoring summary

| Area | Status | Basis |
| --- | --- | --- |
| Critical supplier assessments (KPI-14) | 🟥 **0 of 7 with a record** | 058 §2. Q2 reported 80% (4 of 5); no records found |
| Assurance evidence: certificates and reports | 🟥 **None on file** | 058 §2 |
| Supplier register completeness | 🟨 Register built this quarter | 055: 16 suppliers; 8 added that were already in use; CRM missing from the asset register |
| Sub-processors notified to customers | ⬜ **Unknown: possible nonconformity** | 055 gap 4: five suppliers to confirm |
| Supplier access (guest accounts) | 🟨 Amber | KPI-15, August: 3 guest accounts without expiry. MSP administrator roles not recorded |
| Supplier incidents | ⬜ **No record** | No supplier incident recorded in the period. Without a log of supplier notices, "none recorded" cannot be read as "none occurred" |
| Contract clauses (026 §4) | ⬜ Not reviewed | SoA 5.20: contract clauses not yet reviewed |
| Supplier continuity compared with the BIA | 🟥 Gap | Microsoft concentration (EXT-05); backups in the same region (BIA gap G2) |
| Supplier findings and corrective actions | — | None raised yet: no assessments have been completed |

⬜ means there is no evidence either way. It is shown separately so that it is not mistaken for Green.

## 3. Risks requiring attention

| Risk | Rating (NSD-ISMS-014) | Supplier position this quarter |
| --- | --- | --- |
| **R-16** Compromised supplier account gives access to Northstar systems | 🟧 High (15); target Medium (8) | The MSP's (SUP-04) administrator roles are not recorded; supplier due diligence is untested; 3 guest accounts had no expiry |
| **R-02** EU data processed or transferred unlawfully | 🟧 High (12); target Low (4) | Data and support locations unconfirmed for 15 of 16 suppliers |
| **R-09** Azure regional outage | 🟧 High (10); target Medium (6) | Two Critical services from one supplier; backups in the same region |
| **R-07** Compromised dependency or build tool | 🟧 High (15) | The CI/CD provider (SUP-09) is unassessed and deploys to production |
| *Proposed:* payroll provider discloses employee data | Not yet scored | Not covered by R-03 (058 §5). For the HR Manager to decide whether to raise a risk |

## 4. Actions

Actions already tracked elsewhere are referenced, not repeated. **New** actions are proposed for Steering Group approval.

| Action | Owner | Due | Tracked in |
| --- | --- | --- | --- |
| Find the Q2 KPI-14 records, or confirm they do not exist | Finance Manager | Overdue (14 Sep 2027) | NSD-ISMS-044 |
| Assess the seven Critical suppliers, in the 058 order | GRC Analyst | By 17 Dec 2027 | NSD-ISMS-058 §2 |
| **New:** confirm the MSP's administrator roles. Until assessed, give its engineers named accounts only, with privileged roles activated through PIM with approval, so that no standing admin access remains | IT Manager | 15 Oct 2027 | NSD-ISMS-015, under R-16 |
| **New:** confirm whether SUP-02, 07, 09, 10 and 14 process customer personal data. If any already does and is not on the customer-facing list, record a nonconformity and notify customers as their DPAs require | Data Protection lead | 29 Oct 2027 | NSD-ISMS-034 if confirmed |
| **New:** review Critical and High supplier contracts against the 026 §4 clauses, and DORA terms where relevant | Finance Manager | 31 Jan 2028 | NSD-ISMS-058 |
| Add the CRM to the asset register | Sales lead | 29 Oct 2027 | NSD-ISMS-006 |
| Set expiries on the 3 guest accounts | IT Manager | Overdue (from the August dashboard) | NSD-ISMS-044 |
| Supplier continuity: backups outside the source region | Head of Engineering / IT Manager | Risk review decision | BIA gap G2 |

The draft's owners "Procurement" and "Legal" are not charter roles. Contract work sits with the Finance Manager (owner of 026 and AST-015), and DPA and sub-processor work with the Data Protection lead.

## 5. Decisions requested

| # | Decision | Recommendation | Authority |
| --- | --- | --- | --- |
| 1 | Approve the assessment plan: seven Critical assessments by 17 Dec 2027 | Approve, **with time set aside.** Estimate (to be confirmed): about 3 days per Critical supplier, or about 20 days of GRC Analyst time this quarter. That competes with existing work: the capacity gap is a decision proposed for management review (D-04) | Steering Group |
| 2 | Interim restriction of the MSP's access until it is assessed | Approve. It reduces R-16 now, at little cost | Steering Group |
| 3 | Accept that KPI-14 is reset to the new count from Q3 | Accept. The Q3 result will be reported as 0 of 7 unless records are found, and **not compared like for like** with Q2 | Steering Group |
| 4 | Whether any supplier relationship should be restricted until assessed | Decide once the sub-processor confirmation is complete. If customer data reaches an unlisted sub-processor, that cannot be accepted as a risk (NSD-ISMS-016 §4) and must be corrected | MD |

## 6. Conclusion

Supplier security arrangements are now **designed:** register, methodology, questionnaire, assessment register and procedure (055–059). They are **not yet operating:** no supplier has an assessment record. The figures in this report are lower than the Q2 KPI suggested, because the portfolio now counts every Critical supplier and accepts only evidence on record. The next report (Q4 2027) will show whether the plan in section 4 has been carried out.

## 7. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-056) | Report template with every status "Pending" and illustrative actions |
| 0.2 | Numbered NSD-ISMS-060 and written as the **Q3 2027 report,** using only portfolio records. Statuses use Red, Amber, Green and ⬜ "no evidence", so a gap is not mistaken for Green; "no supplier incidents recorded" is not read as "none occurred". The draft's example concerns replaced by the actual position: 0 of 7 Critical suppliers with records, possibly unlisted sub-processors, unrecorded MSP admin roles. Risks linked to NSD-ISMS-014 ratings. Actions given charter owners and dates, with existing actions referenced rather than duplicated. "Management considerations" turned into four decisions with recommendations, including the time the plan needs. |

---

*Portfolio disclaimer: Simulated report. It does not represent an actual supplier assurance review or supplier approval.*
