# Workflow

## Purpose

This workflow exists to make UI a fast downstream concretization step after protocol work, not a parallel speculative track.

## Minimal Input Set

At minimum, the workflow should have:

- confirmed boundary and intent
- confirmed state flow
- confirmed data objects
- confirmed major effects
- confirmed route or screen ownership

If these are missing, push back to the protocol workflow.

## Standard Sequence

1. read protocol docs
2. load `Principles Framework v1`
3. derive a minimal `UI Context Profile`
4. if taste is unclear, run taste mining rounds
5. write every round result into `Taste Signal Matrix`
6. compile `Taste Principle Mapping`
7. extract canonical screens
8. extract user-visible states per screen
9. define screen blocks and CTA hierarchy
10. draw low-fi wireframes in text or ASCII
11. define one visual direction
12. use external rule libraries such as `ui-ux-pro-max` to tighten accessibility, touch, responsive, and performance constraints
13. define AI-builder handoff rules
14. generate UI
15. run a fast review loop

## What This Workflow Optimizes For

- speed
- clarity
- AI-builder friendliness
- low rework cost
- matrix-based taste capture instead of loose style adjectives

It does not optimize for:

- pixel-perfect custom design before implementation
- large design systems
- long speculative visual exploration

`ui-ux-pro-max` is best used here as a guardrail and lookup layer, not as the primary workflow controller.

## Structural Rule

Do not jump directly from:

- reference comparisons
- founder taste notes
- or mood words

to:

- builder prompts
- visual direction briefs
- or screen styling decisions

The required bridge is:

1. `Principles Framework`
2. `UI Context Profile`
3. `Taste Signal Matrix`
4. `Taste Principle Mapping`

Without this bridge, the output becomes hard for AI builders to reproduce consistently.

## Escalation Rule

Escalate when:

- the protocol is still changing
- generated UI exposes missing business rules
- a screen needs structural redesign more than once
- brand or visual direction is still fundamentally undecided

## Closure Model

The intended closure loop is:

1. `protocol-driven-build` stabilizes product logic and route/screen ownership
2. `protocol-ui-fastlane` turns that into:
   - UI contracts
   - builder briefs
   - external handoff assets
3. UI is generated or implemented
4. the project returns upstream for:
   - traceability checks
   - audit / diff against the confirmed protocol

This workflow is complete when the UI handoff is precise enough that external builders or implementers do not need to invent product logic.
