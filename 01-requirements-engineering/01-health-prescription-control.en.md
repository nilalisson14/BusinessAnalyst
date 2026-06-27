# Sanitary Control of Prescriptions — National Prescription Control System

> [🇧🇷 Português](01-health-prescription-control.pt.md) · [← Back to index](../README.en.md)

| | |
| --- | --- |
| **Domain** | Public health, health surveillance, controlled medication |
| **Role** | Requirements Analyst / Requirements Engineer |
| **Format** | User stories with BDD/Gherkin acceptance criteria |
| **Deliverable** | 52 prototyped screens + user stories |

## Context and goal

A national system that centralizes control of medication prescriptions under health surveillance. I worked on the conception and detailing of requirements for the full lifecycle of controlled-prescription numbering: generation, distribution between surveillance bodies, assignment to prescribers and institutions, pharmacy dispensing, cancellation, and monitoring — with end-to-end traceability across the regulatory agency, state and city bodies, print shops, institutions, prescribers, and dispensing establishments.

## Documented functional scope

**Numbering generation and distribution**
- Generation and cancellation of numbering requests, with emission type (physical or electronic) and quantity.
- Print-shop requisition and distribution/receipt flow between bodies, with receipts.
- Print-shop registration and print template (format, paper, numbering, perforation).

**Assignment and dispensing**
- Assignment to prescribers and institutions with distinct rules per prescription type.
- Dispensing record distinguishing industrialized from compounded medication, with batch, registration, and controlled-substance control.
- Single, prolonged, and partial-use prescriptions, with incremental forms and visibility rules between establishments.
- Usage cancellation with audit trail.

**Lookups, cancellations, and monitoring (BI)**
- Public lookup in the national base, with states Authorized, Used, Partially Used, and Expired.
- Total and partial cancellation, with standardized reasons and mandatory justification.
- Dispensing-monitoring panels, rankings, CSV export, and SLA indicators per body.

## Actors and profiles

Regulatory agency, state and city surveillance bodies, print shop, institution (hospital/health unit), prescriber, and dispensing establishment (pharmacy), each with its own visibility rules and actions.

## Applied skills

Discovery with stakeholders in a complex institutional context · regulatory process mapping · functional and non-functional requirements · clear, testable user stories · BDD acceptance criteria · screen prototyping (UX) · modeling of compliance-sensitive rules, with attention to traceability, auditing, and health-data protection.

## Outcome

Prescription-numbering lifecycle specified end to end, with automatic dispensing that prevents improper reuse — the core sanitary-control objective. Traceable requirements aligned with prototypes, reducing rework between business and development in a high-criticality environment.
