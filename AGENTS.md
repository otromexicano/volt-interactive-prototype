# WORKFLOW AUTHORITY

This project is governed by:

docs/workflow/MASTER_WORKFLOW_PLAYBOOK.txt

Before performing any project phase, Codex MUST:

1. Read AGENTS.md.
2. Read docs/workflow/MASTER_WORKFLOW_PLAYBOOK.txt.
3. Identify the current approved phase/checkpoint.
4. Read only the canonical artifacts required by that phase.
5. Perform only the requested phase scope.
6. Run the phase-specific quality gate.
7. Stop before the next phase.
8. Wait for human approval when required.

The Master Workflow Playbook is the canonical process authority.

## Canonical phase order

The only authoritative canonical phase order is the sequence defined in
`docs/workflow/MASTER_WORKFLOW_PLAYBOOK.txt`:

Discovery
→ Product Definition
→ User Flow
→ Information Architecture
→ Interaction Contract
→ Visual Direction
→ Brand
→ Figma
→ Design System
→ Tokens
→ Code Connect
→ React Components
→ Frontend Engineering Standards
→ Storybook
→ Motion
→ Product Implementation
→ Playwright
→ Accessibility
→ Visual Regression
→ Responsive / Real Data
→ Performance
→ Figma ↔ Code Parity
→ Product Metrics
→ Release Gate
→ Case Study Evidence

Canonical status is recorded in
`docs/workflow/CANONICAL_WORKFLOW_STATUS.md`.

A canonical phase is complete only when 100% of its required inputs,
outputs, phase requirements, exit gate, traceability/evidence, required
read-only audit, and applicable human approval are satisfied. Historical
approval labels do not override missing Master Workflow requirements.

If AGENTS.md, a prompt, an existing document, or a prior AI-generated
artifact conflicts with the Master Workflow Playbook, STOP and report
the conflict before proceeding.

Do not silently reinterpret or skip workflow phases.

Do not begin a later phase because its work appears useful.

Do not implement Foundations, Components, Hi-Fi, Responsive, Prototype,
QA, or Case Study work before their corresponding workflow gates.

If a run is interrupted:
resume from the exact current checkpoint according to the Master
Workflow Playbook.

Human approval governs:
- UX direction selection
- visual direction selection
- brand identity selection
- significant product tradeoffs
- final quality approval



# Volt — Canonical Project Workflow

This file adapts the `CASE_STUDY_WORKFLOW_PLAYBOOK` to the existing Volt project. It governs future repository and Figma work without restarting, replacing, or erasing approved work.

## Project identity

- **Figma file:** Volt — E-commerce UI & Interactive Prototype
- **Repository:** `volt-interactive-prototype`
- **Prototype scope:** Interactive browser-based UI prototype focused on navigation, interaction, responsive behavior, and design-system fidelity.

Explicitly out of scope:

- Authentication
- Payments
- Checkout
- Backend commerce
- Real inventory
- Production transactions

## Working roles

- **Staff Product Designer:** Owns product framing, end-to-end experience coherence, interaction quality, and human design decisions.
- **UX Strategist:** Maintains source integrity, assumptions, open questions, information architecture, flows, and validation needs.
- **Design Systems Architect:** Defines the Primitive → Semantic → Component token architecture and prevents fragmented component families.
- **Design Engineer:** Builds the browser prototype with responsive behavior, interaction fidelity, maintainable implementation, and traceability to approved design.
- **Accessibility Reviewer:** Evaluates the work against WCAG 2.2 AA using automated and manual checks.
- **Design QA Reviewer:** Performs read-only phase audits, records defects and history, and verifies targeted remediation without silently redesigning approved work.

One person or agent may perform several roles, but each review must state which role is active.

## Historical Volt workflow — preserved, non-authoritative

The sequence below records the workflow previously used by Volt. It is
preserved for historical traceability only and must not govern canonical
phase order, phase status, or progression:

Brief
→ UX Assumptions
→ Information Architecture
→ Primary Flow
→ Wireframes
→ UX Hypotheses
→ Human Direction Selection
→ Visual Exploration
→ Human Visual Selection
→ Foundations
→ Components
→ Hi-Fi
→ Responsive
→ Figma Prototype
→ Functional Prototype
→ Accessibility Audit
→ Accessibility Remediation
→ Final Design QA
→ Targeted Remediation
→ Case Study Narrative
→ Figma Case Study Boards

Preserve the artifacts and approvals produced under this historical sequence.
Map them into the Master Workflow by evidence, but do not infer canonical
completion from their former numbering or approval label.

## Evidence and claim integrity

Use these labels consistently:

- **FACT:** Directly supplied by the source brief or observable in an approved artifact.
- **ASSUMPTION:** A provisional belief requiring validation.
- **DESIGN DECISION:** A chosen design interpretation with rationale and status.
- **OPEN QUESTION:** Information not supplied or validated.

Never fabricate research, analytics, customer feedback, usability outcomes, business metrics, product impact, interviews, production usage, or validation. Do not promote assumptions or design decisions to facts. Historical failures and QA history must not be erased.

## Project rules

- Inspect current Figma and repository artifacts before editing.
- Preserve valid historical explorations and approved documentation.
- Preserve Figma pages `90 — Candidates` and `99 — Archive`.
- Human approval governs product direction, UX selection, visual selection, major redesigns, and final quality.
- AI is an accelerator, not the case-study story; human judgment and quality governance remain explicit.
- Reuse approved variables and components once they exist.
- Avoid detached instances and duplicate component families.
- Avoid raw colors when semantic roles exist.
- Avoid random spacing values; use the approved spacing system.
- Use Primitive → Semantic → Component token architecture.
- Target WCAG 2.2 AA.
- Automated accessibility checks supplement but never replace manual checks.
- Major phases require a read-only audit before remediation.
- During an audit, record findings first and stop modifying the audited artifact. Remediation begins only as a separate, explicitly authorized step.
- Preserve earlier QA findings, failed approaches, superseded directions, and remediation history.
- Do not delete approved historical documentation merely to normalize names.

## Phase controls

Each major phase must have:

1. A clearly named artifact or canonical file.
2. Source and evidence classifications.
3. A human approval checkpoint where the workflow requires selection.
4. A read-only audit before any remediation pass.
5. Traceability to the Figma node, repository file, or both.

Do not advance into the next phase merely because a draft exists. Pending work remains visibly Pending.

## Git rule

Do not run `git add`, `git commit`, or `git push` from Codex. Git checkpoints are performed separately by the user in PowerShell after a phase is approved.

## Product Design + Design Engineering Master Workflow

The reusable project methodology is defined in:

`docs/workflow/MASTER_WORKFLOW_PLAYBOOK.txt`

Use that playbook for substantial work involving:

- product discovery and definition
- user flows and information architecture
- interaction contracts
- visual direction and brand
- Figma and Figma MCP
- design systems and tokens
- Figma-to-code workflows
- React and Next.js implementation
- TypeScript architecture
- Storybook
- motion and microinteractions
- Playwright
- accessibility
- visual regression
- responsive and real-data validation
- performance
- Figma ↔ code parity
- product metrics
- release gates
- case-study evidence

The existing Volt workflow and historical approvals remain valid as historical
evidence. They do not by themselves establish completion under the Master
Workflow.

Do not delete or restart valid historical work merely because the Master
Workflow uses a different phase model. Complete only the missing canonical
requirements and preserve the original evidence and decisions.

For the current project:

1. Preserve existing approved artifacts.
2. Map completed work into the new master workflow.
3. Add only the missing engineering, interaction, QA, and evidence layers.
4. Continue from the latest approved checkpoint.

### Engineering standard

The browser prototype uses:

- Next.js
- React
- TypeScript
- Tailwind CSS
- reusable component architecture

Use current version-matched Next.js guidance from `prototype/AGENTS.md`.

Prefer:

- Server Components when appropriate
- Client Components only when interaction requires them
- typed component APIs
- semantic HTML
- reusable components
- design tokens instead of arbitrary values
- explicit loading, empty, error, and success states
- accessible keyboard interaction
- reduced-motion support
- responsive behavior based on real content

### Completion rule

A feature is not complete when its Figma frame is complete.

A feature is complete only after the applicable gates pass:

DESIGN
+
INTERACTION
+
DESIGN SYSTEM
+
CODE
+
RESPONSIVE
+
ACCESSIBILITY
+
TESTING
+
PERFORMANCE
+
FIGMA/CODE PARITY
+
CLAIM INTEGRITY
+
CASE STUDY EVIDENCE

### Planning

For substantial features, architecture changes, or multi-phase implementation work, create an execution plan before modifying the implementation.

The plan must identify:

- source artifacts
- existing approved work
- intended changes
- files affected
- Figma dependencies
- component/system implications
- interaction states
- accessibility considerations
- testing strategy
- case-study evidence to preserve

