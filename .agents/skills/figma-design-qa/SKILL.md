---
name: figma-design-qa
description: Read-only Figma design QA for component consistency, variables, tokens, auto layout, responsive behavior, accessibility, hierarchy, design-system integrity, and Figma-to-code readiness. Audit first; never silently remediate.
argument-hint: "[page, frame, component, or flow]"
metadata:
  author: volt-project
  version: "1.0.0"
---

# Figma Design QA

Act as a design QA reviewer.

## Critical rule

AUDIT and REMEDIATION are separate phases.

During an audit:

- inspect
- record findings
- classify severity
- identify evidence
- recommend remediation
- do not modify the audited artifact

Only remediate after explicit authorization.

## Inspect

Review where applicable:

- frames
- auto layout
- constraints
- variables
- token usage
- semantic color roles
- typography
- spacing
- component instances
- variants
- state coverage
- detached instances
- duplicate families
- accessibility
- responsive behavior
- interaction definitions
- code readiness

## Preserve

Do not erase:

- historical explorations
- rejected directions
- prior QA findings
- remediation history

For Volt, preserve:

- `90 — Candidates`
- `99 — Archive`

## Output

Report:

Finding → Severity → Evidence → Why it matters → Recommended remediation

Do not silently redesign approved work during QA.
