# 03 – Requirements Catalogue

The following requirements form a **fictional, proposed baseline**. Identifiers are stable so they can be referenced by the workflow, MVP plan, risk register and acceptance scenarios. No requirement has been approved by a real stakeholder.

**Status legend:** `PROPOSED` = derived from this case; `TO VERIFY` = awaits a specific business or technical confirmation; `BLOCKED` = implementation depends on unavailable input. Priority is a suggested MoSCoW category, not a customer decision.

## Business Requirements

| ID | Requirement | Rationale | Priority | Status |
|---|---|---|---|---|
| BR-001 | Every new service order shall use one unique reference shared by operations and finance. | Reduce reconciliation errors. | Must | PROPOSED |
| BR-002 | Work may be released for billing only after documented operational acceptance and completeness checks. | Prevent premature invoicing. | Must | PROPOSED |
| BR-003 | Emergency work recorded outside the system during an outage shall be reconciled into the official record before billing. | Preserve continuity without losing traceability. | Should | TO VERIFY |

## Functional Requirements

| ID | Requirement | Suggested acceptance evidence | Priority | Status |
|---|---|---|---|---|
| FR-001 | An authorized user can create a work order linked to a customer, site and issue description; the system assigns an immutable unique ID. | Creation and uniqueness checks. | Must | PROPOSED |
| FR-002 | A work order follows the controlled status lifecycle defined in `04_process_analysis.md`. | Allowed and forbidden transitions tested. | Must | PROPOSED |
| FR-003 | A dispatcher can assign an approved order to an available technician and planned service date. | Assignment saved and visible. | Must | PROPOSED |
| FR-004 | A technician can record work date, time spent and service notes against an assigned work order. | Entries linked to ID and author. | Must | PROPOSED |
| FR-005 | An authorized user can record quantities of materials consumed, including item identifier and unit. | Usage visible before acceptance. | Must | PROPOSED |
| FR-006 | A technician can attach completion evidence to a work order. | Attachment reference retained. | Should | PROPOSED |
| FR-007 | An operations manager can accept completed work only if required labor/material records are present or explicitly marked not applicable. | Missing-data block works. | Must | PROPOSED |
| FR-008 | A finance user can generate invoice-ready records for accepted work with a unique external reference. | Export contains mandatory fields. | Must | TO VERIFY |
| FR-009 | Repeating the same export shall not create a second export item with a new business identifier for the same order/version. | Repeat-export test. | Must | TO VERIFY |
| FR-010 | Users can search and filter work orders by ID, customer, owner and status, within their permissions. | Filter/search demonstration. | Should | PROPOSED |
| FR-011 | An authorized user can cancel an order before acceptance and must enter a reason. | Cancellation authorization and audit test. | Should | PROPOSED |
| FR-012 | The system records significant status, assignment and approval changes with actor and timestamp. | Audit entries inspected. | Must | PROPOSED |
| FR-013 | Warehouse personnel can propose replenishment purchase requests linked to part shortages. | Linked request exists. | Could | PROPOSED |
| FR-014 | Managers can view a dashboard of order volumes, aging and billing readiness. | Dashboard values agree with source records. | Could | PROPOSED |
| FR-015 | Customers can submit and track requests through a portal. | Portal workflow review. | Won't (MVP) | PROPOSED |

## Non-functional Requirements

| ID | Requirement | Verification proposal | Priority | Status |
|---|---|---|---|---|
| NFR-001 | Access to records and actions shall be governed by defined roles, including separation of work acceptance and billing release where required. | Role matrix and negative tests. | Must | TO VERIFY |
| NFR-002 | Status and approval history shall be auditable and retained for a policy-defined period. | Retention policy and audit review. | Must | TO VERIFY |
| NFR-003 | Standard search and order-detail actions should respond within 3 seconds at the 95th percentile for 20 concurrent users. | Performance test plan. | Should | TO VERIFY |
| NFR-004 | The billing interface must support duplicate detection and reconciliation of failed transfers. | Integration test and replay. | Must | BLOCKED |
| NFR-005 | Recovery objectives and backup arrangements shall be agreed with IT before go-live. | Approved RPO/RTO and recovery-test plan. | Must | TO VERIFY |

**Count:** 3 business + 15 functional + 5 non-functional = **23 requirements**.

## Proposed Data Entities

| Entity | Key / relationship | Minimum relevant fields | Ownership question |
|---|---|---|---|
| Customer | `customer_id` | Name, active flag, billing reference | CRM or accounting? |
| Site | `site_id` → `customer_id` | Location, service details | Who maintains sites? |
| Work order | `work_order_id` → customer/site | Issue, status, owner, timestamps | Operations |
| Assignment | `assignment_id` → work order | Technician, service date | Dispatch |
| Labor entry | `labor_entry_id` → work order | Author, duration, note | Technician + manager review |
| Material usage | `usage_id` → work order/part | Quantity, unit, source | Warehouse |
| Approval | `approval_id` → work order | Approver, outcome, timestamp | Operations manager |
| Billing export | `export_id` → work order | Version, external ref, status | Finance + IT |

## Open Questions Before Baseline Approval

- Who owns customer and site master data (`BR-001`, `FR-001`)?
- What is the exact accounting import format (`FR-008`, `FR-009`, `NFR-004`)?
- May a work order be reopened after acceptance (`FR-002`, `BR-002`)?
- What evidence is mandatory by service category (`FR-007`)?
- What audit-retention and recovery obligations apply (`NFR-002`, `NFR-005`)?

**Note:** requirements are proposed statements for portfolio illustration. They must not be treated as implemented features.
