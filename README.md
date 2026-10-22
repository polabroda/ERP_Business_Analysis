# ERP Business Analysis

This project presents an independent, end-to-end **pre-implementation business analysis case study** for a fictional field-services company preparing to evaluate an ERP solution.

The analysis focuses on business needs, requirements engineering, process improvement, scope prioritization, implementation risks, and a structured approach to ERP vendor assessment. **It does not represent a completed ERP implementation.**

---

# Project Overview

- Business context and problem definition
- Stakeholder mapping and discovery plan
- Business, functional, and non-functional requirements
- AS-IS and TO-BE business process analysis
- Requirements prioritization and MVP scope
- Risks, dependencies, and open decisions
- ERP selection criteria and fit-gap framework
- Requirements traceability and proposed acceptance scenarios

---

# Business Scenario

**Aster Field Services** is a **fictional** company with approximately 85 employees, two service depots, mobile technicians, and a central operations team. The organization handles customer maintenance requests, dispatches technicians, records labor and materials, and prepares information for invoicing.

Its processes currently rely on email, spreadsheets, paper job notes, and a separate accounting tool. The proposed ERP initiative aims to improve work-order traceability and create a reliable handoff from operations to finance.

This scenario, all stakeholder needs, example metrics, and vendor profiles are **illustrative assumptions**, not evidence from a real business engagement.

---

# Analysis Scope

The initial scope covers service work orders, dispatching, time and material capture, approval of completed work, invoice-ready data exports, shared reference data, and access controls.

Payroll, general-ledger replacement, advanced procurement, and a full CRM are explicitly **outside the proposed MVP**. No software product or implementation partner has been selected.

---

# Repository Structure

| File | Content |
|---|---|
| [01_business_context.md](01_business_context.md) | Problem statement, assumptions, goals, KPIs, boundaries |
| [02_stakeholders_and_discovery.md](02_stakeholders_and_discovery.md) | Stakeholders, elicitation approach, open questions |
| [03_requirements_catalogue.md](03_requirements_catalogue.md) | Traceable business, functional and non-functional requirements |
| [04_process_analysis.md](04_process_analysis.md) | Current-state and proposed workflows, states and business rules |
| [05_prioritization_and_scope.md](05_prioritization_and_scope.md) | MoSCoW prioritization, MVP and phased approach |
| [06_risks_and_dependencies.md](06_risks_and_dependencies.md) | Risk register, dependencies, assumptions and decisions |
| [07_erp_selection_framework.md](07_erp_selection_framework.md) | Screening, weighted evaluation, fit-gap and vendor questions |
| [08_traceability_and_acceptance.md](08_traceability_and_acceptance.md) | Requirements-to-process traceability and draft UAT scenarios |
| [diagrams/process_as_is.md](diagrams/process_as_is.md) | Current-state workflow in Mermaid |
| [diagrams/process_to_be.md](diagrams/process_to_be.md) | Proposed target workflow in Mermaid |

---

# Methodology

1. Define the fictional business problem and project boundaries.
2. Identify stakeholders and prepare a discovery plan.
3. Express needs as uniquely identified requirements, with priorities and validation status.
4. Compare the AS-IS workflow with a proposed TO-BE workflow.
5. Define a realistic MVP, dependencies, risks, and unresolved decisions.
6. Prepare criteria for ERP solution assessment rather than claiming a product selection.
7. Connect priority requirements to draft acceptance scenarios.

This project uses **MoSCoW**, **process mapping**, **requirements traceability**, and an illustrative **fit-gap assessment framework**. Mermaid diagrams render directly on GitHub.

---

# Tools and Techniques

- Business Analysis / Requirements Engineering
- Business Process Analysis (AS-IS / TO-BE)
- Stakeholder Mapping and Elicitation Planning
- MoSCoW Prioritization
- Risk and Dependency Analysis
- Fit-Gap and Vendor Evaluation Frameworks
- Markdown and Mermaid

---

# Goal

The goal is to demonstrate a structured approach to **ERP pre-implementation analysis**: turning business problems into testable requirements, managing scope and uncertainty, and preparing evidence-based criteria for later solution evaluation.

---

# Results

The case study delivers:

- A coherent set of **23 proposed requirements** across business, functional, and non-functional categories.
- Explicit AS-IS and TO-BE workflows with a controlled work-order lifecycle.
- A documented MVP scope and a dependency-aware phased approach.
- An illustrative risk register and ERP evaluation method.
- Draft acceptance scenarios traceable to selected requirements.

**These are analytical deliverables, not measured operational improvements or evidence of deployment.** All requirements and proposed decisions remain unvalidated outside this fictional case.

---

# Confidentiality and Limitations

This is an **independent, fictional portfolio case study**. It does not disclose or reproduce internal documents, datasets, requirements, vendor assessments, or other materials from any employer or client. Illustrative values are hypotheses, not actual company statistics. The analysis does not claim stakeholder sign-off, vendor demonstrations, software configuration, implementation, or user acceptance testing.

---

# Author

Paulina Broda
