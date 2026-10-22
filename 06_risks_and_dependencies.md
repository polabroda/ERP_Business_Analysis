# 06 – Risk, Dependency and Decision Register

All items below are **illustrative potential risks**, not actual incidents. Likelihood and impact use a 1–3 qualitative scale (1 = low; 3 = high); score = L × I. Owners are **proposed roles**, not assigned people.

## Risk Register

| ID | Risk | L | I | Score | Proposed mitigation | Proposed owner | Status |
|---|---|---:|---:|---:|---|---|---|
| R-01 | Inconsistent customer/site identifiers | 3 | 3 | 9 | Define data owner, profiling and matching rules | Customer service + IT | OPEN |
| R-02 | Missing accounting export contract | 3 | 3 | 9 | Obtain file/API schema and run sample reconciliation | Finance + IT | BLOCKED |
| R-03 | Labor/material details incomplete at approval | 2 | 3 | 6 | Mandatory-field rules and exception policy | Operations | OPEN |
| R-04 | Over-scoping ERP to payroll/general ledger | 2 | 3 | 6 | Maintain MVP boundary and change control | Sponsor | OPEN |
| R-05 | Duplicate invoices on repeated export | 2 | 3 | 6 | Stable external reference and idempotency tests | Finance + IT | BLOCKED |
| R-06 | Field technicians resist increased data entry | 2 | 2 | 4 | Role-centered prototypes and usability tests | Operations | OPEN |
| R-07 | Unclear segregation of approval and billing roles | 2 | 3 | 6 | Access matrix and negative test cases | Security + Finance | OPEN |
| R-08 | Outage prevents urgent work from being registered | 2 | 2 | 4 | Controlled offline log and post-outage reconciliation | Operations + IT | OPEN |

## Dependencies

| Dependency | Upstream decision | Affected requirements | Impact if unresolved |
|---|---|---|---|
| D-01 | Customer/site master-data ownership | BR-001, FR-001 | Duplicates and poor traceability |
| D-02 | Accounting interface contract | FR-008, FR-009, NFR-004 | Billing handoff cannot be validated |
| D-03 | Role and authorization matrix | FR-002, FR-007, FR-011, NFR-001 | Workflow rules cannot be accepted |
| D-04 | Mandatory completion evidence by service type | FR-004–FR-007 | Premature or blocked acceptance |
| D-05 | Availability and recovery policy | BR-003, NFR-005 | Business continuity uncertain |

## Open Decisions (Decision Log)

| ID | Decision needed | Options to evaluate | Suggested decision owner | Status |
|---|---|---|---|---|
| DEC-01 | Authoritative customer/site source | Accounting / existing CRM / ERP master data | Sponsor + IT | OPEN |
| DEC-02 | Billing integration mode | Approved file exchange / API | Finance + IT | OPEN |
| DEC-03 | Reopen accepted job? | Prohibit / controlled reopen with audit | Operations + Finance | OPEN |
| DEC-04 | Multiple technicians per work order? | Single owner with contributors / multi-assignment | Operations | OPEN |
| DEC-05 | Historical data strategy | Clean migration / limited open-order migration / archive | IT + Operations | OPEN |
| DEC-06 | Retention and recovery targets | Determine by legal/security assessment | IT + Compliance | OPEN |

## Risk Evaluation Note

A score of 9 in this *illustrative* matrix signals a priority for discovery, not a quantified project risk. These registers must be confirmed with real stakeholders before use in procurement or delivery planning.
