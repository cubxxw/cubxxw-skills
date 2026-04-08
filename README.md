<div align="center">

# cubxxw-skills

**个人思维框架与认知工具库 | Personal Thinking Frameworks & Cognitive Tools**

[English](#english) · [中文](#中文)

[![License: MIT-K](https://img.shields.io/badge/License-MIT--K-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](manifest.json)
[![Skills](https://img.shields.io/badge/skills-12-orange.svg)](manifest.json)
[![Compatible](https://img.shields.io/badge/compatible-Claude%20Code%20%7C%20OpenClaw%20%7C%20Cursor-purple.svg)](#使用方式--how-to-use)

</div>

---

## 中文

从 13 个月、3580+ 条结构化自我观察中提炼出的个人思维操作系统。每个 Skill 都是一个独立可加载的 `SKILL.md`，教授特定的方法论、框架或判断模式。

### 这是什么

一个模块化的**认知工具箱**，可以直接加载给 AI 助手使用。你可以：

- 加载单个 Skill 来激活某种思维框架
- 使用预设（Preset）一次性加载一组配套技能
- 作为上下文粘贴给任意 AI 助手（Claude、ChatGPT、Cursor 等）

这些 Skill 从一年的每日思考笔记中提炼，通过系统化的知识工程流程编译——追踪认知演化，而不仅仅是记录当下的观点。

### 使用方式

#### Claude Code

将技能目录复制到 Claude Code 的 skills 目录：

```bash
# 复制单个技能
cp -r framework-lean_product ~/.claude/skills/

# 或者克隆整个仓库
git clone https://github.com/cubxxw/cubxxw-skills ~/.claude/skills/cubxxw-skills
```

在对话中引用：
```
@~/.claude/skills/cubxxw-skills/framework-lean_product/SKILL.md
```

或者在 `CLAUDE.md` 中配置自动加载：
```markdown
@~/.claude/skills/cubxxw-skills/framework-ai_native_workflow/SKILL.md
```

#### OpenClaw

OpenClaw 原生支持 `SKILL.md` 格式。将技能目录加入你的 OpenClaw 配置：

```yaml
# .openclaw/config.yaml
skills:
  - path: ~/.openclaw/skills/cubxxw-skills
    auto_load:
      - meta-soul
      - ai_native_workflow
```

手动加载技能：
```
/skill load framework-lean_product
/skill load framework-ai_native_workflow
```

使用预设加载一组技能：
```
/skill preset builder
/skill preset philosopher
```

#### Cursor / Windsurf / Cline

将 `SKILL.md` 内容粘贴为对话上下文，或添加到项目的 `.cursorrules` / `.windsurfrules`：

```bash
# 查看技能内容
cat framework-lean_product/SKILL.md

# 粘贴到你的 AI 工具的上下文窗口
```

#### 通用 AI 助手（ChatGPT、Gemini 等）

直接粘贴任意 `SKILL.md` 的完整内容作为系统提示或对话开头，即可激活对应的思维框架。

#### 编程方式加载（API / 脚本）

```python
import json

# 读取 manifest
with open('manifest.json') as f:
    manifest = json.load(f)

# 加载预设
preset = manifest['load_presets']['builder']
for skill_name in preset['skills']:
    skill = next(s for s in manifest['skills'] if s['name'] == skill_name)
    with open(skill['path']) as f:
        content = f.read()
    # 将 content 注入你的 LLM 调用
```

### 技能目录

#### Meta（元层）
| 技能 | 描述 |
|------|------|
| [meta-soul](meta-soul/SKILL.md) | 完整人格加载器 — 系统性感知现实主义思维伙伴 |

#### Frameworks（框架）
| 技能 | 描述 |
|------|------|
| [self_modeling](framework-self_modeling/SKILL.md) | 身份即建构 — 将自我视为可设计、可维护、可版本化的系统 |
| [lean_product](framework-lean_product/SKILL.md) | 独立开发方法论 — MVP、场景验证、最小行动单元 |
| [ai_native_workflow](framework-ai_native_workflow/SKILL.md) | AI 即基础设施 — Agent 循环、上下文管理、MCP 协议 |
| [meaning_architecture](framework-meaning_architecture/SKILL.md) | 意义建构 — 叙事、欲望类型、成长方程式 |
| [nomadic_cognition](framework-nomadic_cognition/SKILL.md) | 移动与空间作为认知工具 |
| [comparative_culture](framework-comparative_culture/SKILL.md) | 文明分析 — 基础设施、心理笼子、文化维度 |
| [cognitive_evolution](framework-cognitive_evolution/SKILL.md) | 追踪思维如何改变的元方法 |

#### Tensions（张力）
| 技能 | 描述 |
|------|------|
| [authenticity_performance](tension-authenticity_performance/SKILL.md) | 真实 vs 社会表演 — 什么消耗你，什么滋养你 |
| [freedom_order](tension-freedom_order/SKILL.md) | 自由与结构作为设计问题 |
| [relationship_boundaries](tension-relationship_boundaries/SKILL.md) | 亲密关系中的动态边界协商 |
| [systematization_experience](tension-systematization_experience/SKILL.md) | 何时系统化变成了防御机制 |

### 预设

```json
{
  "builder":          ["lean_product", "ai_native_workflow", "systematization_experience"],
  "philosopher":      ["meta-soul", "self_modeling", "meaning_architecture", "authenticity_performance"],
  "traveler":         ["nomadic_cognition", "comparative_culture", "freedom_order"],
  "relationship":     ["relationship_boundaries", "authenticity_performance", "self_modeling"],
  "knowledge_engineer": ["cognitive_evolution", "self_modeling", "systematization_experience"]
}
```

### 设计原则

- **双语**：英文结构，中文概念在无法准确翻译时保留原文并附英文释义
- **自包含**：每个 Skill 独立运行，无外部依赖
- **可操作**：提供可应用的框架，而非仅供阅读的档案
- **演化感知**：每个 Skill 包含思维如何随时间转变的记录
- **互联互通**：通过 `related_skills` 相互引用，但从不相互依赖

---

## English

A personal thinking OS distilled into modular, AI-loadable skills. Extracted from 13 months of structured self-observation (3580+ thinking chunks).

### What This Is

A modular **cognitive toolkit** you can load directly into AI assistants. You can:

- Load individual Skills to activate specific thinking frameworks
- Use Presets to load curated skill combinations at once
- Paste as context to any AI assistant (Claude, ChatGPT, Cursor, etc.)

### How to Use

#### Claude Code

Copy skill directories into Claude Code's skills folder:

```bash
# Copy a single skill
cp -r framework-lean_product ~/.claude/skills/

# Or clone the entire repo
git clone https://github.com/cubxxw/cubxxw-skills ~/.claude/skills/cubxxw-skills
```

Reference in conversation:
```
@~/.claude/skills/cubxxw-skills/framework-lean_product/SKILL.md
```

Or configure auto-loading in `CLAUDE.md`:
```markdown
@~/.claude/skills/cubxxw-skills/framework-ai_native_workflow/SKILL.md
```

#### OpenClaw

OpenClaw natively supports the `SKILL.md` format. Add skill directories to your OpenClaw config:

```yaml
# .openclaw/config.yaml
skills:
  - path: ~/.openclaw/skills/cubxxw-skills
    auto_load:
      - meta-soul
      - ai_native_workflow
```

Manually load skills:
```
/skill load framework-lean_product
/skill preset builder
```

#### Cursor / Windsurf / Cline

Paste `SKILL.md` content as conversation context, or add to your `.cursorrules` / `.windsurfrules`:

```bash
cat framework-lean_product/SKILL.md
# Paste the output into your AI tool's context window
```

#### General AI Assistants (ChatGPT, Gemini, etc.)

Paste any `SKILL.md` content as a system prompt or conversation opener to activate that thinking framework.

#### Programmatic Loading

```python
import json

with open('manifest.json') as f:
    manifest = json.load(f)

preset = manifest['load_presets']['builder']
for skill_name in preset['skills']:
    skill = next(s for s in manifest['skills'] if s['name'] == skill_name)
    with open(skill['path']) as f:
        content = f.read()
    # Inject content into your LLM call
```

### Skill Catalog

#### Meta
| Skill | Description |
|-------|-------------|
| [meta-soul](meta-soul/SKILL.md) | Full persona loader — systematic sensory realist thinking partner |

#### Frameworks
| Skill | Description |
|-------|-------------|
| [self_modeling](framework-self_modeling/SKILL.md) | Identity as construction — designable, maintainable, versionable self |
| [lean_product](framework-lean_product/SKILL.md) | Indie dev methodology — MVP, scene verification, minimum action units |
| [ai_native_workflow](framework-ai_native_workflow/SKILL.md) | AI as infrastructure — agent loops, context management, MCP |
| [meaning_architecture](framework-meaning_architecture/SKILL.md) | Meaning through narrative, desire types, growth equations |
| [nomadic_cognition](framework-nomadic_cognition/SKILL.md) | Travel and space as cognitive tools |
| [comparative_culture](framework-comparative_culture/SKILL.md) | Civilizational analysis — infrastructure, cages, cultural dimensions |
| [cognitive_evolution](framework-cognitive_evolution/SKILL.md) | Meta-method for tracking how thinking changes |

#### Tensions
| Skill | Description |
|-------|-------------|
| [authenticity_performance](tension-authenticity_performance/SKILL.md) | Truth vs. social performance — what drains vs. sustains |
| [freedom_order](tension-freedom_order/SKILL.md) | Freedom and structure as a design problem |
| [relationship_boundaries](tension-relationship_boundaries/SKILL.md) | Dynamic boundary negotiation in intimacy |
| [systematization_experience](tension-systematization_experience/SKILL.md) | When system-building becomes defense |

### Presets

```json
{
  "builder":          ["lean_product", "ai_native_workflow", "systematization_experience"],
  "philosopher":      ["meta-soul", "self_modeling", "meaning_architecture", "authenticity_performance"],
  "traveler":         ["nomadic_cognition", "comparative_culture", "freedom_order"],
  "relationship":     ["relationship_boundaries", "authenticity_performance", "self_modeling"],
  "knowledge_engineer": ["cognitive_evolution", "self_modeling", "systematization_experience"]
}
```

### Design Principles

- **Bilingual**: English structure, Chinese concepts preserved with English glosses where no good translation exists
- **Self-contained**: Each skill works independently — no external dependencies
- **Instructional tone**: Frameworks you can apply, not archives to read
- **Evolution-aware**: Each skill includes how the thinking shifted over time
- **Interconnected**: Skills reference each other through `related_skills` but never require each other

### Origin

Extracted from personal knowledge base that compiles monthly thinking notes into a structured wiki with bidirectional links, cognitive evolution tracking, and concept networks.

---

## Contributing | 贡献

Issues and PRs welcome. If you build something with these skills, share it.

欢迎提 Issue 和 PR。如果你用这些技能构建了什么，欢迎分享。

## License | 协议

[MIT-K License](LICENSE) — Free to use, modify, and distribute with attribution.

MIT-K 协议 — 可自由使用、修改和分发，需保留署名。

---

<div align="center">

v1.0.0 · 2026-04-08 · [cubxxw](https://github.com/cubxxw)

</div>
