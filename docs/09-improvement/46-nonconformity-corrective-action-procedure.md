# Northstar Digital Solutions Ltd — Nonconformity and Corrective Action Procedure

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-046 |
| Version | 0.2 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clause 10.2) |
| Related documents | [NSD-ISMS-034 Corrective Action Register](../06-internal-audit/34-corrective-action-register.md) · [NSD-ISMS-045 Continual Improvement](45-continual-improvement-procedure.md) · NSD-ISMS-048 Root Cause Analysis Report · [NSD-ISMS-030 Audit Programme](../06-internal-audit/30-internal-audit-programme.md) §8 |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually |
| Classification | Internal |

---

## 1. Purpose

This procedure defines how Northstar identifies, records and corrects nonconformities, removes their causes, and checks that the actions worked. It distinguishes three things that are often confused:

| Term | Meaning | Example: a leaver disabled 2 days late (AUD03-F01) |
| --- | --- | --- |
| **Correction** | Fix the immediate problem and deal with its consequences | Disable the account; check the sign-in logs for use |
| **Corrective action** | Remove the **cause**, so it does not recur here or elsewhere | Make the contract end date mandatory at contractor onboarding, so the automated removal always has its trigger |
| **Effectiveness verification** | Check that the corrective action achieved its intended result | Re-test **all** leavers in the following period: 100% disabled on time |

A correction without a corrective action means the problem will come back. A corrective action without verification is an assumption.

## 2. Scope

The procedure covers nonconformities from any source:

- internal and external audits;
- KPI monitoring, where a result shows a requirement is not met (NSD-ISMS-041 §9);
- security incidents and their lessons learned;
- risk reviews;
- management reviews;
- supplier assessments;
- complaints;
- self-identified gaps, such as an applicable SoA control with no plan.

## 3. What a nonconformity is

A **nonconformity** is a requirement that is not fulfilled. Requirements come from:

- ISO/IEC 27001;
- approved Northstar policies and procedures;
- legal and regulatory obligations;
- contracts and DPAs.

**Not every weakness is a nonconformity.** Before classifying anything as one, the assessor must name the specific requirement and the objective evidence that it was not met. A weakness where the requirement **was** met is an observation or improvement, and goes to NSD-ISMS-045.

**Grading.** Nonconformities are graded **Major** or **Minor** using the definitions in NSD-ISMS-030 §8, whatever their source, so that deadlines apply consistently.

## 4. Clause 10.2 requirements

| Clause 10.2 | What Northstar does | Recorded in NSD-ISMS-034 as |
| --- | --- | --- |
| (a) React: (1) control and correct it; (2) deal with the consequences | Immediate correction and containment. Where data or customers may be affected, the incident process applies (NSD-ISMS-027) | Correction; Consequences |
| (b) Evaluate the need to remove the cause: (1) review it; (2) find the cause; (3) check whether similar nonconformities exist or could occur | Root cause analysis (section 5) and an extent check (section 6) | Root cause; Extent check |
| (c) Implement the action needed | Corrective actions **appropriate to the effects** of the nonconformity: proportionate, not excessive | Corrective actions |
| (d) Review the effectiveness of the action | Verification against a defined success measure (section 8) | Effectiveness test |
| (e) Make changes to the ISMS, if necessary | Update policies, procedures, controls or the SoA. Plan the change under clause 6.3 (NSD-ISMS-045 §7) | ISMS changes |
| Documented information on the nature of the nonconformity, the actions taken and the results | The whole record in NSD-ISMS-034, with evidence references | — |

**Good practice beyond clause 10.2.** The affected risks in NSD-ISMS-014 are re-scored, and SoA statuses and KPIs are checked for consistency (clauses 6.1, 8.2 and 9.1).

## 5. Root cause analysis

1. **Use a method suited to the problem:**
    - 5 Whys for a single clear chain of events;
    - fishbone (Ishikawa) diagrams for several possible causes across people, process, technology and governance;
    - process mapping for hand-off failures;
    - trend analysis for repeated problems.
2. **Support every step with evidence.** Possible causes are hypotheses until evidence confirms them.
3. **Never stop at "human error" or "staff forgot".** Ask what allowed the error. Was there no trigger, no check, no automation, no training, or an unclear owner? For example, in AUD03-F02, "the HR Manager thought a verbal review was enough" became **"the process relied on memory, with no recorded workflow."**
4. **The owner leads the analysis,** supported by the GRC Analyst. The auditor does not write the root cause, which keeps their verification independent.
5. A full **root cause analysis report** (NSD-ISMS-048) is required for **Major nonconformities, repeat nonconformities, and corrective actions that failed verification.** For Minors, the RCA is recorded in the NSD-ISMS-034 entry.

## 6. Extent check

The owner checks whether the same cause could be affecting other places: other systems, teams, accounts, suppliers or processes. **The result is recorded even when nothing is found**, together with what was checked. Similar nonconformities found are added to the same record, or raised as new records with cross-references.

## 7. Timescales

| Grade | Correction | Corrective action plan | Closure, including effectiveness verification |
| --- | --- | --- | --- |
| **Major** | Immediately | Within **10 working days** | Within 90 days, and **before Stage 2** or the next certification audit |
| **Minor** | Within 5 working days | Within **20 working days** | Within **90 days**, or the next practical verification point |

These match NSD-ISMS-030 §8. Where the verification needs a longer observation period (section 8), the record shows "action verified; effectiveness pending", with the date it will be checked.

## 8. Effectiveness verification

**Who verifies:** never the owner.

- Audit nonconformities: the **lead auditor**.
- Other sources: the **GRC Analyst**.
- Where the GRC Analyst owns the action: the **internal auditor**.

**How long to observe:** long enough for the problem to have recurred if the fix did not work.

| How often the control runs | Observation period |
| --- | --- |
| Per event, such as leavers or deployments | At least one period containing events; the whole population is re-tested |
| Daily or weekly | At least 1 month |
| Monthly | 2 to 3 cycles |
| Quarterly or annually | The next occurrence, or a simulated test |

**The verifier confirms that:**

1. the action was implemented, with evidence;
2. the **root cause** was addressed, not just the symptom;
3. the extent check was completed and similar cases dealt with;
4. evidence shows the **intended outcome:** the success measure was met;
5. the problem has **not recurred** during the observation period.

**If verification fails,** the record is **reopened**. A new root cause analysis report (NSD-ISMS-048) is required, because the first analysis was wrong or incomplete.

## 9. Closure and escalation

- A record closes only when all five verification checks are met.
- **Overdue:** reported to the Steering Group; escalated to the MD after 30 days.
- **Repeat nonconformity** (the same root cause within 12 months): reported to the Steering Group. The grade is reconsidered, because a repeat Minor suggests a systemic problem and may become a Major.
- **Significant nonconformities** (Major, legal or contractual, or affecting a Very High risk): reported to the MD within 2 working days.
- The status of all corrective actions is input 9.3.2(d)(1) to management review.

## 10. Responsibilities

| Role | Responsibility |
| --- | --- |
| All staff | Report actual or suspected nonconformities; cooperate with investigations |
| Process and control owners | Correct; lead the root cause analysis and extent check; deliver the corrective actions; provide evidence |
| Information Security / GRC Analyst | Records and tracks; supports the analysis; verifies non-audit actions, except its own; maintains NSD-ISMS-034 |
| Lead auditor / internal auditor | Verifies audit nonconformities and GRC-owned actions |
| ISMS Steering Group | Monitors progress; handles repeat and overdue items |
| Managing Director | Provides resources; decides on significant nonconformities; reviews trends at management review |

## 11. Documented information

The register (NSD-ISMS-034), the evidence, root cause analyses, RCA reports (NSD-ISMS-048), extent checks, implementation evidence and verification results are kept for **3 years after closure**, classified Confidential.

## 12. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-042) | First draft |
| 0.2 | Numbered NSD-ISMS-046. Approver changed to the MD. Added a correction / corrective action / verification table with a Northstar example. The draft's clause 10.2 (a)–(e) list is kept and mapped to NSD-ISMS-034 fields; this also **exposed an error in NSD-ISMS-034 v0.2,** which had added an ISO 9001 item as 10.2(e), corrected in v0.3. Added "appropriate to the effects", grading for all sources, the rule that the owner (not the auditor) writes the root cause, an RCA report trigger, a recorded extent check even when nothing is found, timescales, observation periods by control frequency, independent verifiers, reopening on failure, and escalation for repeat and significant nonconformities. The draft's "never stop at human error" rule is kept with an example. |

---

*Portfolio disclaimer: Simulated procedure only. Actual organisational approval and implementation have not been demonstrated.*
