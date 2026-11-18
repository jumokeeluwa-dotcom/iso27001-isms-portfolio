# Northstar Digital Solutions Ltd — Corrective Action Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-034 |
| Version | 1.0 — Simulated records |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clause 10.2) |
| Related documents | [NSD-ISMS-033 Findings Register](33-audit-findings-register.md) · [NSD-ISMS-027 Incident Management](../05-policies/27-incident-management-policy.md) · [NSD-ISMS-014 Risk Register](../03-risk-management/14-risk-register.md) · [NSD-ISMS-030 Audit Programme](30-internal-audit-programme.md) |
| Register owner | Information Security / GRC Analyst (maintains records; verifies actions it does not own) |
| Verifier | The lead auditor for audit-sourced actions. The GRC Analyst for other sources, unless the GRC Analyst owns an action, in which case the internal auditor verifies |
| Classification | Confidential |

---

> **All records below are fictional examples.** No actions are represented as completed. Root cause analyses are illustrative examples of what an owner would produce, and dates follow the NSD-ISMS-030 deadlines.

## 1. Scope

The register holds **every nonconformity from any source** and its corrective action:

- internal audit findings (NSD-ISMS-033);
- external audit findings;
- security incidents and their lessons learned (NSD-ISMS-027 §10);
- management review decisions;
- customer complaints;
- self-identified gaps, such as an SoA control marked "Not implemented".

**Observations and opportunities for improvement are not nonconformities.** Actions taken on them are improvement actions (IMP-nn), tracked in NSD-ISMS-047. Clause 10.2 does not require them.

## 2. Register

| Action | Source | Type | Corrective action (summary) | Accountable owner | Actions due | Effectiveness check by | Verifier | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| CA-01 | AUD03-F01 | Minor NC | Contract end date made mandatory at contractor onboarding; current contractors backfilled; weekly check for accounts past their end date | HR Manager | 31 Aug 2027 | 28 Sep 2027 | Lead auditor | Plan agreed (simulated) |
| CA-02 | AUD03-F02 | Minor NC | Restricted asset reviews moved into Entra ID Access Reviews (system reminders, recorded decisions, automatic removal); asset owners briefed | HR Manager | 31 Aug 2027 | 28 Sep 2027 | Lead auditor | Plan agreed (simulated) |
| CA-03 | INC-2027-014 | Incident: policy breach | Block customer and Restricted data to personal email; block automatic external forwarding; targeted training | IT Manager | 30 Jul 2027 | 31 Aug 2027 | Internal auditor (the GRC Analyst owns part of the action) | Plan agreed (simulated) |

## 3. Clause 10.2 requirements and where they are recorded

| Clause 10.2 requirement | Field in each record |
| --- | --- |
| (a) React: control and correct it, deal with the consequences | Correction; Consequences |
| (b) Evaluate the need to remove the cause: review it, find the cause, check whether similar nonconformities exist or could occur | Root cause; Extent check |
| (c) Implement the action needed | Corrective actions |
| (d) Review the effectiveness of the action | Effectiveness test |
| (e) Make changes to the ISMS if necessary | ISMS changes |
| *Good practice, not a 10.2 requirement:* update the affected risks (clauses 6.1, 8.2) | Risk update |
| Retain documented information on the nature of the nonconformity, the actions and the results | The whole record, plus evidence references |

## 4. Corrective action records

### CA-01 — Leaver account disabled late (AUD03-F01)

| Field | Entry |
| --- | --- |
| Nonconformity | 1 of 7 leavers (a contractor) was disabled 2 working days late, against NSD-ISMS-023 §9 and A 6.5 |
| Correction (a) | Account disabled on day 2. Verified by the auditor in the Entra ID log (WP-AUD03-04) |
| Consequences (a) | Sign-in logs for the 2 days show no use (WP-AUD03-05). No customer or regulator impact |
| Root cause (b): owner's analysis, using 5 Whys | 1. Why late? The automated removal (T-12.3) started 2 days late. 2. Why? The leaving date reached the HR system 2 days after the last day. 3. Why? Contractor end dates are managed by email between the hiring manager and HR. 4. Why? Contractor onboarding does not record a contract end date in the HR system. **Root cause:** the onboarding process does not capture the one data item the automation depends on |
| Extent check (b) | Check every active contractor record for a missing end date, and every guest account for a missing expiry. **Results to be recorded by the owner** |
| Corrective actions (c) | **CA-01.1** Make contract end date a mandatory field at contractor onboarding in the HR system. Owner: HR Manager. Due 31 Aug 2027. **CA-01.2** Backfill end dates for all current contractors. Owner: HR Manager. Due 13 Aug 2027. **CA-01.3** Weekly IT report of accounts belonging to contractors past their end date, disabled the same day. This is a detective backstop. Owner: IT Manager. Due 31 Aug 2027 |
| Effectiveness test (d) | The auditor re-tests **all** leavers from 1 to 24 September 2027 and every contractor record. Pass: 100% disabled by the end of the last working day; 100% of contractor records have an end date. **If there are no leavers in the window,** the check moves to the next AUD-03, and closure is recorded as "action verified; effectiveness pending" |
| Risk update (good practice) | R-12 likelihood is reviewed once the effectiveness test is passed. Control credit stays Partial until then (NSD-ISMS-014) |
| ISMS changes (e) | NSD-ISMS-023 §9 amended: "contractor accounts carry the contract end date from day one". The HR onboarding procedure updated |
| Evidence | HR system field configuration; backfill report; weekly report samples; re-test working papers |
| Closure | Pending. **On hold:** a second late contractor in August 2027 triggered RCA-01 (NSD-ISMS-048); the re-test waits for its result |

### CA-02 — Access review not recorded (AUD03-F02)

| Field | Entry |
| --- | --- |
| Nonconformity | The Q1 2027 access review for the HR SharePoint site (AST-002) was not recorded, against NSD-ISMS-023 §8, A 5.18 and clause 7.5 |
| Correction (a) | The HR Manager completes and records a review of the HR site by **16 July 2027**. The auditor checks it |
| Consequences (a) | The correcting review checks whether anyone holds access they shouldn't. Any inappropriate access found is removed and assessed as a possible incident |
| Root cause (b): owner's analysis | Review reminders are sent to the IT Manager, not the asset owner, and there is no template or system record. The HR Manager believed a verbal discussion was enough. **Root cause:** the process relies on email and memory rather than a recorded workflow, and owners have not been told that records are required |
| Extent check (b) | Check the most recent quarter's review records for all 5 Restricted assets. **Results to be recorded by the owner** |
| Corrective actions (c) | **CA-02.1** Move Restricted asset access reviews into **Entra ID Access Reviews**: reminders go to the asset owner, decisions are recorded, and denied access is removed automatically. Owner: IT Manager. Due 31 Aug 2027. **CA-02.2** Brief all asset owners on their recorded review duty (NSD-ISMS-007 §2). Owner: GRC Analyst. Due 31 Jul 2027 |
| Effectiveness test (d) | All 5 Restricted asset reviews for Q3 2027 completed in the system by **17 September 2027.** The auditor inspects them by 28 September 2027 |
| Risk update (good practice) | No score change for R-03. SoA 5.18 stays Partially implemented until the test is passed |
| ISMS changes (e) | NSD-ISMS-023 §8 names Entra ID Access Reviews as the review method |
| Closure | Pending |

### CA-03 — Customer data sent to a personal email account (incident INC-2027-014)

This illustrative incident is the Milestone 5 analyst challenge, handled under NSD-ISMS-027.

| Field | Entry |
| --- | --- |
| Nonconformity | An employee sent a spreadsheet of customer personal data (Restricted) to their personal Gmail account, against NSD-ISMS-024 §4.5 and NSD-ISMS-025 §3.8 |
| Correction (a) | Evidence captured; the employee deleted all copies under supervision and signed a statement; Gmail account security checked |
| Consequences (a) | The Data Protection lead completed a breach assessment within 24 hours. Affected customers were notified as Northstar is their processor (Article 33(2)). Each decision is recorded in the incident record (AST-017) |
| Root cause (b) | Three contributing causes: 1. **no technical control:** DLP not yet implemented (SoA 8.12 Planned); 2. **awareness gap:** training completion 70% against a 95% target; 3. **unclear approved route** for working from home with company data |
| Extent check (b) | Mail trace for sends to personal email domains over the previous 90 days. **Results to be recorded** |
| Corrective actions (c) | **CA-03.1** DLP rule blocking customer data and Restricted-labelled content to personal email domains, brought forward from T-19.2. Owner: IT Manager. Due 30 Jul 2027. **CA-03.2** Block automatic forwarding to external addresses. Owner: IT Manager. Due 16 Jul 2027. **CA-03.3** Team briefing and an all-staff "working from home securely" message; overdue policy acknowledgements chased. Owner: GRC Analyst with HR Manager. Due 30 Jul 2027 |
| Effectiveness test (d) | A test send of a Restricted file to a personal domain is blocked. 30 days of DLP logs reviewed. Policy acknowledgement at 95% or higher |
| Risk update (good practice) | **New risk R-21** added at the next risk review: a staff member sends customer data to a personal account by mistake |
| ISMS changes (e) | SoA 8.12 moves from Planned once the effectiveness test is passed. NSD-ISMS-024 §8 points to the approved remote access route |
| Closure | Pending |

## 5. Improvement actions (not clause 10.2)

Improvements are not tracked here. IMP-01 (from Observation AUD03-F03) is tracked in the [NSD-ISMS-047 Continual Improvement Register](../09-improvement/47-continual-improvement-register.md), so each item lives in one register.

## 6. Workflow

| Step | What happens | Who |
| --- | --- | --- |
| 1. React | Correct the issue and deal with its consequences straight away | Owner; incident team for incidents |
| 2. Find the root cause | Use 5 Whys or a similar method. **Possible causes are hypotheses until confirmed by evidence** | Owner |
| 3. Check the extent | Look for similar problems in other systems, teams and accounts. Record the result, even if none are found | Owner |
| 4. Plan and act | Specific, measurable actions with an owner, resources and dates. The plan is due within 20 working days for a Minor, 10 for a Major (NSD-ISMS-030 §8) | Owner; plan accepted by the verifier |
| 5. Test effectiveness | Test after enough operating time to show the fix works, **not just that it was done** | Verifier |
| 6. Update risks and the ISMS | Re-score affected risks; change policies, procedures or the SoA where needed | Risk owner; GRC Analyst |
| 7. Close | Close only when the effectiveness test is passed. **If the fix did not work, the record reopens with a new root cause** | Verifier |

## 7. Measures and escalation

| Measure | Target |
| --- | --- |
| Corrective action plans submitted on time | 100% |
| Corrective actions closed by their due date | 90% or higher (NSD-ISMS-030 §13) |
| Actions that work at the first effectiveness test | Tracked; reported at management review |
| Repeat nonconformities (same root cause within 12 months) | 0 |

Overdue items are reported at each Steering Group meeting. A Minor action more than 30 days overdue is escalated to the MD. Corrective action status is a required input to management review (clause 9.3).

---

*Portfolio note: All records are fictional examples. No actions are represented as completed.*
