# Northstar Digital Solutions Ltd — Information Asset Management, Review and Approval Procedure

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-011 |
| Version | 0.1 — Draft for approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 7.5, 9.1, 10.2; Annex A 5.9–5.14, 5.18, 7.10, 7.14, 8.10) |
| Related documents | [NSD-ISMS-006 Asset Register](06-information-asset-register.md) · [NSD-ISMS-007 Ownership](07-asset-ownership-register.md) · [NSD-ISMS-008 Classification](08-information-classification-scheme.md) · [NSD-ISMS-009 Valuation](09-asset-valuation-methodology.md) · [NSD-ISMS-010 Risk Mapping](10-asset-risk-mapping.md) |
| Process owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually, and after significant organisational or technology change |
| Classification | Internal |

---

## 1. Purpose

This procedure defines how information assets are managed from identification to disposal. It covers who approves each change and how assets are reviewed.

It is the operating procedure for the other five asset documents:

| Document | What this procedure does with it |
| --- | --- |
| NSD-ISMS-006 Asset Register | Keeps it complete and accurate |
| NSD-ISMS-007 Ownership Register | Runs acceptance, transfers and attestations |
| NSD-ISMS-008 Classification Standard | Applies it when assets are registered or changed |
| NSD-ISMS-009 Valuation Methodology | Applies it when assets are registered or changed |
| NSD-ISMS-010 Risk Mapping | Updates scenarios when assets change |

**Process owner.** The GRC Analyst owns this procedure, not the IT Manager. The IT Manager owns 5 assets, 4 of them Restricted (NSD-ISMS-007 §4), so owning the process that reviews them would create a segregation-of-duties conflict. The IT Manager remains a key participant, responsible for technical discovery and custodian evidence.

## 2. Roles and responsibilities

**R** = responsible, **A** = accountable, **C** = consulted, **I** = informed.

| Activity | Asset owner | Custodian | GRC Analyst | IT Manager | Data Protection lead | Steering Group / MD |
| --- | --- | --- | --- | --- | --- | --- |
| Identify new assets | R | R | C | R (technical discovery) | I | I |
| Register asset | C | C | R, A | I | I | I |
| Accept ownership | R, A | I | C | I | I | I |
| Classify and value | R, A | C | C | C | C (personal data) | I |
| Map risk scenarios | C | C | R, A | C | I | I |
| Apply protection | A | R | C | R | C | I |
| Periodic attestation | R, A | C | R (coordinate) | I | I | I (results) |
| Discovery reconciliation | I | C | R, A | R | I | I |
| Ownership transfer | R | I | R (record) | I | I | A |
| Retire and dispose | A | R | R (record) | C | C (retention) | I |
| Exceptions | R (request) | I | R (assess) | I | C | A (Restricted) |

## 3. Asset lifecycle

| Stage | What happens | Output | Rule set in |
| --- | --- | --- | --- |
| 1. Identify | Department managers, custodians and discovery sources find assets | Asset request | Section 6 |
| 2. Register | GRC Analyst adds the asset with an AST ID | Register entry | NSD-ISMS-006 |
| 3. Assign owner | Owner and deputy named and accepted | Acceptance record | NSD-ISMS-007 |
| 4. Classify | Owner applies the decision steps | Classification | NSD-ISMS-008 §3 |
| 5. Value | Owner rates C, I and A; tier assigned | Valuation | NSD-ISMS-009 |
| 6. Map risk | GRC Analyst adds or updates scenarios | ARM entries | NSD-ISMS-010 |
| 7. Protect | Custodian applies the handling rules and treatment controls | Control evidence | NSD-ISMS-008 §4; risk treatment plan |
| 8. Review | Owner attests on schedule | Attestation record | Section 5 |
| 9. Change | Approved through the workflows in section 4 | Change log entry | Section 4 |
| 10. Retire and dispose | Data retained or destroyed; asset marked Retired | Disposal record | Section 8 |

## 4. Approval workflows

| Event | Raised by | Approved by | Time limit | Recorded in |
| --- | --- | --- | --- | --- |
| New asset | Department manager, custodian, or a change or procurement request | Owner accepts; Data Protection lead confirms if personal data | Registered within 5 working days; owner accepted within 10 working days of identification | NSD-ISMS-006, 007 |
| New system, SaaS tool or supplier | Change or procurement request | Asset registered and classified **before go-live or contract signature** | Before go-live | NSD-ISMS-006 |
| Classification or valuation upgrade | Anyone | Owner confirms | Higher handling applies at once; owner confirms within 5 working days | NSD-ISMS-006 |
| Classification or valuation downgrade | Owner | Owner, plus the Data Protection lead for personal data | Before handling is relaxed | NSD-ISMS-006 |
| Ownership transfer | Current owner, or the HR leaver/mover process | New owner accepts; Steering Group approves | Before the current owner leaves the role | NSD-ISMS-007 §8 |
| Unowned asset | GRC Analyst | Steering Group assigns an owner; MD is interim owner | Escalated within 10 working days | NSD-ISMS-007 |
| Retirement and disposal | Owner or custodian | Owner; Data Protection lead confirms retention for personal data | Before data is destroyed | Disposal record; NSD-ISMS-006 |
| Exception to this procedure or NSD-ISMS-008 | Requester | Owner (Confidential); MD (Restricted) | Maximum 12 months | Exceptions log |

## 5. Periodic review and attestation

### 5.1 Schedule

| Review | Scope | Frequency |
| --- | --- | --- |
| Restricted and Critical-tier assets | Ownership, classification, valuation, access, risk scenarios | Quarterly |
| All other assets | Same checklist | Six-monthly |
| Full register | All assets, plus the tier distribution and unregistered items | Annually, before management review |
| Discovery reconciliation | Register compared with technical sources (section 6) | Quarterly |
| Out-of-cycle review | Affected assets | After a material change, an incident involving the asset, a role change or a leaver |

These frequencies match NSD-ISMS-006 §9, NSD-ISMS-007 §9 and NSD-ISMS-009 §8. If any of those documents changes, this table changes with it.

### 5.2 Attestation checklist

For each asset in review, the owner confirms:

- [ ] The asset still exists, with its correct status and location (including Azure region)
- [ ] The owner, deputy and custodian are still correct
- [ ] The classification is still correct under NSD-ISMS-008
- [ ] The C, I and A ratings and tier are still correct under NSD-ISMS-009
- [ ] Access has been reviewed: Restricted quarterly, others at each attestation
- [ ] Business use has not changed in a way that affects security
- [ ] The risk scenarios in NSD-ISMS-010 are still accurate
- [ ] There are no open exceptions past their expiry date

### 5.3 Steps and escalation

1. The GRC Analyst sends attestation packs to owners **10 working days** before the quarter ends.
2. Owners complete them within **10 working days**.
3. Not done after 5 working days: the GRC Analyst reminds the owner and copies the deputy.
4. Not done after 10 working days: reported as overdue to the Steering Group.
5. Not done after 20 working days: escalated to the MD and recorded as a nonconformity (clause 10.2).
6. Changes found during attestation go through the workflows in section 4.

## 6. Identification and discovery

Department managers identify the assets their functions use. Technical discovery catches what manual identification misses, such as shadow IT and unrecorded cloud resources.

| Discovery source | Finds | Run by |
| --- | --- | --- |
| Azure resource inventory and Azure Policy | Subscriptions, databases, storage and their regions | IT Manager / DevOps team |
| Device management (e.g. Intune) | Endpoints and mobile devices | IT Operations |
| Entra ID enterprise applications | SaaS tools connected to company identities | IT Operations |
| Procurement and finance supplier lists | New SaaS subscriptions and suppliers | Finance Manager |
| HR joiner, mover and leaver reports | Ownership changes and devices to recover | HR Manager |

**Quarterly reconciliation**

- Found but not registered: registered through the new-asset workflow, or recorded as out of scope with a reason.
- Registered but not found: investigated, then updated or retired.
- The number of differences is reported to the Steering Group (section 10).

## 7. Protection

Protection is set by two documents. This procedure does not repeat them:

- **Handling rules for each classification:** NSD-ISMS-008 §4.
- **Asset-specific controls:** candidate controls in NSD-ISMS-010, confirmed through risk treatment and the Statement of Applicability.

Custodians keep evidence that the required controls work. Owners review that evidence at attestation.

## 8. Retirement and disposal

1. The owner approves retirement and confirms the retention requirement with the Data Protection lead.
2. Information still required is moved to an approved location at the same classification.
3. The custodian destroys the remaining data using the method for its classification (NSD-ISMS-008 §4):
    - Internal: normal deletion.
    - Confidential: secure deletion.
    - Restricted: crypto-erasure or certified destruction, with a destruction record.
4. Hardware is wiped or destroyed and recovered from leavers (Annex A 7.14).
5. Access, keys, integrations and supplier data copies linked to the asset are removed.
6. The GRC Analyst marks the asset **Retired** in NSD-ISMS-006. The AST ID is never reused. Linked ARM scenarios are closed.

**Disposal records are mandatory for Confidential and Restricted assets.** Each record holds the asset ID, the data destroyed, the method, the date, the person who carried it out and the owner's approval.

## 9. Exceptions and non-compliance

- **Exceptions** follow NSD-ISMS-008 §8: requested to the GRC Analyst, risk-assessed, approved by the owner for Confidential or the MD for Restricted, for a maximum of 12 months, and logged.
- **Non-compliance** with this procedure is reported to the GRC Analyst. It is recorded in the corrective action log and treated as a nonconformity under clause 10.2. A non-compliance involving data exposure is also handled as a security incident.

## 10. Measures

Reported at each Steering Group meeting and as input to management review (clause 9.3):

| Measure | Target |
| --- | --- |
| In-scope assets with an accepted owner (Obj 2) | 100% by month 3, then maintained |
| Attestations completed on time | 95% or higher |
| Reconciliation differences open longer than 30 days | 0 |
| Expired exceptions | 0 |
| Retired Confidential and Restricted assets with a disposal record | 100% |

## 11. Records

| Record | Location | Owner | Retention |
| --- | --- | --- | --- |
| Asset register and change history | GRC register | GRC Analyst | Current version plus 3 years of history |
| Ownership acceptances and transfers | GRC register | GRC Analyst | 3 years after the asset is retired |
| Attestation records | GRC register | GRC Analyst | 3 years |
| Reconciliation results | GRC register | GRC Analyst | 3 years |
| Exceptions log | GRC register | GRC Analyst | 3 years after expiry |
| Disposal and destruction records | GRC register | GRC Analyst | 6 years |

The retention periods are proposals. Three years covers a full certification cycle. Disposal records are kept longer because they may be needed to show that personal data was destroyed. The Data Protection lead confirms all periods in the retention schedule.

## 12. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the procedure | Pending | |
| IT Manager | Validates discovery and disposal steps | Pending | |
| Data Protection lead | Validates retention and disposal rules | Pending | |
| Information Security / GRC Analyst | Process owner | Prepared | |

## 13. Change log

| Version | Change |
| --- | --- |
| 1.0 (portfolio draft) | First draft: Information Asset Management Procedure (NSD-ISMS-010) |
| 0.1 | Renumbered from NSD-ISMS-010 to NSD-ISMS-011 and retitled to include review and approval, completing the asset management milestone. Process owner moved from the IT Manager to the GRC Analyst to avoid a segregation-of-duties conflict. Classification now refers to confidentiality only (NSD-ISMS-008), with integrity and availability under NSD-ISMS-009. Replaced "quarterly for all" reviews with the risk-based schedule used in 006, 007 and 009. Added a RACI, the lifecycle stages, approval workflows with time limits, an attestation checklist with escalation, technical discovery and reconciliation, mandatory disposal records, exceptions aligned with NSD-ISMS-008, measures for Obj 2, and record retention periods. Replaced the generic protection list with references to NSD-ISMS-008 and 010. |

---

*Portfolio note: Proposed procedure for the simulated organisation, pending management approval.*
