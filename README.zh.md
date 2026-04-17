# protocol-ui-fastlane

把已确认的协议规范快速转成可交给 AI builder 的 UI 交付包。

## 一句话看懂

把稳定的产品逻辑转成屏幕契约、线框、视觉方向和 revision brief。

## 这个仓库是什么

这是一个独立可发布的 skill 包，用来做下游 UI 落地和 AI builder 交付。

## 适合什么场景

- 协议已经稳定的场景
- 要交给 Lovable、Gemini、Claude、GPT 这类 builder 的场景
- 需要快速审稿和迭代的场景
- 需要做审美对齐和 UI 风格收敛的场景

## 包含内容

- `SKILL.md`
- `agents/`
- `assets/`
- `references/`

## 不是什么

- 不是产品探索 skill
- 不是协议定义的替代品
- 不是重型设计系统流程

## 工作方式

1. 先确认协议门槛。
2. 再提炼最小 UI 契约。
3. 输出可交付给 builder 的 handoff pack。
4. 审核结果并给出边界清晰的 revision brief。

## 安装

把这个仓库复制到你的 Codex skills 目录，或者接到你自己的 skill 加载机制里。

## 与其他 skill 的关系

这个 skill 是 `protocol-driven-build` 的下游。它把已确认的逻辑转成 UI 执行物。

## 许可证

MIT

- English version: [README.en.md](./README.en.md)

