# Principles Framework v1

默认用中文维护。

当前状态：`v1 基线已确认`

这份文档的目标不是复述《Refactoring UI》，而是把其中可执行的部分整理成：

- AI 能理解
- Founder 能看懂
- 能和 Taste Mining 结果对接
- 能最终落到 AI builder handoff

## 结构分层

本框架固定分为三层：

1. `Principles Framework`
   设计准则层。定义哪些结构性规则必须成立。

2. `Builder Translation Layer`
   生成约束层。把设计准则翻译成 AI builder 可执行语言。

3. `Taste Mapping Layer`
   风格调制层。定义哪些原则模块允许被审美偏好调节，哪些不能被破坏。

不要把这三层混写。

## 字段定义

每条原则统一使用以下字段：

- `Principle ID`
- `Principle Name`
- `Module`
- `Constraint Level`
- `Taste Sensitivity`
- `Applies To`
- `One-sentence Rule`
- `Why it matters`
- `Observable signals`
- `Common anti-patterns`

## Constraint Level

用于区分规则强度。

- `hard`
  违反后通常会直接损坏可读性、层级、清晰度或生成稳定性。

- `default`
  默认应该遵守，但在特定产品或布局下可以有意识调整。

- `taste-dependent`
  结构正确性仍然重要，但具体实现会明显受到风格偏好影响。

## Taste Sensitivity

用于表示该原则受审美偏好影响的程度。

- `low`
  更偏结构和可读性，通常不该被风格破坏。

- `medium`
  结构为主，但存在一定风格弹性。

- `high`
  原则仍成立，但具体表达方式高度受风格影响。

## Applies To

建议使用以下标签，不必强制唯一：

- `all-screens`
- `content-screens`
- `data-screens`
- `runtime-screens`
- `cards`
- `forms`
- `empty-states`
- `mobile-first`
- `desktop-first`

## Module 定义

### 1. `Hierarchy`

管什么：

- 主次关系
- 视觉焦点
- CTA 优先级
- 文档结构与视觉结构的关系

### 2. `Spacing`

管什么：

- 留白节奏
- 分组关系
- 组件内外边距
- 布局伸缩策略

### 3. `Typography`

管什么：

- 字号系统
- 行高
- 行宽
- 字重
- 语气与阅读节奏

### 4. `Color`

管什么：

- 色阶体系
- 色彩温度
- 强调与弱化
- 彩色背景上的用色逻辑

### 5. `Surface / Depth`

管什么：

- 分层
- 阴影
- 容器感
- 表面区分
- 背景切换

### 6. `Contrast / Readability`

管什么：

- 文本可读性
- 对比度
- 彩色背景上的阅读清晰度
- 图片/复杂背景上的阅读保护

## Principles Registry

| Principle ID | Principle Name | Module | Constraint Level | Taste Sensitivity | Applies To |
|---|---|---|---|---|---|
| `SYS-001` | 限制选择选项 | `Spacing/Typography/Color` | `hard` | `low` | `all-screens` |
| `HIER-001` | 尺寸并非唯一手段 | `Hierarchy/Typography/Color` | `default` | `medium` | `all-screens` |
| `HIER-002` | 通过弱化来强调 | `Hierarchy` | `default` | `medium` | `all-screens` |
| `DATA-001` | 标签是最后的手段 | `Hierarchy/Typography` | `default` | `low` | `data-screens/forms` |
| `HIER-003` | 分离视觉与文档层级 | `Hierarchy/Typography` | `hard` | `low` | `all-screens` |
| `ACT-001` | 行动层级优先于语义 | `Hierarchy` | `default` | `medium` | `forms/runtime-screens` |
| `SPC-001` | 从过多的留白开始 | `Spacing` | `default` | `medium` | `all-screens` |
| `SPC-002` | 避免模糊的间距 | `Spacing` | `hard` | `low` | `all-screens` |
| `SZE-001` | 相对尺寸无法扩展 | `Spacing/Typography` | `default` | `low` | `mobile-first/runtime-screens` |
| `TYP-001` | 建立非线性字号比例尺 | `Typography` | `hard` | `low` | `all-screens` |
| `TYP-002` | 控制行宽与动态行高 | `Typography/Contrast / Readability` | `hard` | `low` | `content-screens` |
| `COL-001` | HSL 与系统调色板 | `Color` | `hard` | `medium` | `all-screens` |
| `COL-002` | 彩色背景对比度保护 | `Color/Contrast / Readability` | `hard` | `low` | `cards/runtime-screens` |
| `COL-003` | 明度与饱和度补偿 | `Color` | `default` | `medium` | `all-screens` |
| `DEP-001` | 双层阴影与真实光源 | `Surface / Depth` | `default` | `high` | `cards/runtime-screens` |
| `CMP-001` | 空状态优先设计 | `Hierarchy/Spacing` | `default` | `medium` | `empty-states` |
| `DEC-001` | 减少边框的使用 | `Surface / Depth/Spacing` | `default` | `high` | `all-screens` |
| `LAY-001` | 内容驱动最大宽度 | `Spacing/Contrast / Readability` | `hard` | `low` | `content-screens/forms/desktop-first` |

## Sample Structured Entries

下面只展示几条标准写法，作为框架示例。完整条目可后续逐步补齐。

### `SYS-001`

- `Principle ID`: `SYS-001`
- `Principle Name`: 限制选择选项
- `Module`: `Spacing/Typography/Color`
- `Constraint Level`: `hard`
- `Taste Sensitivity`: `low`
- `Applies To`: `all-screens`
- `One-sentence Rule`: 所有间距、尺寸、颜色和字号应来自受限变量池，而不是每次重新创造。
- `Why it matters`: 没有系统约束时，AI 会在每次生成中引入不稳定的新值，破坏一致性和可维护性。
- `Observable signals`: 使用固定 token；相邻数值间距明显；没有大量零散硬编码值。
- `Common anti-patterns`: 到处出现 `13px / 17px / 31px`；颜色全是临时 hex；不同页面 spacing 节奏不一致。

### `SPC-002`

- `Principle ID`: `SPC-002`
- `Principle Name`: 避免模糊的间距
- `Module`: `Spacing`
- `Constraint Level`: `hard`
- `Taste Sensitivity`: `low`
- `Applies To`: `all-screens`
- `One-sentence Rule`: 组件外部间距必须明显大于组件内部间距，否则分组关系会模糊。
- `Why it matters`: 模糊的间距会直接损坏信息分组和视觉理解，AI 很容易生成“所有块都差不多远”的布局。
- `Observable signals`: label 与 input 更近；组件与组件之间留白更大；分组不依赖额外边框也能成立。
- `Common anti-patterns`: 列表项内部和列表项之间间距一样；表单标签和下一组输入的距离同级。

### `COL-002`

- `Principle ID`: `COL-002`
- `Principle Name`: 彩色背景对比度保护
- `Module`: `Color/Contrast / Readability`
- `Constraint Level`: `hard`
- `Taste Sensitivity`: `low`
- `Applies To`: `cards/runtime-screens`
- `One-sentence Rule`: 在彩色背景上弱化文字时，不要用灰色或透明白，而要用同色相范围的专用文本色。
- `Why it matters`: 透明白和灰字在彩色背景上常常造成脏、灰、像 disabled 的阅读体验。
- `Observable signals`: 彩色块上的次级文字依然清晰；弱信息不是“发灰”，而是“同色系低刺激”。
- `Common anti-patterns`: 深蓝卡片上用 `rgba(255,255,255,0.6)`；彩色背景上直接套灰字。

### `DEC-001`

- `Principle ID`: `DEC-001`
- `Principle Name`: 减少边框的使用
- `Module`: `Surface / Depth/Spacing`
- `Constraint Level`: `default`
- `Taste Sensitivity`: `high`
- `Applies To`: `all-screens`
- `One-sentence Rule`: 分隔元素时优先使用留白、背景差异和轻阴影，边框是最后手段。
- `Why it matters`: 边框太容易让界面变脏、变碎、变 Excel 化。
- `Observable signals`: 容器关系主要靠空间和层次表达；边框极少且对比度很低。
- `Common anti-patterns`: 每个卡片、每个区块、每一行都上 1px 边框；界面像表格拼接。

## How It Connects To Taste Mining

Taste Mining 的结果不能直接替代原则框架。

正确关系是：

- `Principles Framework` 负责结构正确性
- `Taste Signal Matrix` 负责风格偏好信号
- `Compiled Style Profile` 负责把两者编译成项目级风格协议

例如：

- `warmth` 主要影响 `Color`、`Typography`、`Surface / Depth`
- `scientificness` 主要影响 `Hierarchy`、`Contrast / Readability`、`Density`
- `companionship` 主要影响 `Typography`、`Motion`、`Surface / Depth`

但无论 taste 如何变化，以下内容不应被破坏：

- 基础 hierarchy 清晰度
- spacing 分组清晰度
- type scale 受限系统
- 基本可读性和对比度

## Usage Rule

在 skill 中的建议顺序应为：

1. 先加载 `Principles Framework`
2. 再加载 `UI Context Profile`
3. 再运行 `Reference Pair Cards`
4. 把 Founder 选择写入 `Taste Signal Matrix`
5. 最后生成 `Compiled Style Profile`

不要直接从 taste 结果跳到 builder prompt。
