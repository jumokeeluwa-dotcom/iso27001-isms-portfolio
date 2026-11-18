# Northstar Digital Solutions Ltd — Risk and Control Mapping Register

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-020 |
| Version | 1.0 — Draft for review |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024 (clause 6.1.3(b)–(d)) |
| Related documents | [NSD-ISMS-014 Risk Register](../03-risk-management/14-risk-register.md) · [NSD-ISMS-015 Treatment Plan](../03-risk-management/15-risk-treatment-plan.md) · [NSD-ISMS-017 Risk Ownership](../03-risk-management/17-risk-ownership-register.md) · [NSD-ISMS-018 SoA Methodology](18-soa-methodology.md) · [NSD-ISMS-019 SoA](19-statement-of-applicability.md) |
| Owner | Information Security / GRC Analyst |
| Approver | Managing Director |
| Review frequency | Whenever NSD-ISMS-014, 015 or 019 changes |
| Classification | Confidential |

---

## 1. Purpose

This register shows that the Statement of Applicability is connected to the risk register and the treatment plan. A control must not appear in the SoA just because it sounds useful: its presence must trace to a risk, a requirement or a business need.

The mapping works in **both directions**:

- **Risk → control** (section 3): which controls treat each risk, and how far they are implemented.
- **Control → risk** (section 4): why each applicable SoA control exists.

## 2. Results

| Check | Result |
| --- | --- |
| Risks in NSD-ISMS-014 with at least one mapped control | **20 of 20** |
| Treatment actions in NSD-ISMS-015 whose Annex A controls appear in the SoA | **36 of 36**: no missing controls |
| Applicable SoA controls linked to at least one risk | **42 of 47** |
| Applicable SoA controls with no risk link | **5**: all justified by requirement reason codes (section 4.1) |
| Risk-to-control links | 79 |
| Controls the risk analysis shows are needed but are still in SoA Wave 2 | **11** (section 5) |

**Most-relied-on controls.** If one of these fails, several risks rise at once, so their evidence is tested first:

| Control | Risks it treats |
| --- | --- |
| 8.5 Secure authentication | 6 |
| 8.2 Privileged access rights | 4 |
| 8.15 Logging | 4 |
| 8.16 Monitoring activities | 4 |
| 5.3 Segregation of duties | 4 |

## 3. Risk → control mapping

**How to read this table**

- **Controls:** a control marked † treats the risk through an existing control or the risk analysis. Unmarked controls come from a treatment action.
- **Weakest SoA status:** the lowest implementation status among the risk's controls (NSD-ISMS-019). A risk cannot reach its target while any of its controls is Planned or Not implemented.
- **Wave 2 controls:** further controls the scenario needs, which are still awaiting SoA assessment.

| Risk | Scenario | Risk owner | Current → target | Controls | Treatment actions | Weakest SoA status | Wave 2 controls |
| --- | --- | --- | --- | --- | --- | --- | --- |
| R-01 | Customer data exfiltration | Head of Engineering | 🟧 15 High → 8 Medium | 5.15, 5.34†, 8.2, 8.3, 8.5†, 8.15, 8.16 | T-01.1, T-01.2 | Partially implemented | — |
| R-02 | EU data outside the EU region | Data Protection lead | 🟧 12 High → 4 Low | 5.23, 5.31, 5.34, 8.9 | T-02.1, T-08.1 | Planned | 5.14 |
| R-03 | HR records exposure | HR Manager | 🟧 12 High → 8 Medium | 5.13, 5.15, 5.18, 5.34† | T-03.1, T-03.2 | Planned | — |
| R-04 | Payment fraud (business email compromise) | Finance Manager | 🟧 12 High → 6 Medium | 5.3, 6.3† | T-04.1 | Planned | — |
| R-05 | Malicious code change | Head of Engineering | 🟧 12 High → 8 Medium | 8.4, 8.5†, 8.28†, 8.32 | T-05.1 | Partially implemented | 8.29 |
| R-06 | Secrets in code or pipelines | Head of Engineering | 🟥 20 Very High → 8 Medium | 5.17, 8.2, 8.4, 8.15, 8.24, 8.28 | T-06.1, T-06.2, T-06.3 | Partially implemented | — |
| R-07 | CI/CD supply-chain compromise | Head of Engineering | 🟧 15 High → 10 High | 5.3, 8.25, 8.28, 8.32 | T-07.1, T-07.2 | Planned | 5.21, 8.29, NSD-C-01 |
| R-08 | Azure misconfiguration | Head of Engineering | 🟧 15 High → 8 Medium | 5.23, 8.9, 8.16 | T-08.1, T-08.2 | Partially implemented | 8.22 |
| R-09 | Azure regional outage | Head of Engineering | 🟧 10 High → 6 Medium | 5.23†, 5.29, 5.30, 8.14 | T-09.1, T-09.2 | To be assessed | — |
| R-10 | Phishing compromises Microsoft 365 | IT Manager | 🟧 12 High → 8 Medium | 6.3, 6.8†, 8.5 | T-10.1, T-10.2 | Partially implemented | 8.7 |
| R-11 | Password spraying / service accounts | IT Manager | 🟧 12 High → 8 Medium | 5.17, 8.5, 8.16† | T-11.1 | Partially implemented | — |
| R-12 | Leavers keep access | HR Manager | 🟥 16 Very High → 8 Medium | 5.16, 5.18, 6.5 | T-12.1, T-12.2, T-12.3 | Partially implemented | 5.11 |
| R-13 | Privileged credential misuse | IT Manager | 🟧 15 High → 10 High | 5.17, 8.2, 8.5†, 8.15 | T-13.1, T-13.2 | Partially implemented | 8.18 |
| R-14 | Ransomware destroys backups | IT Manager | 🟥 20 Very High → 6 Medium | 5.3, 5.30, 8.2, 8.13 | T-14.1, T-14.2, T-14.3 | Planned | 8.7 |
| R-15 | Log tampering or loss | GRC Analyst | 🟧 12 High → 4 Low | 5.3†, 8.15, 8.16† | T-15.1 | Planned | 5.28, 8.17 |
| R-16 | Supplier account compromise | Finance Manager | 🟧 15 High → 8 Medium | 5.18, 5.19, 5.20†, 5.22, 8.5† | T-16.1, T-16.2 | To be assessed | 5.21 |
| R-17 | Unpatched critical vulnerability | Head of Engineering | 🟧 15 High → 8 Medium | 5.7†, 8.8, 8.20, 8.21 | T-17.1, T-17.2 | Planned | — |
| R-18 | Late breach notification | Data Protection lead | 🟧 12 High → 4 Low | 5.24, 5.25, 5.26, 5.27†, 6.8 | T-18.1 | Not implemented | 5.5, 5.28 |
| R-19 | Restricted data in AI tools | Managing Director | 🟥 16 Very High → 8 Medium | 5.10, 5.13†, 6.3†, 8.12, 8.23 | T-19.1, T-19.2 | Planned | 5.14 |
| R-20 | Lost or stolen laptop | IT Manager | 🟨 8 Medium → 4 Low | 8.1, 8.24† | T-20.1 | Partially implemented | 5.11, 7.9 |

## 4. Control → risk mapping

Every applicable control in NSD-ISMS-019, with the risks it treats.

| Control | Title | Risks | Linked risks | SoA reason codes | SoA status |
| --- | --- | --- | --- | --- | --- |
| 5.1 | Policies for information security | 0 | — | BR, IP | Planned |
| 5.2 | Information security roles and responsibilities | 0 | — | BR | Planned |
| 5.3 | Segregation of duties | 4 | R-04, R-07, R-14, R-15 | RT | Planned |
| 5.7 | Threat intelligence | 1 | R-17 | BR, IP | To be assessed |
| 5.9 | Inventory of information and other associated assets | 0 | — | BR, RT | Partially implemented |
| 5.10 | Acceptable use of information and other associated assets | 1 | R-19 | RT | Planned |
| 5.12 | Classification of information | 0 | — | BR, LR | Planned |
| 5.13 | Labelling of information | 2 | R-03, R-19 | RT | Planned |
| 5.15 | Access control | 2 | R-01, R-03 | RT, LR | Partially implemented |
| 5.16 | Identity management | 1 | R-12 | RT | Partially implemented |
| 5.17 | Authentication information | 3 | R-06, R-11, R-13 | RT | Partially implemented |
| 5.18 | Access rights | 3 | R-03, R-12, R-16 | RT | Partially implemented |
| 5.19 | Information security in supplier relationships | 1 | R-16 | RT, CO | To be assessed |
| 5.20 | Addressing information security within supplier agreements | 1 | R-16 | CO, LR | To be assessed |
| 5.22 | Monitoring, review and change management of supplier services | 1 | R-16 | RT | To be assessed |
| 5.23 | Information security for use of cloud services | 3 | R-02, R-08, R-09 | RT, BR | Partially implemented |
| 5.24 | Information security incident management planning and preparation | 1 | R-18 | RT, LR | To be assessed |
| 5.25 | Assessment and decision on information security events | 1 | R-18 | RT, LR | To be assessed |
| 5.26 | Response to information security incidents | 1 | R-18 | RT | To be assessed |
| 5.27 | Learning from information security incidents | 1 | R-18 | BR (clause 10) | Not implemented |
| 5.29 | Information security during disruption | 1 | R-09 | RT | To be assessed |
| 5.30 | ICT readiness for business continuity | 2 | R-09, R-14 | RT, CO | To be assessed |
| 5.31 | Legal, statutory, regulatory and contractual requirements | 1 | R-02 | LR, CO | Planned |
| 5.34 | Privacy and protection of PII | 3 | R-01, R-02, R-03 | LR | Partially implemented |
| 6.3 | Information security awareness, education and training | 3 | R-04, R-10, R-19 | RT, BR | Partially implemented |
| 6.5 | Responsibilities after termination or change of employment | 1 | R-12 | RT | Partially implemented |
| 6.8 | Information security event reporting | 2 | R-10, R-18 | RT, LR | Partially implemented |
| 7.4 | Physical security monitoring | 0 | — | BR | To be assessed |
| 8.1 | User endpoint devices | 1 | R-20 | RT | Partially implemented |
| 8.2 | Privileged access rights | 4 | R-01, R-06, R-13, R-14 | RT | Partially implemented |
| 8.3 | Information access restriction | 1 | R-01 | RT | Partially implemented |
| 8.4 | Access to source code | 2 | R-05, R-06 | RT | Partially implemented |
| 8.5 | Secure authentication | 6 | R-01, R-05, R-10, R-11, R-13, R-16 | RT, CO | Partially implemented |
| 8.8 | Management of technical vulnerabilities | 1 | R-17 | RT, BR | Partially implemented |
| 8.9 | Configuration management | 2 | R-02, R-08 | RT | Partially implemented |
| 8.12 | Data leakage prevention | 1 | R-19 | RT | Planned |
| 8.13 | Information backup | 1 | R-14 | RT, CO | Partially implemented |
| 8.14 | Redundancy of information processing facilities | 1 | R-09 | RT, CO | To be assessed |
| 8.15 | Logging | 4 | R-01, R-06, R-13, R-15 | RT, LR | Partially implemented |
| 8.16 | Monitoring activities | 4 | R-01, R-08, R-11, R-15 | RT | Partially implemented |
| 8.20 | Networks security | 1 | R-17 | RT | Planned |
| 8.21 | Security of network services | 1 | R-17 | RT | Planned |
| 8.23 | Web filtering | 1 | R-19 | RT | Planned |
| 8.24 | Use of cryptography | 2 | R-06, R-20 | RT, LR | Partially implemented |
| 8.25 | Secure development life cycle | 1 | R-07 | RT, BR | To be assessed |
| 8.28 | Secure coding | 3 | R-05, R-06, R-07 | RT | Partially implemented |
| 8.32 | Change management | 2 | R-05, R-07 | RT | Partially implemented |

### 4.1 Controls with no risk link

Five applicable controls treat no specific risk. Each is justified by a requirement, as NSD-ISMS-018 §3 allows:

| Control | Why it is still applicable |
| --- | --- |
| 5.1 Policies for information security | Required for the ISMS; charter Obj 1 (BR, IP) |
| 5.2 Information security roles and responsibilities | Required for the ISMS; clause 5.3 (BR) |
| 5.9 Inventory of information and other associated assets | Foundation of the asset documents NSD-ISMS-006 to 011; Obj 2 (BR) |
| 5.12 Classification of information | Underpins handling for all data; NSD-ISMS-008 (BR, LR) |
| 7.4 Physical security monitoring | Head office only. **No risk yet**: a physical-security scenario is to be raised (NSD-ISMS-019 §6, finding 3) |

These are acceptable because each has a documented reason. A control with neither a risk link nor a reason code would be removed or given a reason.

## 5. Controls confirmed for SoA Wave 2

The mapping shows that these 11 controls, still awaiting assessment in NSD-ISMS-019 §5, are needed to treat specific risks. Wave 2 should confirm them as **applicable** with reason code **RT**, rather than "likely applicable".

| Control | Title | Needed by |
| --- | --- | --- |
| 5.5 | Contact with authorities | R-18 |
| 5.11 | Return of assets | R-12, R-20 |
| 5.14 | Information transfer | R-02, R-19 |
| 5.21 | Managing information security in the ICT supply chain | R-07, R-16 |
| 5.28 | Collection of evidence | R-15, R-18 |
| 7.9 | Security of assets off-premises | R-20 |
| 8.7 | Protection against malware | R-10, R-14 |
| 8.17 | Clock synchronization | R-15 |
| 8.18 | Use of privileged utility programs | R-13 |
| 8.22 | Segregation of networks | R-08 |
| 8.29 | Security testing in development and acceptance | R-05, R-07 |

R-07 also needs the additional control **NSD-C-01** (SBOM verification), already listed in NSD-ISMS-019 §4.

## 6. What the mapping shows

1. **The SoA and treatment plan are consistent.** Every Annex A control named in the 36 treatment actions is in the SoA.
2. **Implementation lags the targets.** Nine risks have at least one Planned or Not implemented control. Their target scores in NSD-ISMS-015 cannot be reached until those controls are in place.
3. **R-18 depends on a control with no plan.** 5.27 (learning from incidents) is Not implemented. The proposed action T-18.2 (NSD-ISMS-019 finding 2) must be added to the treatment plan before R-18 can reach its target.
4. **Authentication is a single point of reliance.** 8.5 treats 6 risks. Its partial status (legacy authentication allowed, service accounts excluded) holds back R-01, R-05, R-10, R-11, R-13 and R-16 together, which is why T-10.1 and T-11.1 matter more than their P3 priority suggests.
5. **Wave 2 is now partly decided.** 11 of the 46 remaining controls are confirmed as needed by specific risks.

## 7. Mapping rules

1. Candidate controls are not automatically necessary. A control is selected only through a treatment decision or a requirement (NSD-ISMS-018 §3).
2. One control can treat several risks, and one risk can need several controls.
3. Controls are written using ISO/IEC 27001:2022 Annex A numbers and titles. For example, 8.3 is Information access restriction, 8.5 is Secure authentication, and 8.14 is Redundancy of information processing facilities.
4. When a risk, treatment action or SoA entry changes, this register is regenerated from those documents, not edited by hand.
5. Every applicable control must appear in section 4, with either a risk link or a reason code.

## 8. Approval

| Role | Responsibility | Decision | Date |
| --- | --- | --- | --- |
| Managing Director | Approves the mapping as evidence of clause 6.1.3(b)–(c) | Pending | |
| Risk owners | Confirm the controls for their risks | Pending | |
| Information Security / GRC Analyst | Prepared the register | Prepared | |

---

*Portfolio note: Mappings and statuses are simulated for a fictional organisation.*
