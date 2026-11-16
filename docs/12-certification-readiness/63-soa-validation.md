# Northstar Digital Solutions Ltd — Statement of Applicability Validation

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-063 |
| Version | 0.3 — Simulated validation |
| Standard | ISO/IEC 27001:2022 incl. Amendment 1:2024, clause 6.1.3(b)–(d) |
| Subject | [NSD-ISMS-019 Statement of Applicability](../04-controls-and-soa/19-statement-of-applicability.md) **v0.3** |
| Status | **Simulated. Checks are performed against portfolio records only** |
| Evidence as at | 30 September 2027 |
| Inputs | [NSD-ISMS-018 SoA methodology](../04-controls-and-soa/18-soa-methodology.md) · [NSD-ISMS-014](../03-risk-management/14-risk-register.md) · [NSD-ISMS-015](../03-risk-management/15-risk-treatment-plan.md) · [NSD-ISMS-020 Risk–control mapping](../04-controls-and-soa/20-risk-control-mapping.md) · [NSD-ISMS-062 Readiness review](62-annex-a-control-readiness-review.md) §5 |
| Validator | Information Security / GRC Analyst (prepared the SoA, so the mock Stage 1 auditor re-performs a sample of these checks: NSD-ISMS-066) |
| Approver | Managing Director |
| Classification | Confidential |

---

## 1. What clause 6.1.3 requires

The SoA must contain the **necessary controls,** the **justification for including** them, **whether they are implemented,** and the **justification for excluding** any Annex A control (6.1.3(d)). The controls come from risk treatment first and are then **compared with Annex A,** so that none is overlooked (6.1.3(b)–(c)). Annex A is a cross-check, not a checklist.

## 2. Validation checklist

The draft's twelve checks are kept. Each one is now **performed** against SoA v0.3, rather than left as "Pending".

| # | Check | Evidence examined | Result | Finding |
| --- | --- | --- | --- | --- |
| 1 | Based on the **current** risk assessment and treatment plan? | 014 v0.3 (Dec 2026); 016 | 🟨 Partial | Based on the December 2026 assessment. Since then R-21 has been proposed but not added, and the acceptance criteria that make scores final are **not approved** (6.1.2(a)) |
| 2 | All 93 Annex A controls considered? | SoA §1, §5 | 🟥 Fail | 48 assessed; **45 in Wave 2, overdue since 29 Jan 2027** |
| 3 | Necessary controls included? | 015; 020; 018 §8 check | 🟩 Pass | Every treatment action maps to an applicable control (17 controls added in v0.1 for this reason). Additional controls beyond Annex A included (NSD-C-01, NSD-C-02) |
| 4 | Exclusions justified? | SoA §5 | ⬜ Not yet testable | No exclusions yet. Three candidates in Wave 2 (for example 7.6, if the office has no secure areas). Each needs a specific reason when decided |
| 5 | Legal, regulatory and contractual requirements considered? | 5.31; NSD-ISMS-005 | 🟥 Fail | **Legal register not written** (proposed action MRA-2027-02). Controls driven by contracts (SLAs, DORA terms) cannot be confirmed as complete |
| 6 | Supplier and customer arrangements considered? | NSD-C-02; 055–058 | 🟨 Partial | DORA terms included as NSD-C-02 (To be assessed); supplier contracts not yet reviewed |
| 7 | Implementation status accurate? | 062 §5; AUD-03; KPI dashboard; 034 | 🟥 Fail | Statuses date from Dec 2026 and were **not revalidated** after AUD-03, the KPI results or the corrective actions. Section 4: 4 status changes recommended, 3 confirmed |
| 8 | Control owners identified? | SoA owner column | 🟨 Partial | Every control has an owner, but **5 have two:** 5.1, 5.15, 5.17, 5.30, 6.3. That breaks the one-accountable-owner rule |
| 9 | Dependencies and shared responsibilities clear? | 5.23; 062 "Operated by" | 🟨 Partial | Shared controls identified in 062, but the SoA does not yet say which part Northstar operates and which part relies on supplier assurance (for example 8.13, 8.24) |
| 10 | Aligned with the treatment plan? | 015; 020 | 🟩 Pass | Control and action references reconcile. Late actions (T-14.3, T-18.1, T-09.2) are correctly not shown as implemented |
| 11 | Residual risks accepted by authorised management? | 016 §8 | 🟥 Fail | **No risk accepted;** interim tolerances for Very High risks await MD approval |
| 12 | Reviewed and approved? | SoA §7 | 🟥 Fail | Not approved; control owners have not confirmed statuses |

**Result: 2 Pass, 4 Partial, 5 Fail, 1 not yet testable.** The SoA's **method** is sound: it is risk-driven, uses two-value applicability and evidence-based statuses, and reconciles with the treatment plan. Its **content** is incomplete and out of date, and it is unapproved.

## 3. The draft's example entries

The draft built new example entries. Validation should test the SoA's **actual** entries, and the examples also conflicted with it in four ways:

| Draft entry | Problem | SoA v0.3 actually says |
| --- | --- | --- |
| "Proposed applicable" | Applicability takes only **Yes or No** (SoA §2.2). "Proposed" belongs to approval, not applicability | Applicable, pending approval |
| "Designed" as a status | Not one of the five statuses (018 §5). The SoA states implementation, not documentation | 5.9, 5.15, 5.23, 6.5, 8.13: **Partially implemented**; 5.19: To be assessed |
| 7.4 "physical hosting is supplier-operated" | **Wrong scope.** Microsoft's data centres are covered by 5.23 and supplier assurance. 7.4 applies to Northstar's own premises | Applicable, **head office only** (scope statement 004 §10) |
| 8.15 "To be determined / not assessed" | Already assessed | Partially implemented |

**The same eight controls, validated in the SoA:**

| Control | Justification specific? | Status supported by evidence? | Note |
| --- | --- | --- | --- |
| 5.9 | Yes | Yes: Partially implemented | Add the CRM (055 gap 3) |
| 5.15 | Yes | Yes | AUD-03 evidence to be referenced; two owners (check 8) |
| 5.19 | Yes (updated in v0.3) | Yes: To be assessed | No assessment records (058) |
| 5.23 | Yes | Yes | Shared-responsibility split to be stated (check 9) |
| 6.5 | Yes | Yes: Partially implemented | Reference AUD03-F01 and RCA-01 as open |
| 7.4 | Yes: head office only | Yes: To be assessed | On-site check still needed |
| 8.13 | Yes | Yes | Reference KPI-09 Red: backup jobs succeed, restores not proven |
| 8.15 | Yes | Partly: rests on Dec 2026 evidence | Re-test: logging is in AUD-04's scope, which has no record |

## 4. Status changes recommended

From the seven differences found in 062 §5. **Changes are recommended, not made:** the control owner confirms each one before it enters the SoA (018), and NSD-ISMS-014 is updated at the same time, because SoA statuses are taken from it.

| Control | v0.3 | Evidence | Recommendation | Owner to confirm |
| --- | --- | --- | --- | --- |
| 5.2 | Planned | Roles exercised in AUD-03 | **Partially implemented.** Owner acceptance (007 §6) still missing | MD |
| 5.3 | Planned | KPI-07: 42 of 42 deployments with second-person approval, validated (044) | **Partially implemented.** Payment and backup segregation untested | IT Manager |
| 5.25, 5.26 | To be assessed | INC-2027-014 triaged, assessed and handled (034 CA-03) | **Partially implemented** | GRC Analyst; IT Manager |
| 5.27 | Not implemented (escalated) | CA-03: root causes found and ISMS changes made after INC-2027-014 | **Partially implemented; end the escalation.** No structured lessons-learned review yet (027 §10) | GRC Analyst |
| 5.1 | Planned | KPI-20: 93% acknowledgement, but no approval record | **No change** until the conflict is resolved (061 gap 2) | MD |
| 8.12 | Planned | KPI-16: DLP blocking | **No change.** CA-03 says the status moves when its effectiveness test passes | IT Manager |
| 7.4 | To be assessed | Draft confused scope | **No change.** Scope confirmed: head office only | IT Manager |

**Owners:** the five controls with two owners each get one accountable owner. Proposed: 5.1 MD; 5.15 and 5.17 split by system (Head of Engineering for the platform, IT Manager for corporate IT), recorded as two lines rather than one shared owner; 5.30 Head of Engineering; 6.3 HR Manager.

**Effect if confirmed:** Partially implemented 23 → 28; Planned 11 → 9; To be assessed 13 → 11; Not implemented 1 → 0 (still 48 assessed).

## 5. Before the SoA can be approved

| Step | Who | Depends on |
| --- | --- | --- |
| Approve the risk acceptance criteria, so scores are final | MD | — |
| Add R-21 to the risk register and map its controls | GRC Analyst; risk owner | — |
| Complete Wave 2: 45 controls, with a specific reason for any exclusion | GRC Analyst; control owners | Legal register for legal and contractual controls |
| Confirm the section 4 changes and update 014 to match | Control owners | — |
| One owner per control | MD | — |
| Risk owners confirm residual risks; MD decides the interim tolerances | Risk owners; MD | Approved criteria |
| **Approve the SoA;** record its version and date in the scope statement (004 §3) | MD | All of the above |

The certification body will cite the approved SoA version on the certificate, so the version approved must be the one the audit examines.

## 6. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| Control owners | Confirm section 4 | Pending |
| Risk owners | Confirm residual risks | Pending |
| Managing Director | Approve the SoA | Pending |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-059) | Twelve validation checks, all "Pending"; eight example entries |
| 0.3 | Correction: 5.2 evidence no longer cites management review MR-2027-01, which is planned but unrecorded. |
| 0.2 | Numbered NSD-ISMS-063. **All twelve checks performed** against SoA v0.3, with evidence and results: 2 Pass, 4 Partial, 5 Fail, 1 not yet testable. The draft's example entries tested against the real SoA: "Proposed applicable" and "Designed" are not valid values; 7.4 had the wrong scope; 8.15 was already assessed. The seven differences from 062 resolved into 4 recommended status changes (including ending the 5.27 escalation) and 3 confirmed as unchanged, each needing owner confirmation and a matching update to 014. Five joint owners found. Steps to approval listed. |

---

*Portfolio disclaimer: Simulated validation. It is not an approved SoA, and no real control evidence has been examined.*
