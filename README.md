# protocol-ui-fastlane

## 中文

### 协议确认后，快速把逻辑翻成 UI 交付包

这个技能不是做“好看的 UI 灵感板”，而是把已经确认的产品逻辑翻成可交给 AI builder 的屏幕契约、线框、视觉方向和 revision brief。

### 这个技能的强点

- 它是下游翻译层，不抢协议定义的工作
- 它把“产品逻辑”翻成“屏幕可执行物”
- 它支持 taste mining，先把审美信号收敛，再生成 UI
- 它让 Lovable / Gemini / Claude / GPT 这类 builder 产出更少跑偏

### 它解决什么

- 产品逻辑已经定了，但 UI 生成还是很散
- 设计和实现之间缺少一层可执行翻译
- Builder 常常生成“看起来像 UI、但并不能落地”的结果
- 团队需要快审、快改、快收敛，而不是重做一套设计系统

### 适合谁

- 已经有稳定协议的产品团队
- 想用 AI builder 快速出 UI 的团队
- 需要审稿和修订 brief 的设计/产品/工程协作场景
- 想把审美和交付流程标准化的 Founder

### 你会得到什么

- 最小但完整的 UI contract
- builder-ready handoff pack
- 视觉方向 brief
- UI review checklist
- 边界清晰的 revision brief

### 包含内容

- `SKILL.md`
- `agents/`
- `assets/`
- `references/`

### 工作方式

1. 先确认协议门槛。
2. 提炼最小 UI 契约。
3. 输出可交付给 builder 的 handoff pack。
4. 审核结果并给出边界清晰的 revision brief。

### 安装

把这个仓库复制到你的 Codex skills 目录，或者接到你自己的 skill 加载机制里。

### 与其他 skill 的关系

它是 `protocol-driven-build` 的下游，把已确认的逻辑转成 UI 执行物。

### 许可证

MIT

## English

### Fast UI translation after protocol is confirmed

This skill is not a moodboard generator. It turns confirmed product logic into screen contracts, wireframes, visual direction, and revision briefs that AI builders can actually use.

### Why this skill is strong

- It stays downstream. It does not steal the job of protocol definition.
- It translates product logic into buildable screen-level artifacts.
- It supports taste mining so the UI direction is coherent before generation starts.
- It reduces drift when using Lovable, Gemini, Claude, or GPT for UI generation.

### What it solves

- Product logic is settled, but UI output still feels scattered.
- There is no executable translation layer between product and design.
- Builders often generate something that looks like UI but is not ready to ship.
- Teams need fast review, tight revision briefs, and convergence, not a redesign of the whole design system.

### Best for

- Teams with stable protocol definitions
- Teams using AI builders to generate UI quickly
- Product / design / engineering collaboration around review and revision
- Founders who want the delivery process to be opinionated and repeatable

### What you get

- A minimal but complete UI contract
- A builder-ready handoff pack
- A visual direction brief
- A UI review checklist
- A bounded revision brief

### Included contents

- `SKILL.md`
- `agents/`
- `assets/`
- `references/`

### How it works

1. Confirm the protocol gate.
2. Derive the minimum UI contract.
3. Produce a builder-ready handoff pack.
4. Review output and issue a bounded revision brief.

### Install

Copy this repository into your Codex skills directory, or wire it into your own skill loader.

### Relationship

This skill is downstream of `protocol-driven-build`. It converts confirmed logic into UI execution artifacts.

### License

MIT
