# Northstar Digital Solutions Ltd — Business Continuity Plan

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-050 (asset AST-019, with NSD-ISMS-051) |
| Version | 0.2 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 5.29, 5.30, 5.24–5.26; clause 8.1 |
| Status | **Simulated. Not activated, approved or exercised** |
| Related documents | [NSD-ISMS-049 BIA](49-business-impact-analysis.md) · NSD-ISMS-051 Disaster Recovery Plan · [NSD-ISMS-027 Incident Management](../05-policies/27-incident-management-policy.md) · [NSD-ISMS-028 Backup and Business Continuity Policy](../05-policies/28-backup-business-continuity-policy.md) |
| Owner | Managing Director (owner of AST-019) |
| Plan coordinator | Information Security / GRC Analyst |
| Approver | Managing Director |
| Copies | SharePoint, plus an **offline copy** held by the MD, the GRC Analyst, the Head of Engineering and the IT Manager, usable when Microsoft 365 is down (NSD-ISMS-028 §7) |
| Classification | Confidential |

---

## 1. Purpose and how this plan fits

This plan keeps Northstar's essential activities (NSD-ISMS-049) running, or running in a reduced form, while normal operations are disrupted.

| Plan | Answers | Led by |
| --- | --- | --- |
| Incident management (NSD-ISMS-027) | What happened, and how is it contained? | Incident manager (GRC Analyst) |
| **This BCP** | How does the business keep serving customers and staff meanwhile? | MD |
| Disaster recovery (NSD-ISMS-051) | How are the systems and data restored safely? | Technical leads |

Most disruptions start as incidents. **One incident timeline is kept,** by the incident manager (NSD-ISMS-027 §7), and the BCP decisions are logged in it. Two separate logs would soon disagree.

## 2. Activation

**The plan is activated when any of these occurs:**

| Trigger | Examples |
| --- | --- |
| A Severity 1 incident (NSD-ISMS-027 §5) | Ransomware; confirmed customer data breach |
| An activity is expected to exceed its **RTO** in NSD-ISMS-049 | Platform outage with no fix expected within 4 hours; customer channel unavailable for 1 hour |
| Microsoft or another Critical supplier has an outage affecting A1, A2, A3 or A5 | Azure regional outage; Entra ID outage |
| The office is unusable for more than 1 working day | Fire, flood, power loss |
| Both technical leads (Head of Engineering and IT Manager) unavailable during an incident | Illness, travel, a single event affecting both |

**Who activates:** the MD. If the MD cannot be reached within 30 minutes, the Head of Engineering (platform) or the IT Manager (corporate IT) activates the plan and informs the MD as soon as possible.

**Time targets:** activation decision within **2 hours** of a Severity 1 incident being declared. A decision **not** to activate is also recorded, with the reason.

## 3. Roles

Every role has a deputy, because a plan that depends on one person fails when that person is the one affected.

| Role | Held by | Deputy | Responsibility |
| --- | --- | --- | --- |
| Continuity lead | Managing Director | Head of Engineering | Activates; sets priorities; approves spend, external communication and any security deviation |
| Incident manager and plan coordinator | GRC Analyst | IT Manager | Keeps the single timeline and decision log; coordinates; tracks actions |
| Technical lead, platform | Head of Engineering | To be named (proposed action MRA-2027-06) | Platform recovery (NSD-ISMS-051) |
| Technical lead, corporate IT | IT Manager | To be named (proposed action MRA-2027-06) | Identity, Microsoft 365, endpoints (NSD-ISMS-051) |
| Customer communication | Customer Support Manager | Sales lead | Runs the customer channel; drafts updates for MD approval |
| Key customer accounts | Sales lead | Customer Support Manager | Direct contact with financial services and other key customers |
| Notifications and data protection | Data Protection lead | GRC Analyst | Breach assessment; notification decisions (NSD-ISMS-027 §8) |
| Staff and welfare | HR Manager | Finance Manager | Staff contact and wellbeing; alternative working; leaver fallback |
| Suppliers and emergency spend | Finance Manager | MD | Supplier escalation; insurer contact; emergency purchases |

**Gap:** until a deputy is named (proposed action MRA-2027-06), the two technical leads have no named deputy. If both are unavailable, that is itself an activation trigger, and the MD engages external support.

## 4. Response stages

| Stage | Actions | Who | Time target |
| --- | --- | --- | --- |
| **1. Assess** | Confirm the disruption; identify affected activities (NSD-ISMS-049 §4); set incident severity | Incident manager, technical leads | Triage within 1 hour for Severity 1 (027 §5) |
| **2. Activate** | Decide whether to activate; set priorities from the BIA recovery order (049 §7); assign roles; open the decision log | MD | Within 2 hours of a Severity 1 |
| **3. Keep essential activities running** | Start the workarounds in section 5; first customer notice; brief staff | Activity owners; Customer Support Manager | First customer notice within **1 hour** of activation |
| **4. Recover** | NSD-ISMS-051 restores systems. Business owners confirm each activity works before it is declared restored | Technical leads; activity owners | Within each activity's RTO |
| **5. Return to normal** | MD approves the return; workarounds stopped; any data entered manually is reconciled; outstanding issues recorded | MD; activity owners | — |
| **6. Learn** | Lessons-learned review; actions triaged into NSD-ISMS-034 or 047 | Incident manager | Within 10 working days of closure (027 §10) |

## 5. Continuity arrangements by activity

| Activity (NSD-ISMS-049) | Workaround while systems are down | Owner |
| --- | --- | --- |
| A1 Customer platform | Failover or restore (NSD-ISMS-051). No manual workaround exists for a SaaS platform, so A2 matters most while A1 is down | Head of Engineering |
| A2 Customer communication | A **status channel and customer contact list that do not depend on the platform or Microsoft 365**: contact list in the offline plan copy; phone for key accounts. *Not yet in place: see BIA gap G1* | Customer Support Manager |
| A3 Incident response | Out-of-hours phone number; offline copy of the incident procedure; break-glass access | GRC Analyst |
| A4 Emergency fixes | Emergency change route (NSD-ISMS-029 §5) | Head of Engineering |
| A5 Staff access | Work from home if the office is lost. If Entra ID or Microsoft 365 is down: phone tree from the offline contact list | IT Manager |
| A6 Finance | Payments through the bank's own service, with dual approval. **No changes to supplier bank details during a disruption,** because payment fraud targets organisations in crisis | Finance Manager |
| A7a Leaver notification | HR phones or texts the IT Manager or deputy with each leaver's name and last day; IT disables manually the same day and keeps a log. Closes BIA gap G6 and supports RCA-01 | HR Manager |

## 6. Communication

| Audience | Channel when normal systems are down | Who | Timing |
| --- | --- | --- | --- |
| Staff | Phone tree from the offline contact list | HR Manager | Within 1 hour of activation |
| Customers (all) | Status channel; email if available | Customer Support Manager, approved by the MD | First notice within 1 hour; updates at least every 2 hours until restored |
| Customers as controllers, if personal data may be affected | As set in each DPA | Data Protection lead | **Without undue delay,** and within DPA timescales (027 §8) |
| Financial services customers | Named contacts, under DORA-related contract terms (IP-03) | Sales lead | As the contract requires |
| Suppliers (Microsoft, others) | Support portal; account manager | Technical leads; Finance Manager | At activation |
| Cyber insurer | As set in the policy (IP-13) | Finance Manager | As the policy requires |
| ICO, EU authorities, NCSC, police | As required | Data Protection lead; MD | ICO within 72 hours where reportable (controller data) |

All external messages are factual, approved by the MD, and consistent with each other. Every notification decision, **including a decision not to notify,** is recorded with its reasons. The update intervals are proposals to be checked against the customer contracts (NSD-ISMS-005).

**After recovery, customers are told about any data loss.** If data was restored to an earlier point, they are told the window of lost data.

## 7. Security during disruption (Annex A 5.29)

Controls stay in force. MFA, access control, logging and encryption are not bypassed to speed things up (NSD-ISMS-028 §8). Any emergency deviation needs MD approval, is logged, and is reversed and reviewed afterwards. Personal contact details in the offline plan are kept to the minimum needed and are held securely.

## 8. Exercises

| Exercise | Scenario | Frequency | Pass criterion |
| --- | --- | --- | --- |
| Tabletop | Rotated: ransomware with backups attacked (R-14); Azure regional outage (R-09); Entra ID or M365 outage (EXT-05); both technical leads unavailable; office flooded (EXT-12, climate) | Annually, combined with the incident exercise (T-18.1) | Activation decision within 2 hours; first customer notice within 1 hour; breach assessment within 24 hours |
| Communication test | Phone tree and customer contact list | Quarterly, with the contact list check (027 §11) | All staff reached within 1 hour; no out-of-date contacts |
| Technical tests | Restore and failover | As in NSD-ISMS-051 §8 | Within RTO and RPO |

Each exercise records its objectives, participants, measured times, what went wrong, and actions. Actions are triaged into NSD-ISMS-034 or 047. An exercise that finds nothing is reviewed for whether it was realistic.

## 9. Maintenance

| Activity | When |
| --- | --- |
| Full plan review | Annually; after every activation or exercise; after major organisational, supplier or platform change |
| Contact lists and offline copies checked | Quarterly |
| BIA changes reflected in sections 5 and 6 | Within 10 working days of BIA approval |

## 10. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-046) | First draft |
| 0.2 | Numbered NSD-ISMS-050. Owner changed from "Operations Director", not a charter role, to the **MD,** who owns AST-019; approver changed from "Senior Management" to the MD. Roles mapped to charter roles: "Incident Coordinator" became the GRC Analyst, as incident manager under NSD-ISMS-027; "Security Lead" removed; "Communications Lead" split between the Customer Support Manager, Sales lead and Data Protection lead, with the MD approving; "department managers" named. Deputies added. "May be considered" and "significantly" replaced with concrete triggers linked to BIA RTOs, a named activator and time targets. One shared timeline with the incident process. Workarounds for each BIA activity, including the leaver fallback and a freeze on supplier bank detail changes. Communication table with channels that work without Microsoft 365, the processor notification duty and data loss disclosure. Exercise scenarios include climate (EXT-12). "Periodically" replaced with set review points. |

---

*Portfolio disclaimer: Simulated continuity plan. It has not been activated, approved or exercised.*
