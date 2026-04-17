# Review Loop

## Goal

Review generated UI quickly, not ceremonially.

## Default Loop

1. inspect the generated UI
2. compare it with the protocol-derived screen contract
3. identify the top structural issues first
4. identify the top visual issues second
5. write a compact revision brief
6. rerun generation

## Review Order

Always review in this order:

1. wrong flow or missing state
2. wrong screen hierarchy
3. wrong CTA emphasis
4. wrong information density
5. wrong visual posture

Do not start with cosmetic notes if the screen logic is wrong.

## Revision Brief Shape

Keep revision briefs short.

Good revision briefs usually contain:

- `3-7` corrections
- direct replace or reorder instructions
- explicit notes on what to keep

## Stop Rule

Stop the loop and escalate if:

- the same structural issue survives more than `2` rounds
- the UI keeps exposing unresolved protocol ambiguity
- the problem is clearly in the screen contract, not the builder output
