---
name: interaction-contract
description: Interaction specification for an approved component or flow before implementation. Use when explicitly defining states, triggers, transitions, keyboard/focus behavior, responsive behavior, motion, and reduced-motion behavior. Do not use for visual art direction, product strategy, implementation architecture, or QA audits.
argument-hint: "[component, flow, or interaction]"
metadata:
  author: volt-project
  version: "1.0.0"
---

# Interaction Contract

Use this skill to define behavior before implementing interaction.

## Required state coverage

Consider where applicable:

- initial
- hover
- focus-visible
- pressed
- selected
- disabled
- loading
- populated
- empty
- partial
- error
- retry
- stale
- success

## Interaction coverage

Define:

- trigger
- system response
- visual feedback
- state transition
- persistence
- cancellation
- keyboard behavior
- focus behavior
- responsive behavior
- reduced-motion behavior

## Motion

Motion must communicate state, hierarchy, causality, or spatial relationship.

Avoid decorative motion that reduces clarity.

Respect `prefers-reduced-motion`.

## Contract format

For substantial interactions document:

Trigger → State change → Feedback → Duration/behavior → Accessibility behavior → Resulting state

Do not implement ambiguous interaction behavior. Resolve or explicitly mark ambiguity first.
