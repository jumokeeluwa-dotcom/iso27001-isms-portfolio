# Northstar Digital Solutions Ltd — Supplier Risk Assessment Methodology

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-056 |
| Version | 1.0 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: clauses 6.1.2, 6.1.3, 8.2; Annex A 5.19–5.23 |
| Parent documents | [NSD-ISMS-012 Risk Assessment Methodology](../03-risk-management/12-risk-assessment-methodology.md) · [NSD-ISMS-013 Scoring Matrix](../03-risk-management/13-risk-scoring-matrix.md) · [NSD-ISMS-016 Acceptance Criteria](../03-risk-management/16-risk-acceptance-criteria-register.md) · [NSD-ISMS-026 Supplier Security Policy](../05-policies/26-supplier-security-policy.md) |
| Records | Tiers: [NSD-ISMS-055](55-supplier-register.md) · Assessment results: NSD-ISMS-058 · Risks: [NSD-ISMS-014](../03-risk-management/14-risk-register.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Classification | Internal |

---

## 1. Purpose

This methodology sets out how Northstar decides how closely to examine each supplier, and how it assesses, records and treats the information security risks suppliers bring. It **applies the existing risk methodology** (NSD-ISMS-012, 013, 016) to suppliers; it does not create a separate one.

## 2. Why there is no separate supplier scoring scale

Supplier risks are scored on Northstar's 5×5 matrix, with its four bands and the acceptance rules tied to them, not on a separate scale.

A second scale would make supplier risks impossible to compare with every other risk: a supplier "High" (6–9 out of 9) would not mean the same as a register "High" (10–15 out of 25), and the acceptance authorities in NSD-ISMS-016 could not be applied. Clause 6.1.2(b) requires risk assessments to produce **consistent, valid and comparable** results.

So the method separates two questions:

| Question | Answered by | Result |
| --- | --- | --- |
| **How closely must we examine this supplier?** | Exposure factors (section 3) | A **tier,** recorded in NSD-ISMS-055 |
| **How much risk does this supplier bring, given what we found?** | The NSD-ISMS-013 matrix, applied to specific risk scenarios (section 5) | Risks scored in NSD-ISMS-014, using the same scale and bands as every other risk |

## 3. Tiering: exposure factors

The tier is set **before** onboarding, from what the supplier will hold or touch, not from how good it claims to be.

| Factor | Question | Pushes the tier to Critical when… |
| --- | --- | --- |
| Customer data | Will it process customer data in the platform? | Yes: it is a sub-processor |
| Access | What access will it have: none, user, privileged, or a route to production? | Privileged access, or a route into production such as CI/CD |
| Dependency | Which BIA activities (NSD-ISMS-049) depend on it, and is there a workaround? | It supports A1, A2 or A3 (RTO of 4 hours or less) with no workaround |
| Northstar information | What is the highest classification it will hold? | — (Restricted or Confidential gives **High**) |
| Personal data | Will it process Northstar's own personal data (staff, applicants, customer contacts)? | — (gives **High**) |
| Financial services flow-down | Does it support services for financial services customers? | DORA terms apply in any tier (NSD-ISMS-026 §4) |

**Tier rule:**

| Tier | Rule |
| --- | --- |
| **Critical** | Any of: processes customer data; privileged or production access; supports A1, A2 or A3 with no workaround |
| **High** | Not Critical, and any of: holds Restricted or Confidential information; processes Northstar personal data; has user-level access to Northstar systems |
| **Standard** | None of the above |
| **Unknown facts** | Treated at the higher tier until confirmed (NSD-ISMS-055 §3) |

This closes gap 5 in the supplier register: suppliers holding **Restricted** information that is not personal data, such as penetration test reports, are now High by rule rather than by judgement. NSD-ISMS-026 §3 is updated to match (v1.0).

**Depth of assessment by tier** follows NSD-ISMS-026 §3: Critical suppliers need independent assurance, **plus** the questionnaire (NSD-ISMS-057), **plus** a DPA where relevant; High suppliers need the questionnaire, plus a certificate where available; Standard suppliers need contract terms only.

## 4. Assurance factors

Assurance factors describe how well the supplier protects what it holds. They affect **likelihood,** and they are assessed in due diligence (NSD-ISMS-057) and recorded in NSD-ISMS-058.

| Factor | What is checked | Evidence, strongest first |
| --- | --- | --- |
| Independent assurance | ISO/IEC 27001 certificate or SOC 2 report; **does its scope cover the service Northstar uses?** For SOC 2: Type II (tested over a period), not Type I (design only); report period; exceptions found by the auditor; bridge letter covering the gap since | Certificate and Statement of Applicability, or the full report |
| Complementary controls | What the assurance report says the **customer** must do. Those controls become Northstar's responsibility (NSD-ISMS-026 §8) | The report's "complementary user entity controls" section |
| Data location and transfers | Where data is stored, processed and supported from; the transfer mechanism outside the UK and EU (R-02) | DPA; sub-processor list |
| Subcontractors (fourth parties) | Which sub-processors it uses; how it manages them; notice of changes | Sub-processor list; contract |
| Incident management | Reporting to Northstar within 24 hours; contacts; support for investigations | Contract clause; process evidence |
| Resilience | Recovery objectives compared with what Northstar's BIA needs | Continuity evidence; SLA |
| Contract terms | The nine clauses in NSD-ISMS-026 §4; DORA terms where relevant | Contract (AST-015) |
| Exit | Return or deletion of data; transition support; substitutability | Contract; exit plan |
| Track record | Incidents, breaches, enforcement or adverse news | Public sources; supplier disclosure |

**How evidence counts.** The NSD-ISMS-012 control credit rule applies to supplier controls too:

| Evidence | Credit |
| --- | --- |
| A current certificate or SOC 2 Type II report whose **scope covers the service,** with no relevant exceptions | Effective: full credit |
| A certificate whose scope does not clearly cover the service; a Type I report; relevant exceptions; questionnaire answers backed by documents | Partial |
| **Questionnaire answers only** (self-assertion), or expired evidence | None |

A supplier saying "yes, we encrypt data at rest" is a claim, not evidence.

## 5. Scoring supplier risks

Supplier risks are scored like any other risk: **likelihood × impact on the NSD-ISMS-013 scales, highest impact category sets the score, bands Low 1–4, Medium 5–9, High 10–15, Very High 16–25.**

1. **Write the risk as a scenario** (NSD-ISMS-012 §5): source, event, asset, consequence. For example: "An attacker compromises the MSP's support account (SUP-04) and uses its access to Microsoft 365 to read Restricted HR files."
2. **Impact** comes from what the supplier holds, the exposure factors in section 3. A sub-processor holding several customers' data can reach impact 5.
3. **Likelihood** starts from the NSD-ISMS-013 likelihood scale, then takes account of the assurance found. Weak or missing assurance, or a history of incidents, means a higher likelihood.
4. Record three ratings, as for every risk: **inherent, current residual and target residual.**

**Not every supplier needs its own risk.** If an assessment finds the supplier's controls adequate and the residual risk within appetite (NSD-ISMS-016 §2), the result is recorded in NSD-ISMS-058 against the existing risks (for example R-16). A **new or re-scored** risk is raised in NSD-ISMS-014 only when the assessment finds something that changes the risk picture: a gap, a missing assurance, a new data flow, or a concentration.

**Tier is not a risk score.** A Critical supplier with strong, evidenced assurance can carry a Medium residual risk. A High supplier with no assurance and Restricted data can carry a High one. The tier sets the depth of examination, whatever the score.

## 6. Process

| Step | Action | Who | Record |
| --- | --- | --- | --- |
| 1 | Record the supplier and **set the tier** before any access or data is given | Business owner, with the GRC Analyst | NSD-ISMS-055 |
| 2 | Map the service and information flows: what data, which systems, which locations | Business owner | NSD-ISMS-055 |
| 3 | Due diligence at the depth set by the tier | GRC Analyst | NSD-ISMS-057 |
| 4 | Review the assurance evidence and apply the credit rule (section 4) | GRC Analyst | NSD-ISMS-058 |
| 5 | Identify risk scenarios; score inherent and current residual risk | Risk owner, supported by the GRC Analyst | NSD-ISMS-014 if new or changed |
| 6 | Decide treatment and target residual risk | Risk owner | NSD-ISMS-015 |
| 7 | **Decision:** approve, approve with dated conditions, or reject | See section 8 | NSD-ISMS-058 |
| 8 | Set the review date and monitoring | GRC Analyst | NSD-ISMS-058 |

## 7. Treatment

The same four options as NSD-ISMS-012 §5:

| Option | For suppliers |
| --- | --- |
| **Modify** (also called mitigate) | Contract clauses; access limits (NSD-ISMS-023 §10); encryption with Northstar-held keys; monitoring of supplier accounts; conditions to be met by a date |
| **Avoid** | Do not use the supplier, or do not send it the data |
| **Share** | Contract liability or insurance. **Accountability for customer data stays with Northstar,** and so do the duties to notify customers |
| **Retain** | Accepted under NSD-ISMS-016, by the authority for the residual band |

**Concentration and exit (Critical suppliers).** Each Critical supplier needs an exit assessment: how hard it would be to replace, how data would be returned, and how long a transition would take. For Microsoft (SUP-01, SUP-02), the risk is concentration rather than exit: one supplier failing affects the platform, identity and email at once (EXT-05). That risk is recorded in R-09 and handled through the BIA and recovery planning, because realistically the supplier cannot be replaced at short notice.

## 8. Approval

| Decision | Authority |
| --- | --- |
| Tier | GRC Analyst proposes; business owner confirms |
| Approve onboarding where residual risk is within appetite | Business owner, on the GRC Analyst's recommendation |
| Accept residual risk outside appetite | By band, under NSD-ISMS-016 §3: **Medium:** risk owner; **High:** Steering Group; **Very High:** MD only. **Any risk with impact 5: the MD** |
| Approve a Critical supplier with any open condition | MD |
| Known non-compliance with a legal or contractual requirement, such as a sub-processor not yet notified to customers | **Cannot be accepted** (NSD-ISMS-016 §4); it must be corrected |

The GRC Analyst assesses and recommends, and **never accepts risk** for the business (NSD-ISMS-016).

## 9. Reassessment

| Trigger | Reassessment |
| --- | --- |
| Scheduled | Critical: annually; High: every 2 years; Standard: at renewal |
| Assurance expiring | Before the certificate or report expires |
| Change in service, access, data, location or sub-processors | Before the change takes effect |
| Supplier security incident affecting Northstar | Within 10 working days of the incident closing |
| Contract renewal | Before signing |
| Merger, acquisition or adverse news | Within 20 working days |
| KPI-14 or other monitoring shows a problem | As decided by the Steering Group |

## 10. Approval

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

---

*Portfolio disclaimer: Simulated methodology. It requires organisational validation and approval.*
