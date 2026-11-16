# Northstar Digital Solutions Ltd — Audit Checklist: AUD-03 Identity and Access Management

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-032 |
| Audit reference | AUD-03 (NSD-ISMS-030 §5) |
| Audit plan | [NSD-ISMS-031](31-audit-plan-aud03-iam.md): tests IAM-01 to IAM-15 |
| Version | 0.2 — Ready for use |
| Lead auditor | External auditor (independence confirmed in section 2) |
| Fieldwork | 15–16 June 2027 · Period tested: 1 February to 31 May 2027 |
| Classification | Confidential once completed: it holds audit evidence |

---

## 1. How to use this checklist

- Each row is one audit question. It is tied to a test in the audit plan (NSD-ISMS-031 §6) and to a requirement the auditee can be held to.
- Record the result, a working paper reference and, where raised, a finding reference against every row. **Every row ends with a result.** "Not tested" at the close of fieldwork must be explained in the report.
- Working papers are numbered **WP-AUD03-nn** and stored in the Confidential audit folder (NSD-ISMS-030 §12).
- **A blank or missing record may indicate an evidence gap.** Investigate it before concluding that a control is not operating: ask for the record, check other sources, and interview the person responsible.

## 2. Before fieldwork

| Check | Done | Notes |
| --- | --- | --- |
| Auditor has signed the independence confirmation (no role in designing or operating IAM) | ☐ | |
| Audit plan issued to auditees by 1 June 2027 | ☐ | |
| Evidence requested in NSD-ISMS-031 §7 received by 8 June 2027 | ☐ | List anything missing |
| Read-only access to Entra ID and Azure confirmed | ☐ | |
| Change record approved for the legacy sign-in test (C-14) | ☐ | Change ref: |
| Previous findings in this area reviewed | ☐ | None (first cycle) |

## 3. Population register

Populations are drawn from **systems of record**. Extraction is observed by the auditor, or the system timestamp is kept. Record each population before sampling.

| Population | Source system | Count | Extracted by and date | Observed by auditor? | WP ref |
| --- | --- | --- | --- | --- | --- |
| Leavers in the period | HR system | | | ☐ | |
| Joiners in the period | HR system | | | ☐ | |
| Movers in the period | HR system | | | ☐ | |
| Enabled user accounts | Entra ID | | | ☐ | |
| Service accounts | Entra ID and inventory | | | ☐ | |
| Access grants to Restricted assets | Access request log | | | ☐ | |
| Privileged role assignments | Entra ID PIM | | | ☐ | |
| Privileged role activations | PIM audit log | | | ☐ | |
| Database role assignments and just-in-time requests | Azure | | | ☐ | |
| Guest accounts | Entra ID | | | ☐ | |
| Access-related exceptions | Exceptions log | | | ☐ | |

**Sample selection.** Populations under 25 are tested in full. Larger populations are sampled to 25 using random selection, and the method is recorded. **A population of zero is itself a result.** Record it: for example, "no movers in the period" makes C-05 Not applicable, with the evidence.

## 4. Checklist

### A. Governance

| No. | Audit question | Criterion | Evidence and test | Pass criterion | Result | WP / finding |
| --- | --- | --- | --- | --- | --- | --- |
| C-01 | Is the Access Control and Identity Management Policy approved, current and acknowledged? | 023; clause 7.5; A 5.15 | Approved policy with version history; acknowledgement report (IAM-15) | Approved by the MD; within its review date; acknowledged by 95% or more | Not tested | |
| C-02 | Are the policy's access measures reported to management? | 023 §12; clause 9.1 | Steering Group minutes and packs for the period | Measures reported at every meeting in the period | Not tested | |

### B. Identity lifecycle

| No. | Audit question | Criterion | Evidence and test | Pass criterion | Result | WP / finding |
| --- | --- | --- | --- | --- | --- | --- |
| C-03 | Is every identity unique, with no unapproved shared accounts? | 023 §4.1–4.2; A 5.16 | All enabled accounts: look for generic or shared accounts; check the exceptions log for any approved | No shared account without an approved exception | Not tested | |
| C-04 | Is joiner access approved before provisioning, and not active before the start date? | 023 §5, §9; A 5.16, 5.18 | All joiners from HR (IAM-03): request, approval, provisioner, dates | 100% approved first; provisioner is not the requester; none active early | Not tested | |
| C-05 | Is a mover's old access removed within 5 working days? | 023 §9; A 5.18 | All movers from HR (IAM-04): access before and after the move | 100% removed within 5 working days | Not tested | |
| C-06 | Are leavers' accounts disabled by the end of their last working day? | 023 §9; A 6.5 | All leavers **from HR** (IAM-01): HR last day compared with the Entra ID disable time | 100% disabled by the end of the last working day | Not tested | |
| C-07 | Are a leaver's sessions, tokens, keys, database users and guest accounts revoked, and devices returned? | 023 §9; A 6.5, 5.18 | Same leavers: session revocation record, database users, repository tokens, guest accounts, device return record | No remaining access for any leaver; all devices returned | Not tested | |
| C-08 | Does every enabled account belong to a current person or an owned service account? | 023 §4; A 5.16 | All enabled accounts matched back to HR and the service account inventory (IAM-02, the reverse test) | Zero orphaned accounts | Not tested | |
| C-09 | Does every service account have an owner, a purpose and protection? | 023 §4.3, §6.1; A 5.17, 8.5 | All service accounts (IAM-08) | 100% owned and documented; managed identity or Conditional Access restriction | Not tested | |

### C. Access approval and least privilege

| No. | Audit question | Criterion | Evidence and test | Pass criterion | Result | WP / finding |
| --- | --- | --- | --- | --- | --- | --- |
| C-10 | Is access to Restricted assets approved by the asset owner or deputy, and provisioned by someone other than the requester? | 023 §5; NSD-ISMS-007; A 5.18 | 25 grants from the request log (IAM-05); confirm approvers with a sample of asset owners | 100% approved by the owner or deputy named in NSD-ISMS-007; provisioner is not the requester | Not tested | |
| C-11 | Is engineers' access to production customer data just in time, approved and time-limited? | 023 §7.4; A 8.3; T-01.1 | Database role assignments; 25 just-in-time requests, or all if fewer (IAM-11) | No standing read access; 100% of requests approved and expired | Not tested | |
| C-12 | Are access reviews completed on schedule, with removals done? | 023 §8; A 5.18 | Quarterly reviews of Restricted assets and privileged roles in the period (IAM-06); trace removals to the system | Reviews completed on time; removals done within 5 working days | Not tested | |

### D. Authentication

| No. | Audit question | Criterion | Evidence and test | Pass criterion | Result | WP / finding |
| --- | --- | --- | --- | --- | --- | --- |
| C-13 | Is MFA (or a managed identity) in place for every account? | 023 §6.1; A 8.5 | MFA registration report; Conditional Access export (IAM-07) | 100% coverage, including service accounts | Not tested | |
| C-14 | Is legacy authentication blocked? | 023 §6.3; A 8.5 | 30 days of sign-in logs, plus **re-performance**: a legacy sign-in attempt with an authorised test account | Zero legacy sign-ins; the test attempt is blocked | Not tested | |
| C-15 | Do administrators use phishing-resistant MFA? | 023 §6.2; A 8.5 | Authentication method report for all admin accounts | 100% of admin accounts | Not tested | |

### E. Privileged access

| No. | Audit question | Criterion | Evidence and test | Pass criterion | Result | WP / finding |
| --- | --- | --- | --- | --- | --- | --- |
| C-16 | Are privileged roles held only just in time, through separate admin accounts? | 023 §7.1–7.3; A 8.2 | All privileged role assignments (IAM-09) | No standing Global Administrators apart from 2 break-glass accounts; admin accounts separate from everyday accounts | Not tested | |
| C-17 | Is every privileged role activation approved, justified and time-limited? | 023 §7.2; A 8.2 | 25 activations from the PIM audit log (IAM-09) | 100% approved, justified and expired on time | Not tested | |
| C-18 | Are break-glass accounts vaulted, alerted, tested and used only with MD approval? | 023 §7.3; A 5.17, 8.2 | Vault record; alert rule; quarterly test records; any use in the period (IAM-10) | Alert active; tested each quarter; every use MD-approved and reviewed | Not tested | |
| C-19 | Is privileged activity logged, and protected from deletion by administrators? | 023 §7.5; A 8.2 | Sample of privileged actions traced to the logs; role check for log deletion rights. **Limited check:** the full logging control (8.15) is audited in AUD-04 | Sampled actions are logged; no administrator can delete logs | Not tested | |

### F. Third-party access

| No. | Audit question | Criterion | Evidence and test | Pass criterion | Result | WP / finding |
| --- | --- | --- | --- | --- | --- | --- |
| C-20 | Does every guest or supplier account have a sponsor, MFA and expiry within 90 days, and is it removed at contract end? | 023 §10; A 5.18; T-16.1 | All guest accounts (IAM-12), compared with contract end dates from the supplier register | 100% compliant; no account left after its contract ended | Not tested | |

### G. Exceptions, incidents and treatment

| No. | Audit question | Criterion | Evidence and test | Pass criterion | Result | WP / finding |
| --- | --- | --- | --- | --- | --- | --- |
| C-21 | Are access exceptions approved by the right authority, time-limited and backed by compensating controls? | NSD-ISMS-008 §8; A 5.15 | All access entries in the exceptions log (IAM-13) | MD approval for Restricted or privileged access; 12 months or less; compensating controls in place | Not tested | |
| C-22 | Were access-related incidents in the period recorded, investigated and closed? | NSD-ISMS-027; A 5.24–5.26 | Incident log, filtered for access incidents. **Cross-check only:** the incident process itself is audited in AUD-07 | Each incident recorded, assessed and closed, with lessons learned where Severity 1 or 2 | Not tested | |
| C-23 | Does the closure evidence for access treatment actions match what the systems show today? | Clause 8.3; NSD-ISMS-015 | T-01.1, T-10.1, T-11.1, T-12.1–12.3, T-13.1, T-13.2, T-16.1: compare filed evidence with current configuration (IAM-14) | Filed evidence matches the live configuration | Not tested | |
| C-24 | Are the SoA statuses for the access controls supported by the results of this audit? | Clause 6.1.3(d); NSD-ISMS-019 | Compare the statuses of 5.15–5.18, 6.5, 8.2, 8.3 and 8.5 with the results above | No status claims more than the evidence supports | Not tested | |

## 5. Results

| Result | Meaning |
| --- | --- |
| **Conforming** | Evidence supports that the requirement is met |
| **Nonconformity: Major** | The requirement is not met at all, or there is a systemic failure (NSD-ISMS-030 §8) |
| **Nonconformity: Minor** | A single or isolated lapse against the requirement |
| **Observation** | Worth management attention, but not established as a nonconformity |
| **Opportunity for improvement** | A suggested enhancement |
| **Not applicable** | Population is zero, or the area is out of scope. The evidence for this is recorded |
| **Not tested** | No conclusion reached. The reason is stated in the report |

## 6. Auditor notes (one per row)

For every row, record:

- the evidence reference (WP-AUD03-nn) and the date it was reviewed;
- the population source and count, and whether the auditor observed the extraction;
- the sample selected, and how it was chosen;
- the interviewee or evidence provider;
- the test performed, including any re-performance;
- the result and the facts supporting it: numbers tested, numbers failing, which items;
- the finding reference, if one is raised (AUD03-Fnn).

## 7. Example entry (illustrative only)

This example shows how to complete a row. It is **not** an audit result.

| Field | Entry |
| --- | --- |
| Row | C-06: leavers disabled by the end of their last working day |
| Population | HR system leaver report for 1 February to 31 May 2027: **7 leavers.** Extracted by the HR Manager on 15 June 2027, observed by the auditor (WP-AUD03-03) |
| Sample | All 7 (population under 25) |
| Test | For each leaver, compared the HR last working day with the Entra ID "account disabled" audit event |
| Facts | 6 of 7 were disabled on their last working day. 1 contractor was disabled **2 working days late.** HR entered the leaving date late, so the automated workflow (T-12.3) started late |
| Investigation before concluding | Asked HR and IT for any manual disablement record: none. Checked sign-in logs for the 2 days: **no sign-ins** |
| Result | **Nonconformity: Minor.** 023 §9 and A 6.5 were not met for 1 of 7 leavers. An isolated lapse, with no evidence of access being used |
| Finding | AUD03-F01. Root cause for the owner to confirm: the automation depends on HR entering the leaving date on time |
| Follow-on | R-12's control credit stays Partial (NSD-ISMS-014). SoA status for 6.5 stays Partially implemented |

## 8. Sign-off

| Role | Name | Date |
| --- | --- | --- |
| Lead auditor: checklist completed | | |
| Process owner (IT Manager): results discussed at the closing meeting | | |

## 9. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-028 / AUD-005) | 15 questions with evidence and results |
| 0.2 | Numbered NSD-ISMS-032, with audit reference AUD-03 to match the programme. Each question tied to a plan test (IAM-01 to IAM-15) and a policy clause. Vague questions made testable: "MFA where required" became 100% of accounts; "disabled promptly" became the end of the last working day; "reviewed periodically" became quarterly. Added questions on joiners, movers, orphan accounts, service accounts, production data access, break-glass accounts, legacy sign-in re-performance, treatment evidence and SoA accuracy. Draft questions 8 and 14 (logging) and 15 (incidents) kept as limited cross-checks, because the full controls are audited in AUD-04 and AUD-07. Added pre-fieldwork checks, a population register, the Major/Minor grade, "Not applicable" with evidence, working paper references and an illustrative example entry. The draft's results scale, notes fields and investigate-first principle are kept. |

---

*Portfolio note: Simulated checklist for a fictional organisation. No audit has been performed.*
