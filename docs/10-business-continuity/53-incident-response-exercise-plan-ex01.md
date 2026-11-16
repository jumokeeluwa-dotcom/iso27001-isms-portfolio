# Northstar Digital Solutions Ltd — Incident Response Exercise Plan EX-01

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-053 (exercise EX-01) |
| Version | 0.2 — Plan for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 5.24–5.27, 5.29, 5.30; clauses 8.1, 9.1 |
| Status | **Simulated plan. The exercise has not taken place. No result in this document is a result** |
| Exercise type | Tabletop: discussion only, no live systems touched |
| Planned date | Wednesday 8 December 2027, 10:00–13:30, UK office with remote joining |
| Treatment action | Delivers T-18.1 (R-18), due **1 Mar 2027**. No exercise record exists in the portfolio, so T-18.1 is **overdue,** not complete |
| Documents exercised | [NSD-ISMS-027 Incident Management](../05-policies/27-incident-management-policy.md) · [NSD-ISMS-050 BCP](50-business-continuity-plan.md) · [NSD-ISMS-051 DRP](51-disaster-recovery-plan.md) · [NSD-ISMS-049 BIA](49-business-impact-analysis.md) |
| Plan owner | Information Security / GRC Analyst (owner of T-18.1) |
| Facilitator and evaluator | Internal auditor (NSD-ISMS-030): independent of every incident role |
| Approver | Managing Director |
| Classification | Confidential (describes attack paths and known weaknesses) |

---

## 1. Why the facilitator is not the GRC Analyst

The GRC Analyst is Northstar's incident manager (NSD-ISMS-027 §3), so they are one of the people being tested. If they also ran and scored the exercise, they would be marking their own work. The GRC Analyst therefore plans the exercise and plays the incident manager; the **internal auditor** facilitates, keeps the exercise clock and evaluates. T-18.1 evidence is then verified by the internal auditor or the MD, as NSD-ISMS-015 requires for actions the GRC Analyst owns.

## 2. Objectives and pass criteria

Each objective is tested against a requirement Northstar has already written down. "Participants understand their roles" cannot be measured; "triage started within 1 hour" can.

| # | Objective | Pass criterion | Source |
| --- | --- | --- | --- |
| O1 | Report and triage | Report through the security channel; triage started within **1 hour** (scenario time) | 027 §4–5 |
| O2 | Severity and escalation | Severity 1 declared when the facts support it; MD informed **immediately** | 027 §5 |
| O3 | Evidence | Logs preserved **before** containment changes them | 027 §7; 051 §5 |
| O4 | Containment | Sessions revoked, account disabled, attacker's persistence removed and secrets rotated, **in that order**, using break-glass access where needed | 051 §5; T-13.2 |
| O5 | Breach assessment | Completed within **24 hours** of awareness. **This is the T-18.1 pass criterion** | 027 §8; R-18 |
| O6 | Notification decisions | A recorded decision, with reasons, for each affected controller, financial services customers (DORA terms), the insurer and NCSC, **including decisions not to notify** | 027 §8 |
| O7 | Continuity | BCP activation decision within **2 hours** of Severity 1; first customer notice within **1 hour** of activation | 050 §2, §4 |
| O8 | Recovery | No failover of an attack; clean restore point **before** the compromise; credentials rotated before restoring | 051 §4–5 |
| O9 | Deputies | Response continues when a key person is the one affected | 027 §3; 050 §3 |
| O10 | Records | One timeline, kept by the incident manager | 027 §7; 050 §1 |

Each objective is rated **Met, Partly met** or **Not met,** with the evidence: what was said or decided, and when in scenario time.

## 3. Participants

| Participant | Plays | Note |
| --- | --- | --- |
| Managing Director | Continuity lead; Severity 1 decisions; external communication approval | |
| GRC Analyst | Incident manager | |
| Head of Engineering | Technical lead, platform; **acting** technical lead, corporate IT | Tests the deputy arrangement |
| IT Manager | Technical lead, corporate IT | **"Unavailable" for injects 1 to 3:** the compromised account is theirs, and they are on leave. Joins from inject 4 |
| Data Protection lead | Breach assessment and notification decisions | Owner of R-18 |
| Customer Support Manager | Customer communication | |
| Sales lead | Key customer accounts, including financial services | |
| Finance Manager | Insurer contact; emergency spend | |
| HR Manager | Staff communication | |
| Internal auditor | Facilitator, timekeeper and evaluator | Does not take part in decisions |

Roles in the draft that are not in the charter were mapped: "Incident Coordinator" is the GRC Analyst; "Security Lead" and "Cloud Administrator" are covered by the technical leads; "Privacy Lead" is the Data Protection lead; "Communications Lead" is split between the Customer Support Manager and Sales lead, with the MD approving; "Senior Management" is the MD.

## 4. Scenario

On a **Friday evening,** an attacker steals the session of the IT Manager's administrator account through a phishing page that relays the sign-in, so MFA is passed (an "adversary-in-the-middle" attack). The IT Manager is on annual leave. The attacker uses the account to activate a privileged role.

The scenario tests risk **R-13** (administrator credentials stolen, rated Very High), and through it **R-01, R-14 and R-18.** It also tests two things the portfolio already marks as weak: database audit logging (R-01, *Untested*) and backup protection (T-14.1, T-14.2, completion not recorded).

Scenario time is compressed. Each inject states the scenario time, so the time targets in section 2 can be checked.

## 5. Injects

### Inject 1 — Friday 17:40 (T+0): unusual privileged activity

An alert shows the IT Manager's administrator account activating a privileged Azure role from an unfamiliar country. The IT Manager's out-of-office says they are on leave until Monday.

**Questions:**
- Who receives this alert at 17:40 on a Friday?
- How is it reported, and who triages it?
- How do you check with the IT Manager without using a channel the attacker may control, such as their Teams or email?
- What severity is it at this point?

**Expected:** report through the security channel; the GRC Analyst triages within 1 hour; contact the IT Manager by phone from the offline contact list; Severity 2 at first (account compromise with access to Restricted data).

### Inject 2 — Friday 18:25 (T+45 min): confirmed compromise

The IT Manager, reached by phone, confirms they did not sign in. Logs show the attacker has created a new app registration with its own secret and a role assignment, giving them a way back in even if the account is disabled.

**Questions:**
- What do you preserve first?
- In what order do you contain?
- Who leads technically while the IT Manager is unavailable?
- Is this now Severity 1, and who tells the MD?

**Expected:**
- Export the logs before changing anything.
- Revoke sessions, disable the account, and remove the app registration and its role.
- Rotate Key Vault secrets the account could reach.
- Use break-glass access if needed.
- The Head of Engineering leads as acting technical lead.
- Severity 1 is declared and the MD informed immediately.

### Inject 3 — Friday 20:40 (T+3 h): possible data exposure

Database logs show large export queries against the **EU** customer database during the attacker's session. They affect two customers, one of them a financial services customer. Part of the log period is missing, because database audit logging was never tested.

**Questions:**
- Who starts the breach assessment, and by when must it be complete?
- What is Northstar's role for this data?
- Whom must Northstar notify, and by when?
- How do you decide the scope when logs are incomplete?
- Who records a decision not to notify someone?

**Expected:**
- The Data Protection lead starts the breach assessment; the 24-hour deadline runs from awareness (T+45 min).
- Northstar is a **processor:** it notifies both customers as controllers **without undue delay** and within their DPA terms, and the customers decide on notifying regulators.
- The DORA terms for the financial services customer are checked.
- The insurer is told under the policy terms.
- With incomplete logs, the scope is assumed to be the worst credible case until it can be narrowed.
- Every decision is recorded with reasons.

### Inject 4 — Saturday 00:10 (T+6.5 h): service disruption

The attacker, still active through a second route not yet found, deletes production resources in the UK region. The UK platform is down. Logs show attempts to delete the backup vault.

**Questions:**
- Is the BCP activated, by whom, and by when?
- Is the DR path failover or restore?
- Were the backups protected?
- When do customers hear?
- What does the IT Manager, now joining, do first?

**Expected:**
- The MD activates the BCP within 2 hours.
- This is an attack, so **do not fail over** into infrastructure the attacker may also control; contain first, then rebuild and restore (051 §4).
- Confirm whether immutability (T-14.1) and the separate backup role (T-14.2) are actually in place.
- First customer notice within 1 hour of activation, approved by the MD, through a channel that does not depend on the platform (BIA gap G1).
- The IT Manager is **not** given back admin access until their account and devices are confirmed clean.

### Inject 5 — Saturday 18:00 (T+24 h 20 min): external pressure

The financial services customer's CISO emails the Sales lead asking whether their data was taken. A post on LinkedIn mentions "a Northstar outage". The breach assessment is due in 25 minutes.

**Questions:**
- Who replies, and with what?
- Is the breach assessment on time?
- Does the reply match what the notification already said?

**Expected:** one approved, factual message; no speculation; the Sales lead replies only with MD-approved wording; the breach assessment is completed or escalated before the deadline.

### Inject 6 — Saturday 22:00 (T+28 h 20 min): recovery

The investigation finds the attacker's first access was **three days earlier.** DevOps propose restoring from the most recent backup, taken at 05:00 today.

**Questions:**
- Is that backup clean?
- What restore point do you choose, and what data is lost?
- Who decides to accept data loss beyond the 1-hour RPO?
- Who validates security, and who approves the return to service?
- What do customers need to be told?

**Expected:**
- The 05:00 backup was taken while the attacker was present, so it is **not clean.**
- Choose the newest backup **before** the first access, rotate credentials before restoring, and rebuild with the current security baseline.
- The data loss beyond the RPO is an MD decision.
- The GRC Analyst reviews the security validation; the MD approves the return.
- Customers are told the window of lost data.

## 6. Running the exercise

| Time | Activity |
| --- | --- |
| 10:00 | Introduction and ground rules |
| 10:15 | Injects 1–3 |
| 11:30 | Break |
| 11:45 | Injects 4–6 |
| 13:00 | Hot debrief: each participant states one thing that worked and one that did not |
| 13:30 | Close |

**Ground rules:**
- Discussion only. **No live system, account or customer is contacted.**
- Every exercise document is marked **"EXERCISE"**, so nothing can be mistaken for a real incident.
- Answers must use the documents as written. Where a document is silent, say so, rather than improvising a better answer than Northstar has. That gap is a finding.
- The aim is to test the arrangements, not individuals. Findings are about the process.
- If a real incident occurs, the exercise stops.

**Before the exercise:**
- Participants read 027, 050 and 051 (one week before).
- The offline contact list is checked.
- The MD approves this plan by 24 Nov 2027.

## 7. After the exercise

| Output | Who | When |
| --- | --- | --- |
| Exercise report EX-01: rating and evidence for each objective, timeline, gaps | Internal auditor, with the GRC Analyst | Within **10 working days** (22 Dec 2027) |
| Each gap triaged under NSD-ISMS-045 §2: a requirement not met goes to NSD-ISMS-034; a weak but compliant arrangement goes to NSD-ISMS-047; a changed risk goes to NSD-ISMS-014 | GRC Analyst | With the report |
| T-18.1 status updated: complete **only if** O5 is rated Met | GRC Analyst, verified by the internal auditor or MD | With the report |
| Summary to management review (input 9.3.2(c)) | GRC Analyst | Next management review |

An exercise that finds nothing is reviewed for whether it was realistic. With database logging untested and backup protection unconfirmed, this scenario is designed to find something.

## 8. Records

Kept for 3 years, classified Confidential: this plan, the inject pack, attendance, the facilitator's timeline and notes, decisions in scenario time, the evaluation, the report, and the resulting actions.

## 9. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-049) | Draft exercise plan EX-001 with five injects |
| 0.2 | Numbered NSD-ISMS-053 (EX-01) and linked to T-18.1, which the portfolio shows as **overdue** (due 1 Mar 2027, no record). Owner changed from "Security Lead" to the GRC Analyst; the internal auditor facilitates and evaluates, so the incident manager is not scoring themselves. Participants mapped to charter roles. Evaluation criteria replaced with ten objectives and pass criteria taken from 027, 050 and 051. Scenario made specific: an adversary-in-the-middle attack on the IT Manager's admin account on a Friday evening, testing R-13, R-01, R-14 and R-18 and the deputy arrangements. Injects timed in scenario time with expected actions; added persistence through an app registration, incomplete database logs, backup deletion attempts, external pressure and a backup that is not clean. Logistics, ground rules, outputs, triage of gaps and record retention added. |

---

*Portfolio disclaimer: Simulated exercise plan. It is not evidence that the exercise has been conducted.*
