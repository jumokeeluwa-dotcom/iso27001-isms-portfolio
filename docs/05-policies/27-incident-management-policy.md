# Northstar Digital Solutions Ltd — Incident Management Policy and Procedure

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-027 |
| Version | 0.2 — Draft for MD approval |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (Annex A 5.24, 5.25, 5.26, 5.27, 5.28, 6.8) |
| Parent policy | [NSD-ISMS-022 Information Security Policy](22-information-security-policy.md) |
| Policy owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Annually, after each exercise, and after every Severity 1 incident |
| Classification | Internal. Incident records are Restricted (AST-017) |

---

## 1. Purpose

Security events and incidents are reported, assessed, contained, investigated, notified, recovered from and learned from in a consistent and timely way. Northstar must also meet its notification duties: to customers as a **processor**, and to regulators as a **controller**.

## 2. Scope

Everyone covered by NSD-ISMS-022, and suppliers involved in an incident (NSD-ISMS-026 §10).

## 3. Roles

| Role | Responsibility |
| --- | --- |
| Anyone | Reports immediately |
| **Incident manager:** GRC Analyst, with the IT Manager as deputy | Records, triages, coordinates and keeps the timeline |
| **Technical lead:** IT Manager (corporate IT) or Head of Engineering (platform) | Containment, investigation and recovery |
| **Data Protection lead** | Breach assessment and notification decisions |
| **Managing Director** | Decides on Severity 1 incidents; approves external communication |

## 4. Reporting

1. **Report immediately** through the security reporting channel: the security mailbox, the Report button in Outlook, or the out-of-hours phone number for anything urgent.
2. Report even when unsure. Examples: suspected phishing or account compromise; lost or stolen devices; unauthorised access; malware or ransomware; accidental disclosure; unusual system activity; loss of service.
3. Suppliers report to Northstar within 24 hours of discovery (NSD-ISMS-026 §4).

## 5. Severity and response times

| Severity | Examples | Triage starts | MD informed |
| --- | --- | --- | --- |
| **1 — Critical** | Confirmed breach of customer data; ransomware; platform outage beyond the 4-hour RTO | Within 1 hour, at any time | Immediately |
| **2 — High** | Account compromise with access to Confidential or Restricted data; suspected breach | Within 4 hours | Same day |
| **3 — Medium** | Contained malware; lost encrypted laptop | Next working day | Monthly report |
| **4 — Low** | Phishing email reported and not clicked | Within 5 working days | Monthly report |

Severity is set at triage and reviewed as facts emerge.

## 6. Containment

Containment is proportionate and coordinated, and **preserves evidence before anything is wiped or rebuilt.** Typical actions include:

- disabling accounts (without deleting them);
- revoking sessions, tokens and keys;
- isolating devices through endpoint security;
- blocking indicators of the attack;
- restricting access;
- engaging Microsoft or other providers.

## 7. Investigation and evidence (Annex A 5.28)

1. Logs and records are exported **before** they expire: sign-in logs, audit and application logs, endpoint alerts, emails and access records.
2. Evidence is stored in the Restricted incident repository with access limited to the incident team. Every hand-over is recorded, which keeps the **chain of custody** intact.
3. The incident manager keeps a timestamped timeline from the first report.

## 8. Personal data breaches and notification

The Data Protection lead completes a **breach assessment within 24 hours** of an incident involving personal data. Duties depend on Northstar's role:

| Northstar's role | Data affected | Duty |
| --- | --- | --- |
| **Processor** | Customer data in the platform | Notify each affected customer (the controller) **without undue delay**, and within the timescale in their DPA. The customer decides whether to notify regulators and individuals. Northstar supports them with facts |
| **Controller** | Employee, finance and marketing data | Notify the ICO, or the lead EU supervisory authority for EU data, within **72 hours** of becoming aware, where the breach is reportable. Inform affected individuals where there is a high risk to them |

**Other notifications assessed for every Severity 1 or 2 incident:**

- financial services customers, under DORA-related contract terms (IP-03);
- the cyber insurer, under the policy conditions (IP-13);
- law enforcement or NCSC, where appropriate (IP-15).

Every notification decision, **including a decision not to notify**, is recorded with its reasons.

## 9. Recovery

Systems are restored only once they are confirmed clean. Restoration follows the BC/DR arrangements (NSD-ISMS-028), and the business owner approves the return to normal service.

## 10. Closure and lessons learned (Annex A 5.27)

1. Each incident record includes:
    - description and timeline;
    - affected assets and services;
    - severity and impact;
    - containment and recovery actions;
    - evidence references;
    - root cause;
    - notification decisions and reasons;
    - corrective actions;
    - closure approval.
2. A **lessons-learned review** is held within **10 working days** of closing every Severity 1 or 2 incident.
3. Lessons are turned into actions:
    - corrective actions go in the corrective action log (clause 10.2);
    - affected risks are re-scored (NSD-ISMS-014);
    - this procedure is updated where needed.
4. Incident trends are reported to each Steering Group meeting and to management review.

## 11. Testing

- A **tabletop exercise** is run at least annually, and after any major change to the platform or organisation (T-18.1). The pass criterion is a breach assessment completed within 24 hours (NSD-ISMS-021, 5.24).
- Contact lists are checked every quarter.

## 12. Measures

| Measure | Target |
| --- | --- |
| Severity 1 triage started within 1 hour | 100% |
| Breach assessments completed within 24 hours | 100% |
| Customer notifications within DPA timescales | 100% |
| Severity 1 and 2 incidents with a lessons-learned review within 10 working days | 100% |

## 13. Related controls and risks

Annex A 5.24–5.28, 6.8 · Risks R-18, plus every risk whose scenario ends in an incident · Actions T-18.1 and the proposed T-18.2 (lessons learned)

## 14. Approval and change log

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-022) | Incident management procedure |
| 0.2 | Numbered NSD-ISMS-027 and retitled "Policy and Procedure". Owner changed from "Security Lead" to the GRC Analyst as incident manager; approver to the MD. Added severity levels with response times, roles and an out-of-hours channel. Added the processor-versus-controller notification table: customers notified under their DPAs, and the ICO or EU authority within 72 hours for Northstar's own data. Added DORA, insurer and law enforcement notifications, a 24-hour breach assessment target and chain of custody. Lessons-learned review within 10 working days, which provides the Annex A 5.27 process the SoA found missing. Annual tabletop exercise. The draft's accurate description of the 72-hour rule is kept. |

---

*Portfolio note: Draft only. This is not an approved or implemented procedure.*
