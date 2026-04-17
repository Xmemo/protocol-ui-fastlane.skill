---
name: protocol-ui-fastlane
description: Turn confirmed protocol specs into fast, AI-builder-friendly UI contracts, low-fi wireframes, visual direction, and revision briefs. Use after protocol stages are stable, especially when the user will rely on Lovable, Gemini, or other AI tools to generate UI quickly.
---

# Protocol UI Fastlane

This skill exists for one specific job:

- take a protocol-defined product or feature
- translate it into a minimal but buildable UI pack
- hand that pack to AI builders such as Lovable, Gemini, Claude, or GPT
- review the generated UI quickly and iterate with bounded revision briefs
- when needed, mine the Founder's aesthetic taste first so the UI pack reflects stable taste signals instead of generic builder defaults

This is not a UI-first skill.

This skill assumes the core product logic is already stable enough.

## When To Use

Use this skill when:

- the protocol or product logic is already mostly confirmed
- the user wants UI to be fast, cheap, and easy to swap later
- the user will rely on AI builders rather than heavy custom design workflows
- the goal is not perfect design-system purity but fast, reviewable UI convergence
- the Founder wants the system to learn their taste through reference comparisons instead of writing long design opinions

Typical triggers:

- "根据协议文档做 UI"
- "把这个 feature 变成可交给 Lovable 的 UI 包"
- "先不要写代码，先把 UI 规格和审稿包做出来"
- "帮我把 AI 生成的 UI 快速审一下并给 revision brief"

## When Not To Use

Do not use this skill when:

- boundary, state, or data are still unstable
- the route or screen contract is still moving heavily
- the user is actually asking for direct frontend implementation
- the task is a brand-new visual exploration without any product logic

If hidden business logic keeps appearing during UI work, stop and send the task back to the protocol workflow instead of papering over the gap with design.

## Required Input Gate

Default minimum gate:

- `Stage 0` Boundary / Intent confirmed
- `Stage 1` State confirmed
- `Stage 2` Memory / Data confirmed
- `Stage 3` Effects / Actions confirmed
- `Stage 5` Route / Screen Contract confirmed

Recommended gate for best results:

- `Stage 0-8` confirmed

Do not let UI exploration become a substitute for unresolved product decisions.

## Upstream And Downstream Boundary

This skill is downstream of `protocol-driven-build`.

It starts when protocol logic is stable enough and should usually stop at one of these points:

1. a builder-ready UI handoff pack is complete
2. an external platform handoff pack is complete
3. a fast review / revision brief loop is complete

It does not replace:

- product logic definition
- data model decisions
- API semantics
- route ownership decisions

If those start changing during UI work, push the task back upstream instead of silently patching around it.

After generated or implemented UI exists, the workflow should feed back into `protocol-driven-build` for traceability and audit.

## Core Principles

1. `Protocol first, UI second`
   UI exists to express settled logic, not to discover the logic.

2. `UI delivery should be low-cost, not low-quality`
   The goal is to reduce Founder effort and shorten iteration time, not to accept cheap-looking output.
   Prefer lightweight artifacts such as text specs, ASCII wireframes, and AI-builder-ready briefs so the UI can be generated, reviewed, replaced, and tightened quickly while still targeting premium presentation quality.

3. `One strong direction, not five moodboards`
   Pick one visual posture per surface and make it buildable.

4. `Fast review beats perfect polish`
   Ship one concrete UI direction into an AI builder, review it, tighten it, and iterate.

5. `AI-friendly by default`
   Outputs must be explicit enough that external AI tools can generate usable UI without inventing business logic.

6. `External resources are leverage`
   Reuse current product docs, screenshots, builder outputs, existing code, reference apps, and design libraries before inventing from scratch.

7. `Premium output with low Founder overhead`
   The Founder should not need to micromanage design decisions.
   The skill should absorb the translation work, use external resources aggressively, and produce UI that feels intentional and high-quality rather than default-builder generic.

## Supported Modes

### Mode A: Protocol -> UI Pack

Use when UI does not exist yet.

Goal:

- turn protocol artifacts into screen contracts, wireframes, and AI builder briefs

### Mode B: AI Output Review

Use when Lovable, Gemini, Claude, or another builder already generated UI.

Goal:

- review the output against the protocol
- generate a compact `UI_Revision_Brief`
- avoid a full redesign unless the structure is fundamentally wrong

### Mode C: Reverse-UI Tightening

Use when UI already exists in code.

Goal:

- reverse-spec the current UI
- compare it to the protocol
- identify ambiguity, drift, and revision priorities

### Mode D: Founder Taste Mining

Use when the Founder does not want to prepare a full reference board manually.

Goal:

- load `Principles Framework v1` first
- derive a minimal `UI Context Profile` from the protocol
- run a short `Base Taste Scan`
- then run a product-aware `Contextual Taste Scan`
- capture fast like/dislike judgments
- write stable taste signals into a `Taste Signal Matrix`
- map those signals back to principle modules instead of leaving them as loose adjectives
- turn those signals into reusable mother-style entries later

## Read Order

Read and follow:

- `references/principles-framework-v1.md`
- `references/workflow.md`
- `references/ai-builder-handoff.md`
- `references/review-loop.md`
- `references/taste-mining.md`
- `assets/Taste_Mining_Round_Template.md`
- `assets/UI_Context_Profile_Template.md`
- `assets/Taste_Signal_Matrix_Template.md`
- `assets/Taste_Principle_Mapping_Template.md`
- `assets/Builder_Translation_Layer_Template.md`
- `assets/Screen_Contract_Pack_Template.md`
- `assets/Visual_Direction_Brief_Template.md`
- `assets/AI_UI_Build_Brief_Template.md`
- `assets/UI_Review_Checklist_Template.md`
- `assets/UI_Revision_Brief_Template.md`

When available, use these as upstream inputs:

- `protocol-driven-build` stage artifacts
- product PRD or handoff docs
- existing screenshots or builder output
- current frontend code
- local or global `frontend-design` skill for visual uplift
- optional UX guardrail references available in the host workspace for accessibility, touch, responsive behavior, performance, and style lookup support

## Default Workflow

1. Confirm the UI gate is met.
2. Read the protocol inputs.
3. Load `Principles Framework v1` as the structural rule base.
4. Derive a minimal `UI Context Profile` from the confirmed protocol.
5. If Founder taste is still unclear, run `Founder Taste Mining`.
   First run `Base Taste Scan`, then run `Contextual Taste Scan` using the current product type and `UI Context Profile`.
6. Write the round outputs into a `Taste Signal Matrix`.
7. Compile `Taste Principle Mapping` before writing any builder-facing style language.
8. Extract the minimum screen list and main user-visible states.
9. Produce a `Screen_Contract_Pack`.
10. Produce a `Visual_Direction_Brief`.
11. Produce an `AI_UI_Build_Brief`.
12. Send that pack to the external AI builder or use it locally.
13. Review the generated UI with `UI_Review_Checklist`.
14. Produce a `UI_Revision_Brief` with only the highest-value corrections.
15. Repeat for at most `2-3` review loops before escalating a structural issue.

## External Resource Priority

Prefer this order:

1. protocol and product docs in the current workspace
2. current code and screenshots
3. previous AI-generated UI outputs
4. existing reference apps or system screenshots the user provides
5. local and global design skills
6. fresh greenfield invention only when the above are insufficient

Do not force Figma or a heavyweight design-system process if the real goal is quick AI-assisted shipping.

## Default Outputs

This skill should usually materialize:

- `Taste_Mining_Round` when taste is still unclear
- `UI_Context_Profile`
- `Taste_Signal_Matrix`
- `Taste_Principle_Mapping`
- `Screen_Contract_Pack`
- `Visual_Direction_Brief`
- `AI_UI_Build_Brief`
- `UI_Review_Checklist`
- `UI_Revision_Brief`

Optional outputs when needed:

- `Builder_Input_Prompt`
- `Builder_Diff_Notes`
- `UI_Drift_Report`

## Output Rules

All outputs should be:

- concise
- Chinese by default
- easy to paste into Lovable, Gemini, Claude, or GPT
- explicit about what the builder may decide
- explicit about what the builder must not invent

Never hand off only vague style words like:

- "modern"
- "高级感"
- "科技感"
- "好看一点"

Always define:

- which screens exist
- what each screen must do
- what state blocks must exist
- what can be visually flexible
- what cannot be structurally changed
- which taste signals were actually confirmed
- which principle modules those taste signals are allowed to modulate

## Fast Review Rule

The review loop should be short and opinionated.

Prefer:

- `3-7` high-signal corrections
- concrete screen-level comments
- direct "replace / remove / move / compress / emphasize" language

Avoid:

- massive redesign essays
- generic aesthetic criticism
- requesting a whole new build when a revision brief is enough

## Anti-Patterns

Avoid these failure modes:

- using UI exploration to hide unresolved product logic
- running generic taste tests that ignore the actual product type
- jumping from taste notes directly to builder prompts without a signal matrix
- treating style adjectives as if they were design rules
- generating dozens of screens before validating the core runtime
- over-building a design system for a still-moving product
- letting builders invent missing state behavior
- rewriting the whole UI every loop instead of issuing targeted revisions

## Success Standard

This skill succeeds when:

- the UI pack is clearly derived from the protocol
- an AI builder can generate a coherent first pass quickly
- the user can review and tighten the result in a small number of loops
- UI remains easy to replace without destabilizing product logic
