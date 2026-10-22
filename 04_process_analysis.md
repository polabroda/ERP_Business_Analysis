# 04 – Business Process Analysis (AS-IS / TO-BE)

## Process Under Review

**Service request → execution → internal acceptance → invoice-ready handoff**.

Visual versions: [AS-IS diagram](diagrams/process_as_is.md) · [TO-BE diagram](diagrams/process_to_be.md).

## AS-IS (illustrative)

1. A customer emails a request; customer service copies details into a spreadsheet.
2. A dispatcher assigns a technician by phone/email.
3. The technician fills in paper or spreadsheet notes after the visit.
4. Warehouse materials and labor records are reconciled manually.
5. The operations manager checks the job via messages.
6. Finance receives an email with billing details and re-enters the data.

### Assumed Pain Points

| Issue | Consequence | Related objective |
|---|---|---|
| Different order references in each team | Manual reconciliation and disputes | OBJ-01 |
| Unstructured completion evidence | Extra follow-up before billing | OBJ-02, OBJ-03 |
| Spreadsheet-based status changes | Limited status visibility | OBJ-04 |
| Email-only approvals | Unclear responsibility / audit | OBJ-03 |

These are **hypothetical process weaknesses**, not observed defects at a real organization.

## TO-BE (proposed)

1. Authorized staff register the request with a customer and site; a unique work-order ID is assigned (`FR-001`, `BR-001`).
2. Operations review and approve work for dispatch (`FR-002`).
3. Dispatch assigns the work and target date (`FR-003`).
4. Technician records labor, material consumption and evidence (`FR-004`–`FR-006`).
5. An operations manager reviews completeness and accepts the work (`FR-007`, `BR-002`).
6. Finance releases invoice-ready data and reconciles the export (`FR-008`, `FR-009`, `NFR-004`).
7. Search, audit trail and access rules apply across the lifecycle (`FR-010`, `FR-012`, `NFR-001`, `NFR-002`).

## Proposed Status Model

`Draft → Approved → Scheduled → In Progress → Work Done → Accepted → Ready for Billing → Billed`

Alternative path: `Draft / Approved / Scheduled / In Progress / Work Done → Cancelled`, subject to authorization and mandatory reason. An order marked `Work Done` may return to `In Progress` when corrections are necessary. **Reopening after acceptance is an OPEN business decision** and is excluded from the proposed standard flow until agreed.

| Transition | Proposed actor | Mandatory check |
|---|---|---|
| Draft → Approved | Operations manager | Customer/site and service scope complete |
| Approved → Scheduled | Dispatcher | Technician and date assigned |
| Scheduled → In Progress | Assigned technician | Work actually started |
| In Progress → Work Done | Assigned technician | Service notes supplied |
| Work Done → Accepted | Operations manager | Labor/material completeness (FR-007) |
| Accepted → Ready for Billing | Finance | Billing references present and not previously released |
| Ready for Billing → Billed | Finance | Reconciled confirmation from accounting (mechanism TO VERIFY) |

## Core Business Rules

- **RULE-01:** `work_order_id` never changes after creation (`FR-001`).
- **RULE-02:** billing release is blocked until work is accepted (`BR-002`, `FR-007`, `FR-008`).
- **RULE-03:** repeated export must reuse the same stable business reference for unchanged billing data (`FR-009`, `NFR-004`).
- **RULE-04:** cancellation before acceptance requires a recorded reason (`FR-011`, `FR-012`).
- **RULE-05:** emergency offline records require reconciliation and approval before billing (`BR-003`).

## Exception Scenarios

| Situation | Proposed behavior | Open dependency |
|---|---|---|
| Technician reports missing parts | Keep order in progress / record delay | Part catalog and stock policy |
| Evidence or time missing | Reject acceptance and return for correction | Mandatory fields by service type |
| Duplicate billing export attempt | Same external reference; reconciliation warning | Accounting interface semantics |
| Accounting endpoint unavailable | Queue/retry or controlled file re-export | Integration contract and IT decision |
| ERP temporarily unavailable | Approved emergency log, then reconcile | Business continuity owner |

## Decisions Required

**Open:** reopen after acceptance; multiple technicians; whether non-stock materials are permitted; owner of site data; full billing export contract; customer notification responsibilities.

This TO-BE model is an **analysis proposal**, not an approved design or implemented workflow.
