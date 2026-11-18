# Northstar Digital Solutions Ltd — Statement of Applicability Methodology

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-018 |
| Version | 1.0 — Draft for approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clause 6.1.3(b)–(f); Annex A) |
| Related documents | [NSD-ISMS-003 Interested Parties](../01-initiation-and-context/03-interested-party-requirements-register.md) · [NSD-ISMS-004 Scope](../01-initiation-and-context/04-isms-scope-statement.md) · [NSD-ISMS-012 Risk Methodology](../03-risk-management/12-risk-assessment-methodology.md) · [NSD-ISMS-014 Risk Register](../03-risk-management/14-risk-register.md) · [NSD-ISMS-015 Treatment Plan](../03-risk-management/15-risk-treatment-plan.md) · [NSD-ISMS-016 Acceptance Criteria](../03-risk-management/16-risk-acceptance-criteria-register.md) · NSD-ISMS-019 Statement of Applicability (planned) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually, and on the triggers in section 9 |
| Classification | Internal |

---

## 1. Purpose

This methodology sets out how Northstar decides which information security controls it needs, records whether each is implemented, and keeps the Statement of Applicability (SoA, NSD-ISMS-019) accurate.

Clause 6.1.3(d) requires the SoA to contain:

- the necessary controls;
- the justification for including them;
- whether they are implemented;
- the justification for excluding any Annex A control.

**Key principles**

- **Annex A is a reference set, not a checklist.** Controls are determined from risk treatment and requirements first. Annex A is then used to check that nothing necessary has been missed (clause 6.1.3(b)–(c)).
- **Applicability and implementation are separate questions.** A control can be applicable but not yet implemented. Most of Northstar's controls are in that position today.
- **The SoA must agree with the risk register.** A control cannot be "Implemented" in the SoA while the same control earns no credit in NSD-ISMS-014.

## 2. Annex A at a glance

ISO/IEC 27001:2022 Annex A contains **93 controls** in four themes:

| Theme | Controls | Count |
| --- | --- | --- |
| Organisational | 5.1 – 5.37 | 37 |
| People | 6.1 – 6.8 | 8 |
| Physical | 7.1 – 7.14 | 14 |
| Technological | 8.1 – 8.34 | 34 |

Every one of the 93 appears in the SoA, either as applicable or as excluded with a justification.

## 3. Sources of control requirements

Each applicable control records at least one reason for inclusion, using these codes:

| Code | Reason | Source |
| --- | --- | --- |
| **RT** | Risk treatment | A treatment action in NSD-ISMS-015 (e.g. T-13.1 → 8.2) |
| **LR** | Legal or regulatory requirement | NSD-ISMS-003 §4; NSD-ISMS-005 legal register (planned) |
| **CO** | Contractual obligation | Customer contracts and DPAs (IP-01, IP-03); insurer (IP-13) |
| **BR** | Business requirement | Charter objectives (Obj 1–10); scope decisions (NSD-ISMS-004) |
| **IP** | Other interested-party requirement | NSD-ISMS-003, e.g. certification body (IP-14) |

A control with no reason code is not justified, and is either given a reason or excluded.

## 4. Applicability decisions

| Decision | Meaning | Requirement |
| --- | --- | --- |
| **Applicable** | The control is necessary for risk treatment or a requirement | At least one reason code, with references (R-xx, T-xx, IP-xx, Obj) |
| **Not applicable** | The control is not necessary within the scope | A specific justification, checked against the rules below |

**Rules for exclusion**

1. **Base it on scope, risk or requirements.** "Northstar does not perform this activity within the scope" is valid, provided NSD-ISMS-004 supports it.
2. **Cost, effort or lack of time are never valid.** An expensive necessary control is applicable, then treated or its risk accepted under NSD-ISMS-016.
3. **"The supplier does it" is not an exclusion.** If a supplier operates the control, it stays applicable, and the SoA records how Northstar gains assurance (5.19–5.23). For example, Microsoft's datacentre physical security sits outside the scope boundary (NSD-ISMS-004 §10), but it is assured through 5.23. It does not justify excluding the physical controls for Northstar's own office.
4. **Check for contradictions.** An exclusion must not conflict with a risk, a treatment action, a requirement or another document. For example, 8.25–8.31 (secure development) cannot be excluded, because Northstar develops its own SaaS platform (INT-05, R-05, R-07).
5. **Partial applicability is recorded as applicable, with its limits stated.** For example: "Applicable to the UK head office only; there are no other Northstar premises."

## 5. Implementation status

Statuses follow the control credit rule in NSD-ISMS-012 §5, so the SoA and the risk register use the same evidence standard:

| SoA status | Meaning | Risk register equivalent |
| --- | --- | --- |
| **Implemented** | Operating, with test evidence from the last 12 months | E: Effective, full credit |
| **Partially implemented** | Operating, but gaps or exceptions were found | P: Partially effective, partial credit |
| **Planned** | Not yet in place; a dated treatment action (NSD-ISMS-015) or charter milestone exists | N: Not in place, with a T-xx or charter reference |
| **Not implemented** | Applicable, with no implementation and no approved plan | N: Not in place. **Must be escalated**, because an applicable control needs a plan or a risk acceptance |
| **To be assessed** | Said to exist, or status unknown; not yet tested | U: Untested, no credit |

A control is never marked **Implemented** on the strength of a policy, a statement or a screenshot older than 12 months.

## 6. Contents of the SoA

| Field | Description |
| --- | --- |
| Control | Annex A reference and title (e.g. 8.2 Privileged access rights) |
| Theme | Organisational, People, Physical or Technological |
| Applicable | Yes or No |
| Reason codes | RT, LR, CO, BR, IP |
| Justification | Why the control is needed, or why it is excluded |
| Linked risks and actions | R-xx (NSD-ISMS-014); T-xx (NSD-ISMS-015) |
| Implementation status | One of the five statuses in section 5 |
| Control owner | Role from NSD-ISMS-007 or charter §6. The control owner runs the control, which is not always the risk owner |
| Evidence reference | Location in the GRC evidence repository, and the evidence date |
| Last reviewed | Date |

**Additional controls.** Controls needed for Northstar but not in Annex A are listed in a separate section of the SoA with IDs **NSD-C-nn**. Examples are specific DORA contract terms for FS customers (IP-03) and SBOM verification (record AR-01). Clause 6.1.3(b) allows controls from any source.

## 7. Process

1. **Derive controls from risk treatment.** For each of the 36 actions in NSD-ISMS-015, record the Annex A control or controls it implements.
2. **Add controls from requirements.** Add controls needed for legal, contractual, business and interested-party requirements (section 3).
3. **Compare with Annex A.** Go through all 93 controls. For each one not yet selected, ask whether any risk or requirement needs it:
    - Yes: mark it applicable. If no risk covers it, raise a new risk scenario for the next assessment.
    - No: exclude it with a justification under the section 4 rules.
4. **Set implementation status** from evidence, using section 5. Control owners supply the evidence, and the GRC Analyst checks it.
5. **Run quality checks** (section 8).
6. **Approve.** The MD approves the SoA alongside the risk owners' approval of the treatment plan and residual risks (clause 6.1.3(f); NSD-ISMS-016).
7. **Publish a version.** The approved SoA version and date are written into the scope statement (NSD-ISMS-004 §3), as the certificate wording refers to it.

## 8. Quality checks

Before approval, the GRC Analyst confirms:

- [ ] All 93 Annex A controls appear in the SoA
- [ ] Every treatment action (T-xx) maps to at least one applicable control
- [ ] Every applicable control has at least one reason code and reference
- [ ] No exclusion is based on cost, effort or supplier responsibility
- [ ] Exclusions are consistent with the scope boundaries (NSD-ISMS-004 §10)
- [ ] Every "Implemented" status has evidence less than 12 months old
- [ ] SoA statuses match the control statuses in NSD-ISMS-014
- [ ] Every "Not implemented" control has been escalated for a treatment plan or a risk acceptance
- [ ] Every applicable control has an owner

## 9. Review and maintenance

The SoA is reviewed:

- at least annually, after the annual risk assessment;
- after each re-score of a risk in NSD-ISMS-014;
- after material changes to risks, systems, suppliers, locations, legal obligations or the scope;
- when a treatment action is verified, so the status moves to Implemented;
- before each certification audit.

Every change is versioned. A new version is approved by the MD when any applicability decision changes. Status-only updates are approved by the GRC Analyst and reported to the Steering Group.

## 10. Classification and sharing

The full SoA is **Confidential**: its implementation statuses show where Northstar's controls are incomplete.

Customers and prospects often ask for it (IP-01, IP-02). It is shared externally only under NDA, with the owner's approval (NSD-ISMS-008 §4). An approved summary showing applicability without detailed statuses can be shared more widely.

## 11. Roles

| Role | Responsibility |
| --- | --- |
| Managing Director | Approves this methodology and each SoA version that changes applicability |
| Control owners | Operate controls and supply evidence |
| Risk owners | Approve treatment and residual risk (NSD-ISMS-016) |
| Information Security / GRC Analyst | Coordinates the SoA, checks evidence, runs quality checks, maintains versions |
| Internal auditor | Samples SoA statuses against evidence during internal audit (clause 9.2) |

## 12. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the methodology | Pending | |
| ISMS Steering Group | Reviews the methodology | Pending | |
| Information Security / GRC Analyst | Prepared the methodology | Prepared | |

---

*Portfolio note: This is a fictional draft methodology, not an approved company procedure.*
