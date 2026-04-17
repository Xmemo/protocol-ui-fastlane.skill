# protocol-ui-fastlane

Fast UI handoff for confirmed protocol specs.

把已确认的协议规范快速转成可交给 AI builder 的 UI 交付包。

## At a glance / 一句话看懂

- EN: Turn stable product logic into screen contracts, wireframes, visual direction, and revision briefs.
- 中文：把稳定的产品逻辑转成屏幕契约、线框、视觉方向和 revision brief。

## What this repo is / 这个仓库是什么

This is a standalone skill pack for downstream UI concretization and builder handoff.

这是一个独立可发布的 skill 包，用来做下游 UI 落地和 AI builder 交付。

## Best for / 适合什么场景

- EN: Protocols that are already stable
- 中文：协议已经稳定的场景
- EN: Lovable / Gemini / Claude / GPT UI handoff
- 中文：要交给 Lovable、Gemini、Claude、GPT 这类 builder 的场景
- EN: Fast review loops
- 中文：需要快速审稿和迭代的场景
- EN: Taste-driven UI alignment
- 中文：需要做审美对齐和 UI 风格收敛的场景

## What is included / 包含内容

- `SKILL.md`
- `agents/`
- `assets/`
- `references/`

## What it is not / 不是什么

- EN: Not a product discovery skill
- 中文：不是产品探索 skill
- EN: Not a replacement for protocol definition
- 中文：不是协议定义的替代品
- EN: Not a heavy design-system process
- 中文：不是重型设计系统流程

## How it works / 工作方式

1. Confirm the protocol gate.
2. Derive the minimum UI contract.
3. Produce a builder-ready handoff pack.
4. Review output and issue a bounded revision brief.

1. 先确认协议门槛。
2. 再提炼最小 UI 契约。
3. 输出可交付给 builder 的 handoff pack。
4. 审核结果并给出边界清晰的 revision brief。

## Install / 安装

Copy this repository into your Codex skills directory, or wire it into your own skill loader.

把这个仓库复制到你的 Codex skills 目录，或者接到你自己的 skill 加载机制里。

## Relationship / 与其他 skill 的关系

This skill is downstream of `protocol-driven-build`. It converts confirmed logic into UI execution artifacts.

这个 skill 是 `protocol-driven-build` 的下游。它把已确认的逻辑转成 UI 执行物。

## License / 许可证

MIT
