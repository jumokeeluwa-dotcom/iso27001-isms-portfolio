# Northstar Digital Solutions Ltd — Annex A Control Readiness Review

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-062 |
| Version | 1.0 — Simulated review |
| Standard | ISO/IEC 27001:2022 incl. Amendment 1:2024, Annex A (93 controls) |
| Status | **Simulated. Evidence is taken from earlier portfolio records only. A record not in the portfolio is treated as missing** |
| Evidence as at | 30 September 2027 |
| Inputs | [NSD-ISMS-019 SoA v1.0](../04-controls-and-soa/19-statement-of-applicability.md) · [NSD-ISMS-014 Risk register](../03-risk-management/14-risk-register.md) · [NSD-ISMS-044 Dashboard](../08-monitoring-and-measurement/44-performance-dashboard.md) · AUD-03 records (031–035) · [NSD-ISMS-034](../06-internal-audit/34-corrective-action-register.md) |
| Method | Same as the clause gap assessment ([NSD-ISMS-061](61-clause-gap-assessment.md) §2) |
| Reviewer | Information Security / GRC Analyst; independent check in the mock audits (066, 067) |
| Approver | Managing Director |
| Classification | Confidential |

---

## 1. Purpose and coverage

This review checks whether each Annex A control is ready to show to a certification auditor: designed, approved and operating with evidence. It accounts for **all 93.** A readiness review that skips controls cannot support a readiness decision.

| Group | Controls | Treatment here |
| --- | --- | --- |
| Assessed in the SoA (v1.0) | 48 | Reviewed one by one (section 4) |
| Awaiting assessment (SoA Wave 2, overdue since Jan 2027) | 45 | **Not ready:** applicability not yet decided. Readiness cannot be judged before applicability |
| **Total** | **93** | |

## 2. Method

Each control is rated on **design** (Approved, Drafted, None) and **operation** (Evidenced, Partial, None, Unknown), giving a readiness of Ready, Partly ready or Not ready (NSD-ISMS-061 §2).

Two separate dimensions keep design and operation apart, so a control that operates but is not approved is still visible.

**Operated by:** whether the control is operated by **Northstar**, **shared** with a supplier (for example, Azure provides the backup service and Northstar configures and tests it), or provided by a **supplier.** For shared controls, Northstar must evidence its own part and hold the supplier's assurance for the rest.

**Comparison with the SoA.** Where later evidence (AUD-03, the KPI dashboard, corrective actions) points to a different status from the SoA, the difference is listed in section 5 for the SoA validation (NSD-ISMS-063). This review does not change the SoA itself.

## 3. Result

| Readiness | Assessed controls (48) | All controls (93) |
| --- | --- | --- |
| Ready | 0 | 0 |
| Partly ready | 29 | 29 |
| Not ready | 19 | 64 (19 + the 45 Wave 2 controls) |

**No control is Ready,** because no supporting policy is approved. Approval alone would not make them Ready either: of the 29 Partly ready controls, none has complete evidence of operation.

**Strongest evidence:** 8.32 change management and 5.3 segregation (KPI-07: 42 of 42 deployments approved by a second person), 8.2 privileged access (KPI-04: no standing admin access), and the IAM controls tested in AUD-03.

**Weakest areas:** continuity and recovery (5.29, 5.30, 8.14: nothing tested), suppliers (5.19–5.22: no assessment records), legal requirements (5.31: no legal register) and network protection (8.20, 8.21: WAF not deployed).

## 4. Assessed controls

| Control | Title | Operated by | Design | Operation | Evidence (as at 30 Sep 2027) | Readiness | SoA v1.0 status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 5.1 | Policies for information security | Northstar | Drafted: 022–029 | Unknown | Policies not approved; yet KPI-20 reports 93% policy acknowledgement. **Conflict** | 🟧 Not ready | Planned |
| 5.2 | Information security roles and responsibilities | Northstar | Drafted: charter; 007 | Partial | Roles operated in AUD-03; owner acceptance not recorded | 🟨 Partly ready | Planned |
| 5.3 | Segregation of duties | Northstar | Drafted: 029 §5 | Partial | KPI-07: 42 of 42 deployments with second-person approval; payment and backup segregation untested | 🟨 Partly ready | Planned |
| 5.7 | Threat intelligence | Northstar | None | None | No defined source or review routine | 🟧 Not ready | To be assessed |
| 5.9 | Inventory of information and other associated assets | Northstar | Drafted: 006, 011 | Partial | Register exists; CRM missing (055 gap 3) | 🟨 Partly ready | Partially implemented |
| 5.10 | Acceptable use of information and other associated assets | Northstar | Drafted: 024 | Unknown | Acknowledgement of AUP not separately evidenced | 🟧 Not ready | Planned |
| 5.12 | Classification of information | Northstar | Drafted: 008 | None | Standard awaiting approval | 🟧 Not ready | Planned |
| 5.13 | Labelling of information | Shared | Drafted: 008 | None | Labels not deployed | 🟧 Not ready | Planned |
| 5.15 | Access control | Northstar | Drafted: 023 | Partial | AUD-03 tested IAM: 2 Minor findings (F01, F02) | 🟨 Partly ready | Partially implemented |
| 5.16 | Identity management | Northstar | Drafted: 023 | Partial | AUD03-F01; RCA-01 open (048) | 🟨 Partly ready | Partially implemented |
| 5.17 | Authentication information | Shared | Drafted: 023 | Partial | KPI-03 MFA 96% (Red) | 🟨 Partly ready | Partially implemented |
| 5.18 | Access rights | Northstar | Drafted: 023 | Partial | KPI-02 Red for a second period; CA-02 not yet effective | 🟨 Partly ready | Partially implemented |
| 5.19 | Information security in supplier relationships | Northstar | Drafted: 026, 055–057 | Unknown | No assessment records (058); Q2 KPI-14 not traceable | 🟧 Not ready | To be assessed |
| 5.20 | Addressing information security within supplier agreements | Northstar | Drafted: 026 §4 | Unknown | Contracts not reviewed | 🟧 Not ready | To be assessed |
| 5.21 | Managing information security in the ICT supply chain | Shared | Drafted: 029, 056 | Unknown | Dependency scanning untested; CI/CD provider unassessed | 🟧 Not ready | To be assessed |
| 5.22 | Monitoring, review and change management of supplier services | Northstar | Drafted: 059 | Unknown | No review evidenced | 🟧 Not ready | To be assessed |
| 5.23 | Information security for use of cloud services | Shared | Drafted: 026 §8 | Partial | KPI-06 cloud configuration 96% (Green); Microsoft assurance not mapped | 🟨 Partly ready | Partially implemented |
| 5.24 | Information security incident management planning and preparation | Northstar | Drafted: 027; EX-01 plan (053) | Unknown | T-18.1 exercise overdue (due 1 Mar 2027) | 🟧 Not ready | To be assessed |
| 5.25 | Assessment and decision on information security events | Northstar | Drafted: 027 §5, §8 | Partial | INC-2027-014 triaged and assessed (CA-03) | 🟨 Partly ready | To be assessed |
| 5.26 | Response to information security incidents | Northstar | Drafted: 027 | Partial | INC-2027-014 response recorded; no Severity 1 events (KPI-12) | 🟨 Partly ready | To be assessed |
| 5.27 | Learning from information security incidents | Northstar | Drafted: 027 §10; 046 | Partial | CA-03 root cause and ISMS changes from INC-2027-014 | 🟨 Partly ready | Not implemented |
| 5.29 | Information security during disruption | Shared | Drafted: 028, 050, 051 | None | No exercise or test | 🟧 Not ready | To be assessed |
| 5.30 | ICT readiness for business continuity | Shared | Drafted: 049–052, 054 | None | No failover test; T-14.3 report missing; KPI-09 Red | 🟧 Not ready | To be assessed |
| 5.31 | Legal, statutory, regulatory and contractual requirements | Northstar | None: legal register 005 not written | None | MRA-2027-02 proposed, not yet decided | 🟧 Not ready | Planned |
| 5.34 | Privacy and protection of PII | Shared | Drafted: 025; DPAs | Partial | Regions set at deployment; analytics copies not checked | 🟨 Partly ready | Partially implemented |
| 6.3 | Information security awareness, education and training | Northstar | Drafted: 022, 024 | Partial | KPI-10 91.8% (Amber); KPI-11 phishing reports 42% | 🟨 Partly ready | Partially implemented |
| 6.5 | Responsibilities after termination or change of employment | Northstar | Drafted: 023 §9 | Partial | KPI-01 90% (Amber); RCA-01 open | 🟨 Partly ready | Partially implemented |
| 6.8 | Information security event reporting | Northstar | Drafted: 027 §4 | Partial | Reporting channel in use (INC-2027-014) | 🟨 Partly ready | Partially implemented |
| 7.4 | Physical security monitoring | Northstar | Drafted: scope 004 §10 | Unknown | Head office only; not yet assessed on site | 🟧 Not ready | To be assessed |
| 8.1 | User endpoint devices | Northstar | Drafted: 024 | Partial | From SoA evidence (014); not re-tested since | 🟨 Partly ready | Partially implemented |
| 8.2 | Privileged access rights | Shared | Drafted: 023 | Partial | KPI-04 0 standing admin (Green); AUD03-F03 observation; break-glass tests not linked | 🟨 Partly ready | Partially implemented |
| 8.3 | Information access restriction | Northstar | Drafted: 023 | Partial | From SoA evidence (014) | 🟨 Partly ready | Partially implemented |
| 8.4 | Access to source code | Northstar | Drafted: 023, 029 | Partial | From SoA evidence (014) | 🟨 Partly ready | Partially implemented |
| 8.5 | Secure authentication | Shared | Drafted: 023 | Partial | KPI-03 96% (Red): 4 non-admin accounts without MFA | 🟨 Partly ready | Partially implemented |
| 8.8 | Management of technical vulnerabilities | Northstar | Drafted: 029 | Partial | KPI-05 90% (Amber) | 🟨 Partly ready | Partially implemented |
| 8.9 | Configuration management | Shared | Drafted: 029 | Partial | KPI-06 96% (Green) | 🟨 Partly ready | Partially implemented |
| 8.12 | Data leakage prevention | Shared | Drafted: 025; CA-03 | Partial | KPI-16 shows DLP blocking; SoA change waits for CA-03 verification | 🟨 Partly ready | Planned |
| 8.13 | Information backup | Shared | Drafted: 028, 052 | Partial | KPI-08 jobs 99.4% (Green), but KPI-09 restores Red; jobs do not prove recovery | 🟨 Partly ready | Partially implemented |
| 8.14 | Redundancy of information processing facilities | Shared | Drafted: 051 | None | Failover never tested | 🟧 Not ready | To be assessed |
| 8.15 | Logging | Shared | Drafted: 027 | Partial | From SoA evidence (014) | 🟨 Partly ready | Partially implemented |
| 8.16 | Monitoring activities | Shared | Drafted: 027 | Partial | From SoA evidence (014) | 🟨 Partly ready | Partially implemented |
| 8.20 | Networks security | Shared | Drafted: 029 | None | WAF not deployed (T-17.2) | 🟧 Not ready | Planned |
| 8.21 | Security of network services | Shared | Drafted: 029 | None | As 8.20 | 🟧 Not ready | Planned |
| 8.23 | Web filtering | Shared | Drafted: 024 | None | No web filtering policy | 🟧 Not ready | Planned |
| 8.24 | Use of cryptography | Shared | Drafted: 025 | Partial | Key Vault in use (014); key management not tested | 🟨 Partly ready | Partially implemented |
| 8.25 | Secure development life cycle | Northstar | Drafted: 029 | Unknown | Dependency scanning untested | 🟧 Not ready | To be assessed |
| 8.28 | Secure coding | Northstar | Drafted: 029 | Partial | From SoA evidence (014) | 🟨 Partly ready | Partially implemented |
| 8.32 | Change management | Northstar | Drafted: 029 §5 | Partial | KPI-07 100% approvals (Green); testing and emergency-change review not evidenced | 🟨 Partly ready | Partially implemented |
## 5. Differences from the SoA, for validation (NSD-ISMS-063)

| Control | SoA v1.0 says | Later evidence says | Question for 063 |
| --- | --- | --- | --- |
| 5.1 | Planned | KPI-20 reports 93% policy acknowledgement | Were policies approved and published outside the portfolio, or were drafts acknowledged? |
| 5.2 | Planned | Roles operated in AUD-03 | Partially implemented? |
| 5.3 | Planned | KPI-07: 100% second-person approval of deployments | Partially implemented for deployments; payments and backups still untested |
| 5.25, 5.26 | To be assessed | INC-2027-014 was triaged, assessed and handled (CA-03) | Partially implemented? |
| 5.27 | **Not implemented (escalated)** | CA-03 recorded root causes and ISMS changes from INC-2027-014 | Partially implemented? The escalation may be out of date |
| 8.12 | Planned | KPI-16 shows DLP blocking Restricted data | Status to change when CA-03 effectiveness is verified, as 034 states |
| 7.4 | To be assessed (head office only) | 7.4 can be mistaken for cloud provider assurance | Keep the SoA scope: Microsoft's facilities are covered by 5.23 and supplier assurance, not 7.4 |

Each difference is evidence pointing one way. The SoA changes only once 063 checks the evidence, and the control owner confirms.

## 6. Review rules

Eight rules apply.

1. Do not mark a control implemented merely because a policy mentions it.
2. Distinguish controls Northstar operates from controls provided by suppliers.
3. For cloud services, assess the shared-responsibility model and the evidence available from the provider.
4. A control may be excluded only with a defensible justification based on risk treatment and requirements.
5. A control not in Annex A may still be needed for an identified risk (for example, NSD-C-02, DORA contract terms).
6. The SoA must show Northstar's actual decisions and status, not a template.
7. **Evidence must be from the last 12 months,** the same window as the control credit rule (NSD-ISMS-012).
8. **"No events" is not evidence that a control works.** KPI-12 and KPI-13 (no Severity 1 incidents or breaches) show nothing about whether response would work; only an exercise does (EX-01).

## 7. Conclusion

29 of the 48 assessed controls are partly ready and 19 are not ready; with Wave 2, 64 of 93 are not ready. The fastest improvement would come from **approvals** (affecting every control) and **Wave 2** (45 controls). The controls most likely to produce major findings at Stage 2 are those with no evidence of operation where the risk is Very High: recovery (R-14) and leavers' access (R-12, where RCA-01 is still open).

## 8. Approval

| Role | Decision | Date |
| --- | --- | --- |
| Managing Director | Pending | |

---

*Portfolio disclaimer: Simulated readiness review. No real control evidence has been examined and no management approval is represented.*
