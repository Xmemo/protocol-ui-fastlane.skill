# AI Builder Handoff

This reference defines how to prepare UI outputs for external AI builders such as:

- Lovable
- Gemini
- Claude
- GPT

## Core Rule

Do not hand off only aesthetics.

Hand off:

- screen list
- purpose of each screen
- required blocks
- required states
- primary and secondary CTA
- structural constraints
- visual direction
- anti-patterns

## What Builders May Decide

The builder may decide:

- exact spacing
- exact component styling
- icon choice within a defined tone
- typography implementation details within the approved posture

## What Builders Must Not Decide

The builder must not invent:

- extra screens
- extra business logic
- hidden steps in the flow
- missing state behavior
- off-brand UI tropes

## Recommended Builder Input Shape

For each run, provide:

1. a short product or feature summary
2. canonical screen list
3. screen-by-screen contracts
4. visual direction
5. anti-patterns
6. explicit revision target if this is not the first pass

## Good Builder Prompt Style

Prefer:

- direct constraints
- bounded flexibility
- concrete layout guidance
- explicit "must include / must not include" language

Avoid:

- vague inspiration dumping
- conflicting style signals
- asking the builder to "figure out the UX"
