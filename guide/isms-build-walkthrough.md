# Building an ISO 27001 ISMS Step by Step — A Walkthrough of the Northstar Portfolio

**Jumoke Eluwa** · Companion guide to the simulated Northstar ISMS portfolio

This guide explains **how each milestone's documents were derived**: what went in, the steps followed, the decisions that mattered, and the mistakes caught along the way. Use it to revise, to explain the portfolio in an interview, or as a method for building an ISMS from scratch.

> Northstar Digital Solutions Ltd is fictional, and every record in the portfolio is simulated. The method is real.

---

## Part 1 — The big picture

### How the milestones connect

An ISMS is a chain. Each milestone takes the previous one's outputs as its inputs:

| Order | Milestone | Answers the question | Feeds into |
| --- | --- | --- | --- |
| 1 | Initiation and context | What are we protecting, why, and within what boundary? | Everything |
| 2 | Asset management | What information and systems do we hold, who owns them, how valuable are they? | Risk |
| 3 | Risk management | What could go wrong, how bad is it, and what will we do about it? | Controls |
| 4 | Controls and SoA | Which controls do we need, and are they working? | Policies, audit |
| 5 | Policies | What rules make the controls happen? | Operation |
| 6 | Internal audit | Do the controls and processes actually work? | Improvement, review |
| 7 | Management review | Does top management direct and resource the ISMS? | Decisions, objectives |
| 8 | Monitoring and measurement | How do we know, month to month, that it is working? | Review, audit |
| 9 | Improvement | How do we fix what fails, and stop it recurring? | Every process |
| 10 | Business continuity | Can we keep going, and recover, when things break? | Risk, controls |
| 11 | Supplier risk | Can we trust the people who hold our data for us? | Risk, controls |
| 12 | Certification readiness | Would it pass an external audit? | Remediation |

**Clause map.** Clauses 4–5 sit in milestone 1; 6.1–6.3 in milestones 2–4; 7 runs through milestones 1, 5 and 12; 8 in milestones 3–5 and 10–11; 9.1 in milestone 8; 9.2 in milestone 6; 9.3 in milestone 7; 10 in milestone 9.

### The rules that run through every document

Learn these first. Almost every correction in the portfolio comes back to one of them.

| # | Rule | Why it matters |
| --- | --- | --- |
| 1 | **Missing records are never counted as success** | "We're confident it was done" is not evidence. No record means not done, or at best unverified |
| 2 | **"No events" is never 100%** | Zero incidents shows nothing about whether incident response would work |
| 3 | **One register per item, one accountable owner** | Two registers holding the same action will soon disagree. Two owners means no owner |
| 4 | **Nobody verifies their own work** | The person who did the work, or designed the control, is never the one who signs it off |
| 5 | **The GRC Analyst never accepts risk** | Risk is accepted by the risk owner or the MD, by band |
| 6 | **Controls come from risk treatment, then Annex A is a cross-check** | Annex A is not a checklist to work through |
| 7 | **Evidence over assertion** | Policies on paper earn no credit; only tested controls reduce a risk score |
| 8 | **Correction, corrective action and effectiveness verification are different** | Fix the symptom; remove the cause; prove it worked |
| 9 | **Concrete commitments, not vague words** | "Promptly", "periodically" and "where appropriate" become a time, a frequency or a condition |
| 10 | **Charter roles only** | Use the organisation's real roles, not "Security Lead" or "Senior Management" when they don't exist |

### How every draft was handled

Each milestone followed the same loop:

1. **Read the draft against the standard.** Which clause or control is it for? What does that clause actually require?
2. **Check it against earlier documents.** Same roles, same risk IDs, same scales, same numbers.
3. **Challenge it like an auditor.** Is anything vague, untestable, duplicated or overstated?
4. **Renumber and align** it into the portfolio sequence.
5. **Record what changed and why** in the change log.
6. **Re-check the counts:** totals in summaries must match the tables.

---

## Part 2 — Milestone by milestone

### Milestone 1 — Initiation and context (001–004)

**Purpose.** Clauses 4.1–4.4 and 5: understand the organisation, its stakeholders and the ISMS boundary, and set up governance.

**Documents and order**

| Step | Document | Derived from |
| --- | --- | --- |
| 1 | 001 Project Charter | Business drivers: customer demands, regulation, certification goal |
| 2 | 002 Context Register | Charter §5; internal and external issues, including climate change |
| 3 | 003 Interested-Party Register | Context register; contracts, law, customers, staff |
| 4 | 004 Scope Statement | All three: what is in, what is out, and why |

**Steps**

1. **Write the charter first.** It sets the objectives everything is measured against. Each objective needs a measure, a target and an owner (clause 6.2), for example "Obj 6: privileged accounts with MFA and quarterly review, 100%, IT Manager". It also names the roles every later document must use.
2. **List internal and external issues** (INT-xx, EXT-xx). For each, record why it matters to information security, not just that it exists. Examples: dependence on one cloud provider (EXT-05, Microsoft concentration); climate-related disruption (EXT-12).
3. **Assess climate change** (Amendment 1:2024). Clause 4.1 now requires the organisation to determine whether climate change is a relevant issue; clause 4.2 notes interested parties may have climate-related requirements. Record a decision either way.
4. **List interested parties and their requirements** (IP-01 to IP-17). For each: what they need, where the requirement comes from (contract, law), whether the ISMS addresses it, and who owns it. Example: IP-03, financial services customers with DORA terms.
5. **Draw the scope boundary.** State the organisation, locations, technology, information and people covered; the interfaces and dependencies (suppliers, cloud); and any exclusions with reasons. Write the scope sentence as it would appear on a certificate.

**Key considerations**

- The scope must be **defensible**: you cannot exclude the thing customers care about most.
- **Interfaces matter.** Services run by suppliers are outside your direct control but inside your risk.
- **Climate change must be assessed,** not ignored, under Amendment 1.
- Objectives must be **measurable,** or clause 9.1 cannot evaluate them later.

**Caught in the drafts:** roles that did not exist in the organisation; a scope missing the EU-based staff and the EU Azure region.

**Interview angle:** "How did you set the ISMS scope?" Explain boundaries, interfaces and why nothing customers depend on was excluded.

---

### Milestone 2 — Information asset management (006–011)

**Purpose.** Annex A 5.9–5.13: know what you hold, who owns it, how sensitive and valuable it is. This is the raw material for risk assessment.

**Documents and order**

| Step | Document | What it adds |
| --- | --- | --- |
| 1 | 006 Asset Register | 20 assets (AST-001 to 020): information plus the systems that hold it |
| 2 | 007 Ownership Register | One accountable owner per asset; workload and segregation checks |
| 3 | 008 Classification Scheme | Four levels: Restricted, Confidential, Internal, Public; handling rules |
| 4 | 009 Valuation Methodology | Confidentiality, integrity and availability rated High, Medium or Low |
| 5 | 010 Asset–Risk Mapping | First risk scenarios per asset, handed to the risk register |
| 6 | 011 Review Procedure | Lifecycle, attestation, disposal |

**Steps**

1. **Inventory information first, then the systems that hold it.** Customer data is the asset; the database is a supporting asset.
2. **Give every asset one owner,** a role accountable for it, not a team. Then check **concentration:** if two people own most assets, that is a capacity risk.
3. **Classify by confidentiality** using decision steps, so two people would reach the same answer.
4. **Value each asset on C, I and A separately.** Then set the **criticality tier by how many dimensions are High:** Critical (2–3 High), High (1), Medium, Low. Taking the single highest rating would make almost everything High and stop you prioritising.
5. **Apply inheritance, aggregation and dependency rules:** a system inherits the highest value of the information it holds; many Internal records together can be Confidential; a system everything depends on is valued for availability accordingly.
6. **Map assets to first risk scenarios** and hand them over to the risk register.

**Key considerations**

- **Classification ≠ valuation.** Classification is about confidentiality and handling; valuation covers C, I and A.
- **An asset not in the register has no owner, no classification and no risk assessment.** The supplier milestone later found a CRM missing for exactly this reason.
- **Check the totals.** Summary counts must match the tables.

**Caught in the drafts:** count errors (13 High-rated assets, not 14; 10 Restricted, not 11); one asset's confidentiality over-rated (AST-004, High to Medium).

**Interview angle:** "How do you value an asset?" Explain C/I/A and why the tier counts High ratings rather than taking the maximum.

---

### Milestone 3 — Risk assessment and treatment (012–017)

**Purpose.** Clauses 6.1.2, 6.1.3, 8.2 and 8.3: assess risks consistently, decide treatment, and get the right people to accept what remains.

**Documents and order**

| Step | Document | Key content |
| --- | --- | --- |
| 1 | 012 Methodology | How risks are identified, analysed, rated and treated |
| 2 | 013 Scoring Matrix | 5×5 likelihood and impact scales; bands |
| 3 | 016 Acceptance Criteria (Part A) | Appetite and who can accept what; **approved before scoring** |
| 4 | 014 Risk Register | 20 risk scenarios with three ratings each |
| 5 | 015 Treatment Plan | 36 actions in four priority groups |
| 6 | 017 Ownership Register | One appropriate owner per risk |

**Steps**

1. **Fix the method before scoring** (clause 6.1.2(a)): the criteria for accepting risk and for performing assessments must exist first, or every score is provisional.
2. **Write each risk as a scenario:** threat source, event, asset, consequence. "Leavers keep access" (R-12) is better than "access control risk".
3. **Score on the 5×5 matrix.** Likelihood within 12 months; impact by the **worst credible** consequence across confidentiality, integrity, availability, legal, contractual, financial and reputational effects. Record evidence and a confidence level.
4. **Rate each risk three times:**
    - **inherent** (no specific controls);
    - **current residual** (existing controls, credited only as far as evidence supports);
    - **target residual** (after the treatment plan).
5. **Apply the control credit rule:** tested in the last 12 months = full credit; partly effective = partial; untested or paper-only = **none**.
6. **Band the scores:** Low 1–4, Medium 5–9, High 10–15, Very High 16–25. Any impact 5 goes to the MD. Result here: 4 Very High (R-06, R-12, R-14, R-19).
7. **Plan treatment:** each action has an owner, a date, and **the evidence that proves it is complete.**
8. **Review ownership:** the first allocation gave two technical leads 15 of 20 risks, and the GRC Analyst owned risks it also verified. Business risks went to business owners (HR Manager for R-12; Data Protection lead for R-02 and R-18).

**Key considerations**

- "Very High" is a risk band; "Critical" is an asset tier. Don't mix them.
- **Risk acceptance has authority levels:** Medium by the risk owner, High by the Steering Group, Very High only by the MD. Some things cannot be accepted at all, such as known legal non-compliance.
- **Treatment wording:** Modify (also called mitigate), Avoid, Share, Retain.

**Caught in the drafts:** "Critical" used as a risk band; a control credited as Effective without test evidence (R-20, BitLocker, corrected to Partial); 15 of 20 risks owned by two people; owners who were also the verifiers.

**Interview angle:** "What's the difference between inherent and residual risk?" Then add the control credit rule: it is what stops paper policies lowering risk scores.

---

### Milestone 4 — Controls and Statement of Applicability (018–021)

**Purpose.** Clause 6.1.3(b)–(d): select controls from risk treatment, compare with Annex A, and document applicability, justification and implementation status.

**Documents and order**

| Step | Document | Key content |
| --- | --- | --- |
| 1 | 018 SoA Methodology | Sources of controls; applicability rules; five statuses; seven-step process |
| 2 | 019 Statement of Applicability | 48 of 93 controls assessed (two waves) |
| 3 | 020 Risk–Control Mapping | Risk → control and control → risk, both directions |
| 4 | 021 Control Evidence Checklist | Evidence types; sample sizes by control frequency |

**Steps**

1. **Derive controls from the 36 treatment actions.** Each action maps to one or more Annex A controls.
2. **Add controls required by law, contracts and stakeholders,** including controls not in Annex A (for example NSD-C-02, DORA contract terms).
3. **Compare with all 93 Annex A controls.** For each not yet selected: does any risk or requirement need it? Yes → applicable (and raise a risk if none covers it). No → exclude, with a specific reason.
4. **Applicability is Yes or No only.** "Proposed applicable" is not a value.
5. **Set status from evidence:** Implemented, Partially implemented, Planned, Not implemented (escalate), To be assessed.
6. **Map both ways.** Risk → control shows every risk is treated; control → risk shows every control has a reason.
7. **Define the evidence for each control** (documented, operational, effectiveness) and **sample sizes:** annual 1; quarterly 2; monthly 2–3; weekly 5; daily 20–25; per event 25, **or all if fewer than 25.**

**Key considerations**

- **Statuses must match the risk register's control evidence.** If they disagree, one of them is wrong.
- **Phasing is acceptable** (48 controls first, by risk), but the rest must be dated, and late phases are a finding.
- The SoA version approved is the one on the certificate.

**Caught in the drafts:** 17 controls named in the treatment plan but missing from the SoA. Later, the SoA validation (063) also rejected "Proposed applicable" and "Designed" as SoA values.

**Interview angle:** "How do you build an SoA?" Risk treatment first, Annex A second; two-value applicability; evidence-based status.

---

### Milestone 5 — Policies (022–029)

**Purpose.** Annex A 5.1 and topic-specific controls: turn decisions into rules people follow.

**Documents:** 022 Information Security Policy; 023 Access Control; 024 Acceptable Use; 025 Classification and Handling; 026 Supplier Security; 027 Incident Management; 028 Backup and Business Continuity; 029 Vulnerability and Change Management.

**Steps**

1. **Write the top-level policy** (022): commitment, objectives framework, roles, and how topic policies hang from it.
2. **Write each topic policy from the risks and controls it serves.** Example: 023 §9 says leavers' accounts are disabled **by the end of the last working day,** because R-12 is Very High.
3. **Replace every vague word** with a testable commitment. For example, supplier incident notice became "within 24 hours of discovery" (026 §4), and reviews got set frequencies.
4. **Give each policy an owner, an approver (the MD), a review date and an exceptions process.**
5. **Cross-check** that policy numbers agree with the risk register, KPIs and other policies.

**Key considerations**

- **A policy must be testable by an auditor.** If you can't write an audit test for a sentence, rewrite it.
- **Approval comes before acknowledgement.** Later, the readiness work found staff had acknowledged policies that had never been approved (KPI-20).

**Caught in the drafts:** vague terms such as "promptly" and "where appropriate"; roles not in the charter; a single owner for policies covering both platform and corporate IT (029, split between the Head of Engineering and the IT Manager).

**Interview angle:** "What makes a good policy?" Testable commitments, a clear owner, an exceptions route, and approval before publication.

---

### Milestone 6 — Internal audit (030–035)

**Purpose.** Clause 9.2: independently check whether the ISMS conforms and works.

**Documents and order**

| Step | Document | Key content |
| --- | --- | --- |
| 1 | 030 Audit Programme | 9 risk-based audits in cycle 1; independence; grading |
| 2 | 031 Audit Plan AUD-03 | Scope, criteria, sample requests for identity and access |
| 3 | 032 Checklist | Tests with population, sample and expected evidence |
| 4 | 033 Findings Register | Graded findings with evidence |
| 5 | 034 Corrective Action Register | Correction, corrective action, verification |
| 6 | 035 Audit Report | Conclusion, findings, positive observations |

**Steps**

1. **Prioritise audits by risk.** AUD-03 (identity and access) went first because it covers R-12, a Very High risk.
2. **Ensure independence.** An external internal auditor; nobody audits their own work.
3. **Take populations from the system of record:** leavers from the HR system, accounts from Entra ID, never a list prepared by the auditee.
4. **Test the whole population if it is under 25.** AUD-03 tested all 7 leavers.
5. **Add a reverse test:** start from enabled accounts and look for a current person behind each one.
6. **Grade findings:** Major (a requirement not met at all, or a systemic failure); Minor (an isolated lapse); Observation; OFI. AUD-03 found two Minors (F01: a contractor disabled 2 days late; F02: an HR review not recorded) and one Observation.
7. **Raise corrective actions with all of clause 10.2(a)–(e):** react; evaluate causes, including checking for similar cases; implement; review effectiveness; change the ISMS if needed.

**Key considerations**

- **Clause 10.2 has five items, (a) to (e).** "Update risks and opportunities" comes from ISO 9001, not ISO 27001. The portfolio made this mistake once and corrected it.
- **Write down what would make a finding Major,** so grading is consistent.

**Caught in the drafts:** logging and monitoring (8.15, 8.16) missing from audit coverage; an ISO 9001 item mapped into clause 10.2.

**Interview angle:** Walk through AUD03-F01: population, test, finding, grade, correction, root cause, effectiveness test.

---

### Milestone 7 — Management review (036–040)

**Purpose.** Clause 9.3: top management reviews the ISMS and makes decisions.

**Documents:** 036 Procedure; 037 Agenda and Inputs; 038 Minutes Template; 039 Actions Register; 040 Summary Template.

**Steps**

1. **Set the frequency, chair (the MD), quorum and attendees.**
2. **Map every required input (9.3.2) to a source document:** (a) status of previous actions; (b) changes in external and internal issues; (c) changes in interested parties' needs; (d) performance feedback, covering nonconformities and corrective actions, monitoring results, audit results and objectives; (e) feedback from interested parties; (f) risk assessment results and treatment status; (g) opportunities for improvement.
3. **Define the outputs (9.3.3):** decisions on improvement and on any changes to the ISMS, recorded with owners and dates.
4. **Prepare the agenda with the decisions needed** (D-01 to D-08), so the meeting decides rather than discusses.

**Key considerations**

- **A management review is evidenced by minutes and decisions,** not by an agenda.
- **Only record actions from decisions actually taken.**

**Lesson from the portfolio:** MR-2027-01 was prepared but **never recorded as held.** The readiness work at first assumed it had happened, then corrected every affected document. A missing management review is likely to be a Major nonconformity.

**Interview angle:** "What does an auditor look for in management review?" All seven inputs, decisions as outputs, and follow-up of actions.

---

### Milestone 8 — Monitoring and measurement (041–044)

**Purpose.** Clause 9.1: decide what to measure, how, when, and who analyses and evaluates the results.

**Documents:** 041 Procedure; 042 KPI Register (21 KPIs); 043 Measurement Plan; 044 Dashboard (August 2027).

**Steps**

1. **Start from objectives and Very High risks,** not from data that is easy to collect.
2. **Define each KPI:** formula, source system, frequency, target, threshold (Red, Amber, Green), owner, and the requirement it comes from.
3. **Write the counting rules:** a missing record counts as a failure in the numerator and stays in the denominator; no events is reported as "No events".
4. **Set hard limits** that override percentages. A single critical item breaching them is escalated whatever the percentage.
5. **Separate the roles:** collecting, analysing and evaluating are done by different people (9.1(d)–(f)).
6. **Validate before reporting:** trace the KPI back to its source records.

**Key considerations**

- **A good percentage doesn't prove a control works;** audit re-performance does.
- **Validation is a control in itself.** The mock Stage 1 audit later found three KPIs had passed validation without supporting records (KPI-14, 18, 20).

**Caught in the drafts:** "required timeframe" left undefined (now the end of the last working day); a training target of 100% that contradicted the charter's 95%; an activity measure (incident acknowledgement) instead of outcomes; "closed" not meaning verified effective.

**Interview angle:** Give a good KPI and a bad one, and explain the "missing records count as failures" rule.

---

### Milestone 9 — Improvement (045–048)

**Purpose.** Clause 10: fix nonconformities, remove causes, and improve.

**Documents and order**

| Step | Document | Key content |
| --- | --- | --- |
| 1 | 045 Continual Improvement Procedure | Triage; priority by mandatory, benefit and effort |
| 2 | 046 Nonconformity and Corrective Action Procedure | Correction vs corrective action vs verification |
| 3 | 047 Improvement Register | Only true improvements; everything else routed |
| 4 | 048 Root Cause Analysis RCA-01 | A worked investigation of a possible repeat |

**Steps**

1. **Triage every item first.** Is a requirement unmet? → nonconformity (034). Is a risk above target? → treatment plan (015). Already decided? → its own register. Otherwise → improvement (047). In the portfolio, 6 of 8 proposed "improvements" turned out to belong elsewhere.
2. **For a nonconformity, separate:**
    - **correction:** disable the account, check for use;
    - **corrective action:** remove the cause, for example a mandatory contract end date;
    - **effectiveness verification:** re-test the whole population later.
3. **Do root cause analysis with evidence.** Never stop at "human error"; ask what allowed the error. Use 5 Whys, fishbone, process mapping or trend analysis.
4. **Use "is / is not" analysis:** compare the failing cases with the working ones. In RCA-01, only contractors failed, which ruled out "no workflow" as the cause.
5. **Test hypotheses rather than assume.** RCA-01 set three (H1 timing, H2 incomplete backfill, H3 early terminations), each with a test and a consequence.
6. **Run an extent check,** recorded even when nothing is found.
7. **Verify with someone independent,** over an observation period long enough for the problem to recur.

**Key considerations**

- **Repeat nonconformities get escalated** and may be re-graded.
- **If verification fails, reopen** with a new root cause analysis.

**Caught in the drafts:** nonconformities listed as improvements; "human error" as a root cause; the auditor writing the root cause.

**Interview angle:** "Correction or corrective action?" Use RCA-01 to show both, plus verification.

---

### Milestone 10 — Business continuity and recovery (049–054)

**Purpose.** Annex A 5.29, 5.30, 8.13, 8.14: keep essential activities running and recover safely.

**Documents and order**

| Step | Document | Key content |
| --- | --- | --- |
| 1 | 049 BIA | Activities, impact over time, RTO, RPO, MTPD, gaps |
| 2 | 052 Recovery Objectives | System-level targets derived from the BIA |
| 3 | 050 BCP | Activation, roles and deputies, workarounds, communication |
| 4 | 051 DRP | Recovery paths by scenario, restore order, clean restore point |
| 5 | 053 Exercise Plan EX-01 | Tabletop with measurable objectives and timed injects |
| 6 | 054 Restore Test BRT-01 | Template with exact start and stop points |

**Steps**

1. **List business activities, not systems.** Identity, cloud and backup are resources that activities depend on.
2. **Rate the impact over time** (1 hour, 4 hours, 1 day, 3 days) on the risk matrix's 1–5 impact scale.
3. **Derive the objectives by rule:** RTO is the latest point before impact reaches 4; MTPD is when it reaches 5; RTO must be shorter than MTPD.
4. **Derive system objectives:** a system's RTO is the shortest RTO of the activities that depend on it.
5. **Compare targets with demonstrated capability.** A target is not a capability. Record the gaps, such as backups held in the same region as the platform.
6. **Plan by scenario:** a regional outage means failing over; ransomware means **don't** fail over, but rotate credentials and restore from a clean point before the compromise.
7. **Test with exact measures:** the RTO clock stops when the business confirms the service works, not when the restore job ends. Pass only if every item passes.

**Key considerations**

- **Restore identity first.** Nobody can restore a platform without being able to sign in.
- **A backup job succeeding doesn't prove recovery;** only a measured restore does.
- **A clean restore point may be older than the RPO.** That is an MD decision, and customers must be told.

**Caught in the drafts:** resources listed as activities; an RTO equal to the MTPD (no margin); identity restored after the databases; one test covering four systems.

**Interview angle:** "We have backups, so we're fine." Explain why that isn't enough.

---

### Milestone 11 — Supplier and third-party risk (055–060)

**Purpose.** Annex A 5.19–5.23: know your suppliers, assess them in proportion to risk, and monitor them.

**Documents and order**

| Step | Document | Key content |
| --- | --- | --- |
| 1 | 055 Supplier Register | 16 suppliers; tiers from the policy; gaps |
| 2 | 056 Risk Methodology | Tiering by exposure; risks scored on the 5×5 matrix |
| 3 | 057 Questionnaire | Part A by Northstar; evidence for every "Yes"; knock-outs |
| 4 | 058 Assessment Register | Evidence, credit, findings and decisions |
| 5 | 059 Review Procedure | Monitoring, incidents, changes, exit |
| 6 | 060 Assurance Report | Q3 2027 position and decisions needed |

**Steps**

1. **Build the register from several sources:** the asset register, Finance's paid-supplier list and Entra ID guest accounts, not just people's memory.
2. **Tier using the policy rules:** Critical (customer data, privileged access, or platform dependency), High, Standard. **Unknown facts mean the higher tier.**
3. **Score supplier risks on the same 5×5 matrix as every other risk.** A separate 3×3 scale would make results incomparable (clause 6.1.2(b)).
4. **Separate exposure from assurance:** exposure (data, access, dependency) sets the tier and impact; assurance (certificates, contracts, resilience) affects likelihood.
5. **Weigh evidence:**
    - questionnaire answers alone: no credit;
    - a certificate or SOC 2 Type II report **whose scope covers the service:** full credit;
    - Northstar's own checks in its own tenant: the strongest evidence.
6. **Monitor between reviews:** certificate expiries, guest accounts, sub-processor notices, outages and news.
7. **Report honestly:** the Q2 KPI said 80%; with no records found, the true position was 0 of 7.

**Key considerations**

- **Sub-processors must be notified to customers before they process customer data.** That cannot be accepted as a risk; it must be corrected.
- **Concentration risk** (one supplier for platform, identity and email) is handled through continuity planning.

**Caught in the drafts:** Critical suppliers under-tiered; a second, conflicting review schedule; risk ratings recorded before any assessment.

**Interview angle:** The IT support supplier challenge: reduce the access requested, ask for independent evidence, and let the MD accept impact-5 risk.

---

### Milestone 12 — Certification readiness and mock audit (061–068)

**Purpose.** Bring everything together: would the ISMS pass Stage 1 and Stage 2?

**Documents and order**

| Step | Document | Key content |
| --- | --- | --- |
| 1 | 061 Clause Gap Assessment | 25 clause requirements: design and operation |
| 2 | 062 Annex A Readiness | All 93 controls |
| 3 | 063 SoA Validation | 12 checks performed |
| 4 | 064 Evidence Index | 38 items: documented, operational, effectiveness |
| 5 | 065 Readiness Report | Conclusion; Stage 1 and Stage 2 entry criteria |
| 6 | 066 Mock Stage 1 | Independent baseline audit |
| 7 | 067 Mock Stage 2 | Plan and 18-test programme |
| 8 | 068 Remediation Tracker | 26 gaps pointing to their home registers |

**Steps**

1. **Assess on two dimensions:** design (approved, drafted, none) and operation (evidenced, partial, none, unknown). One scale can't show "working but unapproved".
2. **Cover everything:** all 25 clause requirements and all 93 controls, not a sample.
3. **Validate the SoA by performing the checks,** not listing them.
4. **Index the evidence:** for each requirement, the source system, period, owner and status. Missing stays missing; never create records after the fact.
5. **Write a definite conclusion** with entry criteria: Stage 1 checks the documented ISMS is ready; Stage 2 checks it works.
6. **Get an independent mock audit.** The mock Stage 1 confirmed the self-assessment and found what it missed: KPI validation weaknesses.
7. **Track remediation without duplicating:** point to existing registers; create new actions only for gaps with no other home.

**Key considerations**

- **Understating evidence is as wrong as overstating it.** Credit what genuinely works.
- **A mock auditor never declares certification.** Only a certification body decides.
- **Check your own assumptions against the records.** The management review correction was found exactly this way.

**The conclusion:** not ready for Stage 1. Core documents are unapproved, there is no management review, 8 of 9 audits have no records, and recovery and supplier assurance are unevidenced. Every gap has an owner and a date.

**Interview angle:** "How would you prepare an organisation for certification?" Gap assessment, evidence index, independent mock audit, entry criteria, remediation.

---

## Part 3 — Using this in practice

### A checklist for any new ISMS document

- [ ] Which clause or control is it for, and what exactly does that require?
- [ ] Does it use the organisation's real roles, with one owner per item?
- [ ] Are the IDs, scales and numbers consistent with earlier documents?
- [ ] Is every commitment testable: a time, a frequency, a condition?
- [ ] Does anything duplicate an item held in another register?
- [ ] Does anyone verify their own work, or does the GRC Analyst accept risk?
- [ ] Are missing records and "no events" treated correctly?
- [ ] Do the summary totals match the tables?
- [ ] Is there a change log saying what changed and why?
- [ ] Is it clearly labelled as simulated, if it is portfolio work?

### Five stories worth knowing for interviews

| Story | Shows |
| --- | --- |
| A leaver disabled late, then a second case: AUD03-F01 to RCA-01 | Audit testing, grading, root cause analysis, hypothesis testing |
| The supplier KPI reset from 80% to 0 of 7 | Evidence over assertion; honest reporting |
| The ISO 9001 clause 10.2 mapping error | Knowing the standard precisely; correcting openly |
| The management review assumed held, then corrected across eight documents | Checking assumptions against records |
| The mock auditor finding KPI validation weaknesses | Why independence matters |

---

*Simulated portfolio. Northstar Digital Solutions Ltd is fictional; the documents demonstrate method, not a real implementation or certification.*
