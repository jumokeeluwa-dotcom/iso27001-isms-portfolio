# Northstar Digital Solutions Ltd — Supplier Security Assessment Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-058 |
| Version | 1.0 — Simulated records |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 5.19–5.23; clause 8.2 |
| Status | **Simulated. No assessment has been performed through this register** |
| Position as at | 30 September 2027 |
| Method | [NSD-ISMS-056](56-supplier-risk-assessment-methodology.md) · questionnaire [NSD-ISMS-057](57-supplier-due-diligence-questionnaire.md) |
| Related records | Suppliers and tiers: [NSD-ISMS-055](55-supplier-register.md) · Risk ratings: [NSD-ISMS-014](../03-risk-management/14-risk-register.md) · KPI-14 |
| Register owner | Information Security / GRC Analyst |
| Classification | Confidential |

---

## 1. What this register holds

One entry per assessment: the evidence reviewed, how much credit it earns, what was found, the risks affected and the decision. **Risk ratings are not held here.** They live in NSD-ISMS-014, on the NSD-ISMS-013 scale.

## 2. Assessment status

| Supplier | Tier (055) | Assessment record in the portfolio? | Status | Due by | Order |
| --- | --- | --- | --- | --- | --- |
| SUP-04 MSP | Critical (provisional) | No | **Not assessed.** First confirm whether it holds administrator roles | 29 Oct 2027 | 1 |
| SUP-07 Security monitoring | Critical | No | Not assessed | 12 Nov 2027 | 2 |
| SUP-10 Support ticketing | Critical | No | Not assessed. Sub-processor status to confirm (055 gap 4) | 12 Nov 2027 | 3 |
| SUP-09 Code repository and CI/CD | Critical | No | Not assessed | 26 Nov 2027 | 4 |
| SUP-01 Microsoft Azure | Critical | No | Not assessed: **mapping of published assurance** (057 §1) | 10 Dec 2027 | 5 |
| SUP-02 Microsoft 365 and Entra ID | Critical | No | Not assessed: mapping of published assurance | 10 Dec 2027 | 5 |
| SUP-16 Incident response provider | Critical | No | Not assessed. **Must be assessed before it is needed** | 17 Dec 2027 | 6 |
| SUP-03, 05, 06, 08, 11, 12, 13, 14, 15 | High | No | Not assessed | By 30 Jun 2028 | 7 |

**About the Q2 2027 KPI.** The dashboard reported 4 of 5 Critical suppliers assessed (KPI-14, NSD-ISMS-044). Neither the list of five nor their assessment records are in the portfolio. Missing records are not counted as success, so **no supplier is shown as assessed here** until the Finance Manager's investigation (due 14 Sep 2027) produces the records. If it does, each is entered with its evidence and checked against the 056 credit rule.

**Effect on KPI-14:** at Q3 2027, 0 of 7 Critical suppliers have an assessment record here, so KPI-14 would be **0%**, unless the records are found. That is reported as it is, with the reason (055 gap 1).

**The order** puts first the suppliers where a compromise would do most harm and least is known: the MSP's access is the scenario in R-16, which is rated High (15).

## 3. Assessment record

Each assessment records:

| Field | Notes |
| --- | --- |
| Supplier ID, tier, business owner | From NSD-ISMS-055 |
| Assessment type and date | Onboarding, scheduled, or triggered (056 §9), with the trigger |
| Assessor; technical reviewer | GRC Analyst; IT Manager or Head of Engineering (057 §5) |
| Evidence reviewed, **by type** | See section 4: each item labelled with its evidence type |
| Certificate or report check | Issuer, number, validity, **scope covers the service?**, exclusions; for SOC 2: type, period, exceptions, bridge letter |
| Complementary controls | What Northstar must do; who owns each one |
| Knock-out answers | Any ★ answer that was unacceptable, and the escalation |
| Findings | Each gap, with evidence |
| Control credit | Effective, Partial or none for each control relied on (056 §4) |
| Risks affected | Existing risk IDs, or a new risk raised in NSD-ISMS-014; **ratings are held there** |
| Decision | Approve; approve with dated conditions; escalate for acceptance (056 §8); do not onboard or plan exit |
| Decision by, date | At the authority in 056 §8 |
| Conditions and actions | Owner and due date; tracked in NSD-ISMS-015 or 034 |
| Next review | From the tier and triggers (056 §9) |

## 4. Types of evidence

| Evidence type | Example | Credit (056 §4) |
| --- | --- | --- |
| **Supplier assertion** | "Yes" in the questionnaire | None |
| **Supplier's own documents** | Its policy or procedure | Partial at most: shows design, not operation |
| **Contract commitment** | 24-hour incident notification clause | An enforceable obligation, **not evidence that the control works** |
| **Independent assurance** | ISO/IEC 27001 certificate, SOC 2 Type II report | Effective, **if the scope covers the service** and there are no relevant exceptions |
| **Validated by Northstar** | Northstar's own check of the supplier's guest accounts, MFA and sign-in logs in Entra ID | Effective for what was checked |

A certificate shows that a management system was audited within its scope. It does not show that every risk to Northstar is covered. **Northstar's own checks are the strongest evidence for controls Northstar can see**, such as MFA on supplier accounts in its own tenant.

## 5. Risk scenarios for the first assessments

These are scenarios **to examine**, written in the NSD-ISMS-012 format. They are not ratings. A scenario becomes a new or re-scored risk in NSD-ISMS-014 only if the assessment finds that the existing risks do not cover it (056 §5).

| Supplier | Scenario | Existing risk | What the assessment must establish |
| --- | --- | --- | --- |
| SUP-04 MSP | An attacker compromises an MSP engineer's account and uses its access to Microsoft 365 or Entra ID to read Restricted files or change security settings | **R-16** (High, 15). Controls: due diligence (U), guest accounts with MFA (P) | Which roles the MSP holds; named accounts only; MFA enforced **in Northstar's tenant** (checked by Northstar); 90-day guest expiry; sign-in monitoring; contract terms |
| SUP-03 Payroll | Employees' salary and bank details are disclosed through the provider's weak access control or insecure file transfer | Not directly covered: **R-03** concerns Northstar's own SharePoint, not the provider | DPA; transfer method (no email attachments); encryption; the provider's assurance; deletion. If not covered, **propose a new risk** to the HR Manager |

The treatments for these scenarios (MFA, named accounts, monitoring, DPA, encryption and so on) are the **controls to test,** not controls assumed to be in place.

## 6. Conclusions

| Decision | When | Authority |
| --- | --- | --- |
| Approve | Residual risk within appetite; no knock-out issues | Business owner, on the GRC Analyst's recommendation |
| Approve with conditions | Gaps that can be fixed by a date | As above; MD if Critical |
| Escalate | Residual risk outside appetite | By band (NSD-ISMS-016 §3); MD for impact 5 |
| Do not onboard, or plan exit | Knock-out issue not resolved; legal non-compliance | MD |

For a supplier **already in use,** "do not onboard" means an exit plan or a dated remediation, decided by the MD.

## 7. Approval

| Role | Decision | Date |
| --- | --- | --- |
| ISMS Steering Group | Pending | |

---

*Portfolio disclaimer: No real supplier security assessments have been conducted through this simulated register.*
