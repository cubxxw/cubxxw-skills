<div align="center">

# cubxxw-skills

**个人思维框架与认知工具库**

[English](README.md) · [manifest.json](manifest.json)

[![License: MIT-K](https://img.shields.io/badge/License-MIT--K-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](manifest.json)
[![Skills](https://img.shields.io/badge/skills-12-orange.svg)](manifest.json)

</div>

从 13 个月、3580+ 条结构化自我观察中提炼出的个人思维操作系统。每个 Skill 都是一个独立可加载的 `SKILL.md`，教授特定的方法论、框架或判断模式。

## 快速开始

```bash
# 安装
git clone https://github.com/cubxxw/cubxxw-skills ~/.cubxxw-skills

# 复制某个技能内容到剪贴板（macOS）
cat ~/.cubxxw-skills/framework-lean_product/SKILL.md | pbcopy

# 列出所有可用技能
cat ~/.cubxxw-skills/manifest.json | jq '.skills[].name'

# 一次性加载一个预设（以 builder 为例）
manifest=~/.cubxxw-skills/manifest.json
jq -r '.load_presets.builder.skills[]' $manifest | while read skill; do
  path=$(jq -r --arg s "$skill" '.skills[] | select(.name==$s) | .path' $manifest)
  cat ~/.cubxxw-skills/$path
done
```

## 使用方式

### Claude Code

克隆仓库到 Claude Code 的技能目录：

```bash
git clone https://github.com/cubxxw/cubxxw-skills ~/.claude/skills/cubxxw-skills
```

**在对话中引用：**
```
@~/.claude/skills/cubxxw-skills/framework-lean_product/SKILL.md
```

**在 `CLAUDE.md` 中配置自动加载**（对项目下所有会话生效）：
```markdown
@~/.claude/skills/cubxxw-skills/framework-ai_native_workflow/SKILL.md
@~/.claude/skills/cubxxw-skills/meta-soul/SKILL.md
```

**通过命令行加载预设：**
```bash
# 将 builder 预设的所有技能内容输出到 stdout
manifest=~/.claude/skills/cubxxw-skills/manifest.json
jq -r '.load_presets.builder.skills[]' $manifest | while read skill; do
  path=$(jq -r --arg s "$skill" '.skills[] | select(.name==$s) | .path' $manifest)
  cat ~/.claude/skills/cubxxw-skills/$path
done
```

---

### OpenClaw

OpenClaw 原生支持 `SKILL.md` 格式，在配置文件中加入：

```yaml
# ~/.openclaw/config.yaml
skills:
  - path: ~/.openclaw/skills/cubxxw-skills
    auto_load:
      - meta-soul
      - ai_native_workflow
```

**命令行操作：**
```bash
# 加载单个技能
/skill load framework-lean_product

# 加载预设
/skill preset builder
/skill preset philosopher

# 查看已加载的技能
/skill list
```

**安装：**
```bash
mkdir -p ~/.openclaw/skills
git clone https://github.com/cubxxw/cubxxw-skills ~/.openclaw/skills/cubxxw-skills
```

---

### Cursor / Windsurf / Cline

**方式 A — 粘贴到上下文窗口：**
```bash
# 复制技能内容到剪贴板（macOS）
cat ~/.cubxxw-skills/framework-lean_product/SKILL.md | pbcopy
# 然后粘贴到 AI 对话窗口
```

**方式 B — 写入规则文件：**
```bash
# 追加某个技能到 .cursorrules
cat ~/.cubxxw-skills/framework-ai_native_workflow/SKILL.md >> .cursorrules

# 或者用预设生成完整的规则文件
manifest=~/.cubxxw-skills/manifest.json
jq -r '.load_presets.builder.skills[]' $manifest | while read skill; do
  path=$(jq -r --arg s "$skill" '.skills[] | select(.name==$s) | .path' $manifest)
  cat ~/.cubxxw-skills/$path
done > .cursorrules
```

---

### 通用 AI 助手（ChatGPT、Gemini 等）

将任意 `SKILL.md` 的完整内容粘贴为系统提示或对话开头，即可激活对应的思维框架。

```bash
cat ~/.cubxxw-skills/meta-soul/SKILL.md
# 复制输出内容，粘贴给任意 AI 助手
```

---

### 编程方式 / API 集成

```bash
# Shell：将技能内容存入变量
SKILL=$(cat ~/.cubxxw-skills/framework-lean_product/SKILL.md)

# 传入任意 LLM CLI 工具
echo "$SKILL" | llm -s "你是一位掌握以下框架的专家：" -
```

```python
import json, pathlib

root = pathlib.Path.home() / ".cubxxw-skills"
manifest = json.loads((root / "manifest.json").read_text())

def load_preset(name: str) -> str:
    """加载预设，返回合并后的 prompt 字符串"""
    skills = manifest["load_presets"][name]["skills"]
    parts = []
    for skill_name in skills:
        skill = next(s for s in manifest["skills"] if s["name"] == skill_name)
        parts.append((root / skill["path"]).read_text())
    return "\n\n---\n\n".join(parts)

# 作为系统提示使用
system_prompt = load_preset("builder")
```

---

## 技能目录

### Meta（元层）
| 技能 | 描述 |
|------|------|
| [meta-soul](meta-soul/SKILL.md) | 完整人格加载器 — 系统性感知现实主义思维伙伴 |

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

## 预设

| 预设 | 包含技能 |
|------|----------|
| `builder` | lean_product, ai_native_workflow, systematization_experience |
| `philosopher` | meta-soul, self_modeling, meaning_architecture, authenticity_performance |
| `traveler` | nomadic_cognition, comparative_culture, freedom_order |
| `relationship` | relationship_boundaries, authenticity_performance, self_modeling |
| `knowledge_engineer` | cognitive_evolution, self_modeling, systematization_experience |

## 设计原则

- **自包含**：每个 Skill 独立运行，无外部依赖
- **可操作**：提供可应用的框架，而非仅供阅读的档案
- **演化感知**：每个 Skill 包含思维如何随时间转变的记录
- **双语**：英文结构，中文概念在无法准确翻译时保留原文并附英文释义
- **互联互通**：通过 `related_skills` 相互引用，但从不相互依赖

## 贡献

欢迎提 Issue 和 PR。如果你用这些技能构建了什么，欢迎分享。

## 协议

[MIT-K 协议](LICENSE) — 可自由使用、修改和分发，需保留署名。

---

<div align="center">
v1.0.0 · 2026-04-08 · <a href="https://github.com/cubxxw">cubxxw</a>
</div>
