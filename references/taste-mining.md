# Taste Mining

## Purpose

This workflow exists to infer the Founder's taste without requiring the Founder to manually build a reference board.

The assistant should do the heavier work:

- gather reference candidates
- curate high-contrast comparison pairs
- ask compact preference questions
- infer stable taste signals from the answers

## Core Rule

Do not ask the Founder to describe taste in abstract words first.

Prefer:

- `A vs B`
- what feels closer
- what feels wrong
- which specific element is liked or disliked

This is a reverse-spec workflow for taste.

## Required Objects

Taste mining is not a standalone questionnaire.

It should always sit inside this chain:

1. `Principles Framework`
2. `UI Context Profile`
3. `Taste Mining Round`
4. `Taste Signal Matrix`
5. `Taste Principle Mapping`

The mining step only discovers preference signals.
It does not directly author builder prompts.

## Round Structure

Run in short rounds.

Recommended:

- `6-8` comparisons per round
- `1-2` dimensions per comparison only
- `2-4` rounds total before summarizing the taste profile

Each comparison should be controlled enough that the result can be written back into the matrix.

At minimum, every comparison should identify:

- the measured axis
- the related principle modules
- what stays roughly constant
- what is intentionally different

## Two-Layer Mining Model

### Layer A: Base Taste Scan

Purpose:

- infer the Founder's reusable long-term taste signals
- identify broad style tendencies that may carry across projects

Typical axes:

- calm vs dramatic
- editorial vs utilitarian
- soft vs sharp
- sparse vs dense
- warm vs cold
- ritual vs dashboard

This layer should stay relatively product-agnostic.

### Layer B: Contextual Taste Scan

Purpose:

- infer which expressions fit the current product type, user state, and protocol context
- filter out references that may match the Founder's general taste but are wrong for this specific product

The assistant should derive the reference pool from:

- product type
- user emotional state
- runtime posture
- interaction intensity
- trust posture
- protocol-defined route and screen contract

Examples:

- health, meditation, breathwork, recovery products should bias toward calm, trust, ritual, soft-scientific, and companion-like references
- workflow or B2B tools may bias toward clarity, density control, and system posture
- editorial or content products may bias toward typography, reading rhythm, and visual pacing

Do not run Contextual Taste Scan with a generic all-product reference pool.

## Before Running A Round

First derive a minimal `UI Context Profile` from the protocol.

This profile should at least define:

- product type
- core user state
- trust posture
- runtime posture
- density target
- companion level
- scientificness target
- forbidden drifts

Without this, contextual taste comparisons drift back into generic taste testing.

## Suggested Order

### Round 1: Base Taste Axes

Infer broad long-term preferences.

### Round 2: Contextual Product-Type Comparisons

Infer which same-family references best fit the current product.

### Round 3: Element Preferences

Infer concrete UI preferences:

- typography posture
- color posture
- spacing density
- card or surface behavior
- depth and shadow behavior
- icon or illustration behavior

### Round 4: Anti-Pattern Extraction

Infer what must be avoided:

- generic SaaS dashboard drift
- purple-gradient AI startup drift
- over-glassmorphism
- crowded card walls
- over-gamified widgets
- over-polished marketing theatrics

## Output Rule

Each round should end with:

- provisional taste signals
- strongest positive signals
- strongest negative signals
- unresolved questions for the next round

In addition, each round must write matrix-ready entries with:

- `Signal ID`
- `Taste Axis`
- `Direction`
- `Strength`
- `Confidence`
- `Evidence`
- `Affected Modules`
- `Context Fit`
- `Non-Negotiables`

After enough rounds, summarize into:

- base taste profile
- current product-type taste profile
- mother-style candidates
- forbidden tropes

## Relation To Refactoring UI

Taste mining does not replace design principles.

The process should keep these layers separate:

- `taste layer`: the Founder's preferred style and atmosphere
- `principles layer`: hierarchy, spacing, contrast, type scale, color layering, depth

Taste mining defines the style direction.
Principle compilation defines whether the execution is structurally good.

The output should therefore be read as:

- `Taste Signal Matrix` = what kind of modulation the Founder prefers
- `Taste Principle Mapping` = where that modulation is allowed to happen
- `Builder Translation Layer` = how that modulation becomes builder-safe instructions

Both layers are required:

- `Base Taste` without `Contextual Taste` becomes generic self-expression
- `Contextual Taste` without `Base Taste` becomes category mimicry

## Signal Quality Rule

If a round only produces statements like:

- "更高级"
- "更有感觉"
- "更温和"

then the round is incomplete.

The round should be pushed one step further until the result can be written into at least one structured signal such as:

- `warmth = medium-high`
- `scientificness = medium-high`
- `cold-systemness = low`
- `dashboard-density = low`
- `companionship = medium`

with evidence and affected modules attached.

## Escalation Rule

Escalate when:

- the Founder gives contradictory signals across multiple rounds
- the taste preference is clearly project-specific rather than reusable
- the real disagreement is about product positioning, not style
