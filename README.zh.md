<div align="center">

# cubxxw-skills

**个人思维框架与认知工具库**

[English](README.md) · [manifest.json](manifest.json)

[![License: MIT-K](https://img.shields.io/badge/License-MIT--K-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](manifest.json)
[![Skills](https://img.shields.io/badge/skills-12-orange.svg)](manifest.json)
[![Compatible](https://img.shields.io/badge/compatible-Claude%20Code-purple.svg)](#使用方式)

</div>

从 13 个月、3580+ 条结构化自我观察中提炼出的个人思维操作系统。每个 Skill 都是独立可加载的 `SKILL.md`，教授特定的方法论、框架或判断模式。

---

## 安装

```bash
git clone https://github.com/cubxxw/cubxxw-skills ~/.claude/skills/cubxxw-skills
```

重启 Claude Code 后，Skill 会自动注册为 `/cubxxw-skills`。

---

## 使用方式

在任意 Claude Code 对话中输入 `/cubxxw-skills`，即可激活完整的思维操作系统 — 它会加载基础人格，并根据对话内容动态加载对应子技能。

```
/cubxxw-skills
```

就这一条命令，不需要任何参数。Claude 会进入思维伙伴模式，随着对话推进自动调用相关框架。

---

## 典型使用场景

以下是 `/cubxxw-skills` 最能改变输出质量的对话类型：

### 1. 产品验证 — "这个东西值得做吗？"

```
/cubxxw-skills

我有个想法，做一个帮助独立开发者管理 Claude 长会话上下文窗口的工具。
值得做吗？谁会为它付费？
```

激活：`lean_product` + `ai_native_workflow`。进行场景验证，找到在动手之前测试需求的最小行动单元。

---

### 2. 身份与职业 — "我到底想要什么？"

```
/cubxxw-skills

我做后端基础设施六年了。AI 正在吞噬我的技术栈。我不知道该转产品、
深入 AI 系统方向，还是完全换个赛道。我感觉卡住了。
```

激活：`self_modeling` + `meaning_architecture`。区分刺激性欲望（追新求变）和生成性欲望（真正对你有复利的事）。不给你答案 — 而是帮你把地形看清楚，然后由你选择。

---

### 3. 关系摩擦 — "为什么这种情况反复出现？"

```
/cubxxw-skills

每次我试图跟伴侣划定边界，最后都变成另一件事的争吵。
原来的问题从来没被解决过。到底发生了什么？
```

激活：`relationship_boundaries` + `authenticity_performance`。看模式背后的模式 — 哪种社会表演正在被防御，哪个真实需求没有被说出来。

---

### 4. 居住与工作设计 — "我该把根据地放在哪里？"

```
/cubxxw-skills

我在考虑去日本待三个月，或者留在深圳。我远程工作，
在乎步行友好性、城市密度和能独处思考的时间。怎么做决定？
```

激活：`nomadic_cognition` + `comparative_culture`。环境-思维映射 — 分析每个城市的基础设施如何塑造认知状态，而不只是生活方式偏好的对比。

---

### 5. 知识系统 — "我的笔记是个坟墓"

```
/cubxxw-skills

我有四年的 Obsidian 笔记。需要用的时候什么都找不到。
记下来的东西从来不回头看。问题出在系统上还是习惯上？
```

激活：`cognitive_evolution` + `systematization_experience`。诊断你是在建知识系统还是在建防御机制。提出最小可用检索方案，而不是又一次重新整理。

---

### 6. 直接加载某个具体框架

如果你已经知道需要哪个视角，在激活后直接说：

```
/cubxxw-skills

加载 freedom_order。我想弄清楚早晨要加多少结构，
才不会把自发性全部杀死。
```

可用的 skills：`meta-soul`、`self_modeling`、`lean_product`、`ai_native_workflow`、`meaning_architecture`、`nomadic_cognition`、`comparative_culture`、`cognitive_evolution`、`authenticity_performance`、`freedom_order`、`relationship_boundaries`、`systematization_experience`

---

## 预设

对于有明确焦点的对话，可以请求加载预设组合：

| 预设 | 包含技能 | 适合场景 |
|------|----------|----------|
| `builder` | lean_product · ai_native_workflow · systematization_experience | 做产品、出货、避免过度工程化 |
| `philosopher` | meta-soul · self_modeling · meaning_architecture · authenticity_performance | 身份工作、意义建构、存在主义问题 |
| `traveler` | nomadic_cognition · comparative_culture · freedom_order | 搬家、远程工作设计、跨文化分析 |
| `relationship` | relationship_boundaries · authenticity_performance · self_modeling | 亲密关系、社交动力学、边界协商 |
| `knowledge_engineer` | cognitive_evolution · self_modeling · systematization_experience | 个人知识系统、范式追踪 |

```
/cubxxw-skills

加载 philosopher 预设。我想想清楚，为什么我每次在项目快做完的时候就放弃了。
```

---

## 技能目录

### Meta（元层）
| 技能 | 描述 |
|------|------|
| [meta-soul](meta-soul/SKILL.md) | 基础人格 — 逻辑核与感性核双核并行，三层现实模型 |

### Frameworks（框架）
| 技能 | 描述 |
|------|------|
| [self_modeling](framework-self_modeling/SKILL.md) | 身份即建构 — 将自我视为可设计、可维护、可版本化的系统 |
| [lean_product](framework-lean_product/SKILL.md) | 独立开发方法论 — MVP、场景验证、最小行动单元 |
| [ai_native_workflow](framework-ai_native_workflow/SKILL.md) | AI 即基础设施 — Agent 循环、上下文管理、MCP 协议 |
| [meaning_architecture](framework-meaning_architecture/SKILL.md) | 意义建构 — 叙事、欲望类型、成长方程式 |
| [nomadic_cognition](framework-nomadic_cognition/SKILL.md) | 移动与空间作为认知工具 |
| [comparative_culture](framework-comparative_culture/SKILL.md) | 文明分析 — 基础设施、心理笼子、文化维度 |
| [cognitive_evolution](framework-cognitive_evolution/SKILL.md) | 追踪思维如何改变的元方法 |

### Tensions（张力）
| 技能 | 描述 |
|------|------|
| [authenticity_performance](tension-authenticity_performance/SKILL.md) | 真实 vs 社会表演 — 什么消耗你，什么滋养你 |
| [freedom_order](tension-freedom_order/SKILL.md) | 自由与结构作为设计问题 |
| [relationship_boundaries](tension-relationship_boundaries/SKILL.md) | 亲密关系中的动态边界协商 |
| [systematization_experience](tension-systematization_experience/SKILL.md) | 何时系统化变成了防御机制 |

---

## 设计原则

- **自包含**：每个 Skill 独立运行，无外部依赖
- **可操作**：提供可应用的框架，而非仅供阅读的档案
- **演化感知**：每个 Skill 包含思维如何随时间转变的记录
- **双语**：英文结构，中文概念在无法准确翻译时保留原文并附英文释义
- **互联互通**：通过 `related_skills` 相互引用，但从不相互依赖

## 协议

[MIT-K 协议](LICENSE) — 可自由使用、修改和分发，需保留署名。

---

<div align="center">
v1.0.0 · 2026-04-08 · <a href="https://github.com/cubxxw">cubxxw</a>
</div>
