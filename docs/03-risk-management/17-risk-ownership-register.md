# Northstar Digital Solutions Ltd — Risk Ownership Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-017 |
| Version | 0.1 — Draft for owner acceptance |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clauses 5.3, 6.1.2(c)(2), 6.1.3(f)) |
| Related documents | [NSD-ISMS-007 Asset Ownership](../02-asset-management/07-asset-ownership-register.md) · [NSD-ISMS-014 Risk Register](14-risk-register.md) · [NSD-ISMS-015 Treatment Plan](15-risk-treatment-plan.md) · [NSD-ISMS-016 Acceptance Criteria](16-risk-acceptance-criteria-register.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Quarterly, and when a risk owner changes role or leaves |
| Classification | Confidential |

---

## 1. Purpose

Clause 6.1.2(c)(2) requires every information security risk to have an owner. Clause 6.1.3(f) requires risk owners to approve treatment and accept residual risk. This register:

- assigns each of the 20 risks in NSD-ISMS-014 to an owner with the **authority, budget and capacity** to act;
- fixes the concentration of risk ownership found in NSD-ISMS-007, 010, 014 and 015;
- records each owner's acceptance of ownership.

## 2. Four kinds of owner

| Role | Accountable for | Source |
| --- | --- | --- |
| **Asset owner** | An asset: its classification, access and protection | NSD-ISMS-007 |
| **Risk owner** | A risk: approving treatment, accepting residual risk within authority, reviewing it on schedule | This register |
| **Control owner** | Running a control and providing evidence | NSD-ISMS-019 |
| **Action owner** | Delivering a treatment action | NSD-ISMS-015 |

One person can hold several of these roles, but the GRC Analyst never accepts risk (NSD-ISMS-016 §3).

## 3. Criteria for a risk owner

A risk owner must:

1. Be accountable for the **business area** the risk affects, not just the technology involved.
2. Have the **authority** to approve the treatment and direct the action owners.
3. Control the **budget** for proportionate treatment, or have direct access to the MD for it.
4. Have the **capacity** to review the risk at the frequency its band requires (NSD-ISMS-012 §9).
5. Have no **conflict of interest.** For example, the GRC Analyst coordinates and verifies treatment, so should own as few risks as possible.

## 4. What the review found

The first allocation in NSD-ISMS-014 v0.2 failed three of these criteria:

| Finding | Detail | Criterion |
| --- | --- | --- |
| Concentration | The Head of Engineering and IT Manager owned 15 of 20 risks, including all 4 Very High risks | 4 (capacity) |
| Technical owners for business risks | Leavers keeping access (R-12) starts in the HR process. AI tool misuse (R-19) is about how all staff behave. EU data residency (R-02) and breach notification (R-18) are legal duties | 1 (business accountability) |
| Oversight role owning risk | The GRC Analyst owned R-15 and R-18 while also verifying their treatment | 5 (conflict) |

## 5. Revised allocation

| Risk | Scenario (short) | Current | Old owner | **New owner** | Reason for change |
| --- | --- | --- | --- | --- | --- |
| R-01 | Customer data exfiltration | 15 High | Head of Engineering | Head of Engineering | Unchanged: owns the platform and AST-001 |
| R-02 | EU data outside the EU region | 12 High | Head of Engineering | **Data Protection lead** | A legal compliance duty. The Head of Engineering remains action owner (T-02.1, T-08.1) |
| R-03 | HR records exposure | 12 High | HR Manager | HR Manager | Unchanged |
| R-04 | Payment fraud | 12 High | Finance Manager | Finance Manager | Unchanged |
| R-05 | Malicious code change | 12 High | Head of Engineering | Head of Engineering | Unchanged |
| R-06 | Secrets in code | 20 Very High | Head of Engineering | Head of Engineering | Unchanged |
| R-07 | CI/CD supply chain | 15 High | Head of Engineering | Head of Engineering | Unchanged |
| R-08 | Azure misconfiguration | 15 High | Head of Engineering | Head of Engineering | Unchanged |
| R-09 | Azure regional outage | 10 High | Head of Engineering | Head of Engineering | Unchanged |
| R-10 | Phishing → Microsoft 365 compromise | 12 High | IT Manager | IT Manager | Unchanged |
| R-11 | Password spraying | 12 High | IT Manager | IT Manager | Unchanged |
| R-12 | Leavers keep access | 16 Very High | IT Manager | **HR Manager** | The leaver process starts in HR. IT Operations remains action owner (T-12.1–12.3) |
| R-13 | Privileged credential misuse | 15 High | IT Manager | IT Manager | Unchanged |
| R-14 | Ransomware destroys backups | 20 Very High | IT Manager | IT Manager | Unchanged |
| R-15 | Log tampering or loss | 12 High | GRC Analyst | GRC Analyst | Unchanged, with a recorded exception: no other role is independent of the administrators. Accepted by the Steering Group; treatment verified by the internal auditor |
| R-16 | Supplier account compromise | 15 High | Finance Manager | Finance Manager | Unchanged: owns supplier contracts (AST-015) |
| R-17 | Unpatched critical vulnerability | 15 High | Head of Engineering | Head of Engineering | Unchanged: owns patching of the platform |
| R-18 | Late breach notification | 12 High | GRC Analyst | **Data Protection lead** | Breach notification is a data protection duty. The GRC Analyst remains action owner (T-18.1) |
| R-19 | Restricted data in AI tools | 16 Very High | IT Manager | **Managing Director** | A business-wide decision about acceptable use and staff behaviour. IT Operations remains action owner (T-19.2) |
| R-20 | Lost or stolen laptop | 8 Medium | IT Manager | IT Manager | Unchanged |

## 6. Effect of the change

| Risk owner | Before | After | Very High (after) | Risk reviews per year (after) |
| --- | --- | --- | --- | --- |
| Head of Engineering | 8 | **7** | 1 (R-06) | 36 |
| IT Manager | 7 | **5** | 1 (R-14) | 26 |
| HR Manager | 1 | **2** | 1 (R-12) | 16 |
| Finance Manager | 2 | 2 | 0 | 8 |
| Data Protection lead | 0 | **2** | 0 | 8 |
| Managing Director | 0 | **1** | 1 (R-19) | 12 |
| GRC Analyst | 2 | **1** | 0 | 4 |
| **Total** | 20 | 20 | 4 | 110 |

Reviews per year follow the current band: Very High monthly (12), High quarterly (4), Medium six-monthly (2), Low annually (1).

**What improved**

- The 4 Very High risks now sit with 4 different owners, instead of 2.
- The Head of Engineering and IT Manager own 12 risks instead of 15.

**What did not change, and why.** Twelve of 20 is still a concentration. The remaining risks are platform and infrastructure risks, and only these two roles have the authority to direct that work. Moving them to someone without that authority would fail criterion 2. The concentration is managed instead through:

- **Deputies** (section 7).
- **Capacity.** The Head of Engineering carries about 36 risk reviews a year, mostly quarterly. The charter §8.1 resource decision must include their time.
- **Reallocation as the risks fall.** When treatment moves risks from High to Medium (NSD-ISMS-015 targets), the review load drops from 110 to 40 a year.

## 7. Deputies and escalation

| Risk owner | Deputy | Notes |
| --- | --- | --- |
| Head of Engineering | IT Manager | Cross-cover, as in NSD-ISMS-007 |
| IT Manager | Head of Engineering | Cross-cover. If both are unavailable (ARM-26), the MD acts |
| HR Manager | Managing Director | |
| Finance Manager | Managing Director | |
| Data Protection lead | Managing Director | |
| GRC Analyst (R-15) | Managing Director | Keeps independence from the administrators |
| Managing Director (R-19) | Finance Manager, as nominated Steering Group member | The deputy acts on reviews only. MD-level acceptance decisions wait for the MD |

A deputy acts only during absence or a conflict of interest. Deputies cannot accept risk above their own authority under NSD-ISMS-016.

## 8. Risk owner duties

| Duty | Frequency | Record |
| --- | --- | --- |
| Review each owned risk: score, controls, treatment progress | By band (section 6) | Review entry in NSD-ISMS-014 |
| Approve the treatment and target residual for each risk | When the plan is approved, and on each change | NSD-ISMS-015 §4 |
| Propose acceptance decisions with justification | When needed | NSD-ISMS-016 Part B |
| Report material changes: new threats, incidents, business changes | As they occur | Steering Group minutes |
| Attend the Steering Group when an owned risk is High or Very High | Each meeting | Minutes |
| Hand over ownership before leaving the role | On role change | Section 10 |

## 9. Ownership acceptance

| Risk owner | Risks | Acceptance |
| --- | --- | --- |
| Head of Engineering | R-01, 05, 06, 07, 08, 09, 17 | Pending |
| IT Manager | R-10, 11, 13, 14, 20 | Pending |
| HR Manager | R-03, R-12 | Pending |
| Finance Manager | R-04, R-16 | Pending |
| Data Protection lead | R-02, R-18 | Pending |
| Managing Director | R-19 | Pending |
| GRC Analyst | R-15 | Pending, with the recorded exception in section 5 |

Each acceptance records:

- the risk IDs;
- the owner's name and role;
- the date;
- confirmation that the owner has read the duties in section 8 and the authority limits in NSD-ISMS-016;
- how it was recorded: signed form, email or GRC tool entry.

## 10. Ownership changes

- Ownership transfers **before** the current owner leaves the role. The HR leaver and mover process triggers this check, as for assets (NSD-ISMS-007 §7).
- A risk with no owner is escalated to the Steering Group within 10 working days. The MD is interim owner until one is assigned.
- Every change is recorded below, with the reason and the MD's approval.

| Date | Risk | From | To | Reason | Approved by |
| --- | --- | --- | --- | --- | --- |
| Pending approval | R-02 | Head of Engineering | Data Protection lead | Legal duty (section 4) | MD |
| Pending approval | R-12 | IT Manager | HR Manager | Business process owner | MD |
| Pending approval | R-18 | GRC Analyst | Data Protection lead | Legal duty; removes oversight conflict | MD |
| Pending approval | R-19 | IT Manager | Managing Director | Business-wide behaviour | MD |

## 11. Documents updated by this register

| Document | Update |
| --- | --- |
| NSD-ISMS-014 Risk Register | v0.3: owners for R-02, R-12, R-18 and R-19; concentration table |
| NSD-ISMS-015 Treatment Plan | v0.3: target approval owners; independent verification rule |
| NSD-ISMS-016 Acceptance Criteria | v0.2: GRC-owned risks are now R-15 only; target acceptance owners |

## 12. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the allocation and the four ownership changes | Pending | |
| Risk owners | Accept ownership (section 9) | Pending | |
| Information Security / GRC Analyst | Prepared the register | Prepared | |

## 13. Change log

| Version | Change |
| --- | --- |
| 0.1 | First version. Owner criteria set; review of the NSD-ISMS-014 allocation; four ownership changes (R-02, R-12, R-18, R-19); capacity analysis; deputies; duties; acceptance and change records. |

---

*Portfolio note: Ownership assignments are simulated and require management validation.*
