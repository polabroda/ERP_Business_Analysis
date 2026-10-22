# 02 – Stakeholders and Discovery Plan

This file describes **hypothetical stakeholders** and a **proposed elicitation plan**. No real interviews or workshops were conducted for this portfolio case.

## Stakeholder Map

| Role | Main concern | Expected contribution | Engagement |
|---|---|---|---|
| Executive sponsor | Business value, delivery risk, budget | Objectives, scope decisions | Kick-off and steering review |
| Operations manager | Workflow control and job acceptance | Status rules, approvals, exceptions | Workshop and validation |
| Dispatcher | Work assignment, visibility, prioritization | Current dispatch flow, edge cases | Shadowing and walkthrough |
| Field technician | Efficient job reporting | Time entry, materials, attachments | Prototype review |
| Warehouse lead | Part availability and usage records | Catalog, stock rules, reconciliation | Process workshop |
| Finance lead | Reliable and non-duplicated billing input | Export contract, acceptance checks | Integration workshop |
| IT / security representative | Access, uptime, integrations, data quality | NFRs and constraints | Technical review |
| Customer service representative | Customer/site accuracy | Intake, customer communications | Interview |

## Discovery Approach (proposed)

**Step 1 – Document review:** collect current order forms, timesheets, inventory sheets, invoice import specifications and role descriptions.

**Step 2 – Process walkthroughs:** follow one standard job and one emergency job from customer request to finance handoff; identify manual decisions and rework.

**Step 3 – Cross-functional workshop:** agree on core states, data owners, mandatory fields, and the conditions for billing readiness.

**Step 4 – Validation:** review the requirements catalogue, model exceptions and confirm MVP boundaries with named decision owners.

## Sample Elicitation Questions

1. Which event creates an official work order and who may create it?
2. Can two requests refer to the same site and incident; how are duplicates detected?
3. Who may approve a job for scheduling, and what happens when approval is rejected?
4. Can a dispatcher assign two technicians to one work order?
5. Are technicians allowed to add parts not currently present in the stock catalog?
6. Which exact evidence must be present before the operations manager accepts work?
7. Who may mark an order as ready for billing, and can that decision be reversed?
8. What is the authoritative customer/site identifier in the accounting tool?
9. How should a repeated export be prevented from creating duplicate invoices?
10. What is the fallback when the system is temporarily unavailable?
11. Which combinations of permissions would create a separation-of-duties risk?
12. Which historical records must be migrated, and how will data quality be checked?

## Working Outputs

- Stakeholder roles and proposed decision owners
- AS-IS process description with known/assumed pain points
- Requirements list with validation status
- Open issues and decisions requiring resolution

## Validation Status

All stakeholder needs in this case are **scenario-derived / PROPOSED**. Before real use, each one would require evidence, an accountable business owner, and confirmation.
