# R&D&I Opportunity Governance — Partner Selection Platform

> [🇧🇷 Português](02-rd-opportunity-governance.pt.md) · [← Back to index](../README.en.md)

| | |
| --- | --- |
| **Domain** | Research, Development & Innovation (R&D&I); partner selection; regulatory compliance |
| **Role** | Requirements Analyst / Requirements Engineer |
| **Deliverable** | 183 prototyped screens + user stories |

## Context and goal

A corporate module (large state-owned energy company) supporting the management of R&D&I opportunities and the selection of technology partners. I documented the full flow, from opportunity creation by the technical area to winning-proposal selection, through pre-proposal submission, committee judgment, competence-limit approvals, and administrative functions — always aligned with regulatory R&D&I investment obligations.

## Documented functional scope

**Opportunity registration and lifecycle**
- Creation in three modes (Public, Thematic, and Direct selection), each with a two-step flow.
- Classification, deliverables detailing, cost estimation, and execution team.
- Linking of related projects, partnerships, competence-limit approvers, and committee composition.
- **State machine:** Draft → Submitted → Published → Judgment → Selection → Finalized, with version history.

**Pre-proposals and judgment**
- Pre-proposal submission with compliance declaration, schedule, and expense breakdown (capital, current, counterpart, other sources).
- Judging committee with acceptance registration/refusal, automatic and manual criteria evaluation, and consolidated view.
- Multi-level approval (technical manager and partner technical manager) with justification.

**Collaborative room, reports, and administration**
- Communication channel across profiles, with public discussion, direct messaging, notices, and export.
- Result reports (XLSX), administration (parameters, tags, evaluation criteria), and administrative functions with acceptance terms and history.

## Actors and profiles

Interlocutor, Coordinator (proposer), Technical Manager, Partner Technical Manager, Judging Committee Member, and Administrator, each with its own dashboard and permissions.

## Applied skills

Multi-level approval flow modeling with a state machine · selection and contracting process mapping · financial rules (line items, counterpart, sources) · user stories and acceptance criteria for complex flows · prototyping of 180+ screens · alignment between business rules, governance, and regulatory compliance.

## Outcome

A complete, auditable selection flow, with conflict-of-interest governance preserved by a business rule (acceptance term) and traceability of all substitutions, approvals, and cancellations. Impact analysis reduced rework by anticipating effects on existing features.
