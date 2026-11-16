# Northstar Digital Solutions Ltd — Backup and Recovery Test Report BRT-01

| Field | Value |
| --- | --- |
| Reference | NSD-ISMS-054 (test BRT-01) |
| Version | 0.2 — Report template with BRT-01 planned |
| Framework | ISO/IEC 27001:2022 incl. Amendment 1:2024: Annex A 8.13, 5.30, 8.31, 8.33 |
| Status | **Simulated. No test has been performed. Every result field is blank until a test produces evidence** |
| Requirement tested | [NSD-ISMS-028](../05-policies/28-backup-business-continuity-policy.md) §6.1: full restore of the production database into an isolated environment at least once a year, measured against the RTO and RPO · Treatment action T-14.3 (R-14) |
| Objectives | [NSD-ISMS-052](52-recovery-objectives-register.md) item 4: **RTO 4 hours, RPO 1 hour** |
| Owner | IT Manager (backup owner, AST-011) |
| Classification | Confidential |

---

## 1. Why this report exists

Two records are missing from the portfolio:

- **T-14.3,** the first full production restore, was due on 29 Jan 2027. No report of it exists.
- **KPI-09** for Q2 2027 counted one recovery test as a failure because it had **no record** (NSD-ISMS-044).

Whether those tests ran is not assumed either way. This template exists so that every test produces the same record. **A test without a completed report counts as a failure** (KPI-09).

**One test, one report.** Each report covers one system and one restore. A report covering a database, application data, configuration files and identity together cannot give a clear pass or fail for any of them.

| Draft scope item | Where it is tested |
| --- | --- |
| Customer database | **This report: BRT-01 (UK database). BRT-02 covers the EU database** |
| SaaS application data | Included in BRT-01: the application is tested against the restored database |
| Configuration files | Environment rebuild from code: the failover test (T-09.2, NSD-ISMS-051 §8) |
| Identity recovery | Not restorable by Northstar (Microsoft-held). Break-glass sign-in is tested quarterly (T-13.2) |
| Backup repository access and integrity | Included in BRT-01, sections 4 and 5 |

## 2. Test details

| Field | BRT-01 |
| --- | --- |
| System | Production customer database, **UK region** (AST-001) |
| Planned date | Tuesday 12 October 2027: the rescheduled test from the KPI-09 investigation (NSD-ISMS-044) |
| Test environment | Isolated Azure environment in a **UK** region: no network route to production; the same access controls as production |
| Authorised by | Head of Engineering (owner of AST-001), through a standard change record (NSD-ISMS-029 §5) |
| Data Protection lead | Informed in advance, because customer personal data is restored outside production |
| Restore performed by | IT Operations **deputy** (not the usual expert), following the runbook. This tests the runbook and BIA gap G4. The expert may observe; any help given is recorded |
| Backup used | From the **immutable** store (T-14.1), restored with the **separate backup role** (T-14.2), not a production administrator role |
| Business validation | Customer Support Manager: checks sample customer functions in the application |
| Evidence reviewed by | GRC Analyst, who does not take part in the restore |
| Sign-off | Head of Engineering (T-14.3 evidence requirement) |
| Report due | Within **5 working days** of the test |

## 3. How the times are measured

Without fixed start and stop points, a restore can be made to look faster than it was. The points are agreed before the test.

| Measure | Start | Stop |
| --- | --- | --- |
| **Achieved RTO** | The simulated disruption time **T0,** declared by the GRC Analyst. The clock includes finding the runbook, getting access and choosing the backup | The Customer Support Manager confirms the application works on the restored data. **Not** when the database restore job finishes |
| **Achieved RPO** | The time of the **last committed transaction** in the restored data | T0. Measured from the data itself, not from the backup job's timestamp |

## 4. Procedure

| Step | Action | Record |
| --- | --- | --- |
| 1 | Change approved; Data Protection lead informed; test environment confirmed isolated | Change reference; isolation check |
| 2 | GRC Analyst declares T0 | T0 timestamp |
| 3 | Operator signs in with the backup role, using MFA. The **production administrator role must not work** for this step | Sign-in log; result of the role check |
| 4 | Select the backup closest to T0; record its timestamp | Backup ID and timestamp |
| 5 | Confirm the backup is immutable: a deletion attempt with a test account is **refused** | Screenshot of the refusal |
| 6 | Restore into the isolated environment | Start and finish time of the restore job |
| 7 | Check integrity: table row counts and checksums against figures recorded from production at backup time; database consistency check | Comparison table |
| 8 | Connect a test instance of the application; run smoke tests | Test results |
| 9 | Customer Support Manager checks sample customer functions | Confirmation and time (stop of the RTO clock) |
| 10 | Find the last committed transaction (stop of the RPO measure) | Query output |
| 11 | **Destroy the restored copy;** confirm deletion | Deletion evidence (A 8.33) |
| 12 | Complete this report within 5 working days | — |

## 5. Results

| Item | Pass criterion | Result | Evidence |
| --- | --- | --- | --- |
| Separate backup role | Restore possible with the backup role; **not** possible with a production administrator role | To be recorded | |
| Immutability | Deletion attempt refused | To be recorded | |
| Backup available | A backup exists within 1 hour before T0 | To be recorded | |
| Integrity | Row counts and checksums match; consistency check clean | To be recorded | |
| Application | All smoke tests and sample customer functions pass | To be recorded | |
| **Achieved RTO** | **4 hours or less** | To be recorded | |
| **Achieved RPO** | **1 hour or less** | To be recorded | |
| Runbook | Restore completed by the deputy without unrecorded help | To be recorded | |
| Test data destroyed | Deletion confirmed | To be recorded | |

**Result values:** Pass, Fail, or Not tested (with the reason). Nothing else is used.

**Overall result:** **Pass only if every item passes.** A database that restores correctly in 6 hours has **failed** the test. "Restored successfully" is a description, not a result.

**What this test cannot show:** that a backup is available when the UK region itself is down. Backups are held in the same region as the source (BIA gap G2). That scenario is recorded as **Not tested,** not as a pass.

## 6. Findings

Each failed or untested item is recorded with the evidence and triaged under NSD-ISMS-045 §2:

- An RTO or RPO not met, or a backup control (T-14.1, T-14.2) not working: a requirement of NSD-ISMS-028 is not met, so it goes to **NSD-ISMS-034.**
- The runbook unclear, or help needed: an improvement for **NSD-ISMS-047,** unless it caused a failure.
- Results that change a risk (R-14, R-09): updated in **NSD-ISMS-014.**

| Finding | Item | Evidence | Triage | Reference |
| --- | --- | --- | --- | --- |
| To be recorded | | | | |

Corrective actions are tracked in the register the finding is triaged to, not in this report.

## 7. What the result updates

| Record | Pass | Fail |
| --- | --- | --- |
| NSD-ISMS-052 item 4 | Status becomes **Demonstrated** (valid for 12 months) | Stays Proposed or Approved; finding raised |
| KPI-09 | Counted as met | Counted as failed |
| R-14 control credit, "restore testing" | **Effective,** tested in the last 12 months | Partial or Untested, so no full credit |
| T-14.3 | Evidence for closure, verified by the GRC Analyst | Stays open |

## 8. Sign-off

| Role | Name | Decision | Date |
| --- | --- | --- | --- |
| Restore operator (IT Operations deputy) | | | |
| Business validation (Customer Support Manager) | | | |
| Evidence review (GRC Analyst) | | | |
| Sign-off (Head of Engineering) | | | |

## 9. Change log

| Version | Change |
| --- | --- |
| 0.1 (portfolio draft, as NSD-ISMS-050) | Template BRT-001, all results pending |
| 0.2 | Numbered NSD-ISMS-054 (BRT-01). The draft's honest "pending" approach is kept: no results are claimed. Linked to the 028 §6 requirement, T-14.3 and KPI-09, and records that the T-14.3 report and one Q2 test record are missing. **One system per report;** the other draft scope items are placed with their own tests. Details filled in where the portfolio sets them: system, objectives, isolated UK environment, authorisation, deputy operator, immutable backup and separate backup role. Exact start and stop points for the achieved RTO and RPO. Pass criteria for every item; "pass only if every item passes"; result values limited to Pass, Fail and Not tested. Added protection of restored personal data and its destruction afterwards. Findings triaged into the existing registers rather than tracked in the report. Effects on NSD-ISMS-052, KPI-09, R-14 control credit and T-14.3 set out. |

---

*Portfolio disclaimer: Simulated test report template. No backup or restoration test has been performed.*
