# Volt — E-commerce UI & Interactive Prototype

**Project status:** In progress

**Current canonical phase:** PHASE 05 — INTERACTION CONTRACT — COMPLETE

**Last canonical phase passing 100%:** PHASE 05 — INTERACTION CONTRACT

**Next canonical phase:** PHASE 06 — VISUAL DIRECTION — NOT STARTED

Canonical status authority: [docs/workflow/CANONICAL_WORKFLOW_STATUS.md](docs/workflow/CANONICAL_WORKFLOW_STATUS.md)

**Project type:** Portfolio concept / interactive UI prototype

**Source:** Goodbrief design brief

## Primary disciplines

- Product Design
- UX/UI
- Design Systems
- Responsive Design
- Accessibility
- Design Engineering

## Project objective

Transform an ambiguous electronics e-commerce brief into an approachable, responsive shopping experience focused on product discovery, clarity, visual delight, and easy access to support.

## Prototype objective

Build a real browser-based interactive UI prototype rather than relying only on static Figma screens.

The prototype is not intended to implement real commerce functionality. It will demonstrate UI navigation and interaction only; payments, checkout, authentication, accounts, backend commerce, real inventory, production transactions, and other production commerce behavior are out of scope.

## Project overview

Volt is an in-progress portfolio project exploring how an ambiguous source brief can be developed into a documented product-design process, a coherent responsive interface, and eventually a coded interactive prototype.

## Original brief

The supplied Goodbrief source brief describes an electronics corner shop and asks for a trendy, white website that makes contacting the company easy while encouraging catalogue browsing. It is recorded without embellishment in [docs/00-project-brief.md](docs/00-project-brief.md).

## Problem framing

The initial framing focuses on making electronics discovery simple and delightful while keeping human support easy to reach. Current statements are hypotheses and working decisions, not validated research findings. See [docs/01-discovery.md](docs/01-discovery.md).

## Scope

In scope:

- Product discovery and catalogue-oriented UI
- Responsive interface design
- Reusable design-system foundations and components
- Accessible interaction patterns
- Browser-based navigation and interaction
- Design and implementation QA
- Documentation of the design process and AI-assisted workflow

Out of scope:

- Payments and checkout
- Authentication and accounts
- Backend commerce
- Real inventory
- Production transactions

## Design process and workflow status

Figma is the primary design artifact. This repository preserves supporting documentation, implementation history, and the current coded-prototype scaffold. Canonical workflow order and completion are governed by [AGENTS.md](AGENTS.md), the [Master Workflow Playbook](docs/workflow/MASTER_WORKFLOW_PLAYBOOK.txt), and the [Canonical Workflow Status](docs/workflow/CANONICAL_WORKFLOW_STATUS.md).

Historical Volt artifacts remain approved historical evidence, but their former phase numbers do not establish canonical completion. Under the strict Master Workflow reconciliation, **PHASE 01 — DISCOVERY is COMPLETE**, **PHASE 02 — PRODUCT DEFINITION is COMPLETE**, **PHASE 03 — USER FLOW is COMPLETE**, **PHASE 04 — INFORMATION ARCHITECTURE is COMPLETE**, and **PHASE 05 — INTERACTION CONTRACT is COMPLETE**. The next canonical phase is **PHASE 06 — VISUAL DIRECTION**, which has not started.

## Historical approved Figma milestones

These milestones preserve the original Volt workflow history. Their labels and approvals remain traceable but do not override current canonical status.

| Milestone | Frame | Status | Figma node |
| --- | --- | --- | --- |
| 00 — Cover | COVER — Project Overview | **APPROVED** | `5:2` |
| 01.1 — Original Brief | DISCOVERY — 01 Original Brief | **APPROVED** | `11:2` |
| 01.2 — Brief Audit | DISCOVERY — 02 Brief Audit | **APPROVED** | `15:2` |
| 01.3 — Problem Framing | DISCOVERY — 03 Problem Framing | **APPROVED** | `25:2` |
| 02 — UX Assumptions | DISCOVERY — 04 UX Assumptions | **COMPLETE / APPROVED** | `34:2` |
| 03 — Information Architecture | IA — 01 Product Architecture | **COMPLETE / APPROVED** | `39:2` |
| 04 — Primary Flow | FLOW — 01 Primary Discovery & Support | **COMPLETE / APPROVED** | `44:2` |

## Repository structure

```text
AGENTS.md
docs/
  BRIEF.md
  UX_ASSUMPTIONS.md
  INFORMATION_ARCHITECTURE.md
  PRIMARY_FLOW.md
  00-project-brief.md
  01-discovery.md
  02-product-definition.md
  03-user-flow.md
  04-information-architecture.md
  05-interaction-contract.md
  02-ia-flows.md
  03-wireframes.md
  04-explorations.md
  05-foundations.md
  06-components.md
  07-hi-fi.md
  08-responsive.md
  09-prototype.md
  10-qa.md
  11-case-study.md
  decision-log.md
  workflow/
    MASTER_WORKFLOW_PLAYBOOK.txt
    CANONICAL_WORKFLOW_STATUS.md
prototype/
case-study/
archive/
```

The `prototype/` directory now contains a Create Next App scaffold using Next.js, React, TypeScript, and Tailwind CSS. It remains framework scaffolding only; it is not evidence that React Components, Product Implementation, accessibility, testing, responsive, or release gates are complete.

## Figma

The [main Volt Figma project](https://www.figma.com/design/UIEx2VVwyPeGFUzwkh2dkn/Volt-%E2%80%94-E-commerce-UI---Interactive-Prototype) is the primary design artifact and design source of truth. The repository preserves supporting documentation, the current framework scaffold, and future implementation history.

## Interactive prototype

The intended prototype remains a real browser-based responsive UI focused on navigation and interaction. The framework scaffold exists, but Volt product implementation and its downstream gates remain **Pending**.

## Accessibility

Accessibility is a core discipline and an experience principle for the project. Specific requirements, audits, and findings are **Pending**.

## QA

Design, responsive, accessibility, and implementation QA plans and findings are **Pending**.

## Case study

The final case study narrative and verified outcomes are **Pending**. It will not claim research, impact, or results that did not occur.

## Documentation policy

Project documentation uses the following evidence labels:

- **FACT:** Directly supplied by the original brief or an observable artifact.
- **ASSUMPTION:** A temporary design assumption.
- **HYPOTHESIS:** Something intended to be evaluated.
- **DECISION:** A design or product choice and its rationale.
- **EVIDENCE:** An observed testing, QA, accessibility, or implementation finding.
- **RESULT:** An outcome that actually occurred.

Assumptions and hypotheses must never be presented as research findings. The project must not invent users, interviews, usability results, analytics, conversion improvements, client feedback, production usage, or business impact.

## Version and history policy

Meaningful design and implementation history must be preserved.

- In Figma, `90 — Candidates` holds viable alternatives under evaluation.
- In Figma, `99 — Archive` holds superseded historical artifacts.
- In Git, commits preserve meaningful documentation and implementation milestones.
- History must not be rewritten simply to make the project appear cleaner.

## Current canonical status

- **PHASE 01 — DISCOVERY:** COMPLETE
- **PHASE 02 — PRODUCT DEFINITION:** COMPLETE
- **PHASE 03 — USER FLOW:** COMPLETE
- **PHASE 04 — INFORMATION ARCHITECTURE:** COMPLETE
- **PHASE 05 — INTERACTION CONTRACT:** COMPLETE
- **LAST PHASE PASSING 100%:** PHASE 05 — INTERACTION CONTRACT
- **NEXT CANONICAL PHASE:** PHASE 06 — VISUAL DIRECTION
- **PHASE 06 STATUS:** NOT STARTED
- **PHASE 04 STARTED:** YES
- **PHASE 05 STARTED:** YES
- **PHASE 06 STARTED:** NO

The historical Product Brief, UX Assumptions, Information Architecture, and Primary Flow remain preserved as evidence. They must be evaluated against the Master Workflow rather than treated as four completed canonical phases. Wireframes remain a historical future artifact, not a standalone canonical phase. See [CANONICAL_WORKFLOW_STATUS.md](docs/workflow/CANONICAL_WORKFLOW_STATUS.md) for the crosswalk and blockers.
