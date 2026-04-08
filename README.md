<div align="center">

# cubxxw-skills

**Personal Thinking Frameworks & Cognitive Tools**

[中文文档](README.zh.md) · [manifest.json](manifest.json)

[![License: MIT-K](https://img.shields.io/badge/License-MIT--K-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](manifest.json)
[![Skills](https://img.shields.io/badge/skills-12-orange.svg)](manifest.json)
[![Compatible](https://img.shields.io/badge/compatible-Claude%20Code%20%7C%20OpenClaw%20%7C%20Cursor-purple.svg)](#how-to-use)

</div>

A personal thinking OS distilled into modular, AI-loadable skills. Extracted from 13 months of structured self-observation (3580+ thinking chunks). Each skill is a standalone `SKILL.md` that teaches a specific method, framework, or mode of discernment.

## Quick Start

```bash
# Install
git clone https://github.com/cubxxw/cubxxw-skills ~/.cubxxw-skills

# Load a skill into Claude Code
cat ~/.cubxxw-skills/framework-lean_product/SKILL.md | pbcopy  # macOS
cat ~/.cubxxw-skills/framework-lean_product/SKILL.md | xclip   # Linux

# List all available skills
cat ~/.cubxxw-skills/manifest.json | jq '.skills[].name'

# Load a preset (builder, philosopher, traveler, relationship, knowledge_engineer)
cat ~/.cubxxw-skills/manifest.json | jq -r '.load_presets.builder.skills[]' \
  | xargs -I{} cat ~/.cubxxw-skills/*/SKILL.md 2>/dev/null
```

## How to Use

### Claude Code

Clone the repo and reference skills directly in conversation or config:

```bash
git clone https://github.com/cubxxw/cubxxw-skills ~/.claude/skills/cubxxw-skills
```

**Reference in a conversation:**
```
@~/.claude/skills/cubxxw-skills/framework-lean_product/SKILL.md
```

**Auto-load in `CLAUDE.md`** (applies to all sessions in a project):
```markdown
@~/.claude/skills/cubxxw-skills/framework-ai_native_workflow/SKILL.md
@~/.claude/skills/cubxxw-skills/meta-soul/SKILL.md
```

**Load a preset via shell:**
```bash
# Print all skills in the "builder" preset to stdout
manifest=~/.claude/skills/cubxxw-skills/manifest.json
jq -r '.load_presets.builder.skills[]' $manifest | while read skill; do
  path=$(jq -r --arg s "$skill" '.skills[] | select(.name==$s) | .path' $manifest)
  cat ~/.claude/skills/cubxxw-skills/$path
done
```

---

### OpenClaw

OpenClaw natively supports `SKILL.md` format. Add to your config:

```yaml
# ~/.openclaw/config.yaml
skills:
  - path: ~/.openclaw/skills/cubxxw-skills
    auto_load:
      - meta-soul
      - ai_native_workflow
```

**CLI commands:**
```bash
# Load a single skill
/skill load framework-lean_product

# Load a preset
/skill preset builder
/skill preset philosopher

# List loaded skills
/skill list
```

**Install via shell:**
```bash
mkdir -p ~/.openclaw/skills
git clone https://github.com/cubxxw/cubxxw-skills ~/.openclaw/skills/cubxxw-skills
```

---

### Cursor / Windsurf / Cline

**Option A — paste into context:**
```bash
# Copy a skill to clipboard (macOS)
cat framework-lean_product/SKILL.md | pbcopy

# Then paste into the AI chat window
```

**Option B — add to rules file:**
```bash
# Append a skill to .cursorrules
cat ~/.cubxxw-skills/framework-ai_native_workflow/SKILL.md >> .cursorrules

# Or create a combined rules file from a preset
manifest=~/.cubxxw-skills/manifest.json
jq -r '.load_presets.builder.skills[]' $manifest | while read skill; do
  path=$(jq -r --arg s "$skill" '.skills[] | select(.name==$s) | .path' $manifest)
  cat ~/.cubxxw-skills/$path
done > .cursorrules
```

---

### General AI Assistants (ChatGPT, Gemini, etc.)

Paste any `SKILL.md` content as a system prompt or conversation opener to activate that thinking framework. No special tooling needed.

```bash
# Print and copy any skill
cat ~/.cubxxw-skills/meta-soul/SKILL.md
```

---

### Programmatic / API

```bash
# Shell: load skill content into a variable
SKILL=$(cat ~/.cubxxw-skills/framework-lean_product/SKILL.md)

# Pass to any LLM CLI
echo "$SKILL" | llm -s "You are an expert with this framework:" -
```

```python
import json, pathlib

root = pathlib.Path.home() / ".cubxxw-skills"
manifest = json.loads((root / "manifest.json").read_text())

def load_preset(name: str) -> str:
    skills = manifest["load_presets"][name]["skills"]
    parts = []
    for skill_name in skills:
        skill = next(s for s in manifest["skills"] if s["name"] == skill_name)
        parts.append((root / skill["path"]).read_text())
    return "\n\n---\n\n".join(parts)

# Use as system prompt
system_prompt = load_preset("builder")
```

---

## Skill Catalog

### Meta
| Skill | Description |
|-------|-------------|
| [meta-soul](meta-soul/SKILL.md) | Full persona loader — systematic sensory realist thinking partner |

### Frameworks
| Skill | Description |
|-------|-------------|
| [self_modeling](framework-self_modeling/SKILL.md) | Identity as construction — designable, maintainable, versionable self |
| [lean_product](framework-lean_product/SKILL.md) | Indie dev methodology — MVP, scene verification, minimum action units |
| [ai_native_workflow](framework-ai_native_workflow/SKILL.md) | AI as infrastructure — agent loops, context management, MCP |
| [meaning_architecture](framework-meaning_architecture/SKILL.md) | Meaning through narrative, desire types, growth equations |
| [nomadic_cognition](framework-nomadic_cognition/SKILL.md) | Travel and space as cognitive tools |
| [comparative_culture](framework-comparative_culture/SKILL.md) | Civilizational analysis — infrastructure, cages, cultural dimensions |
| [cognitive_evolution](framework-cognitive_evolution/SKILL.md) | Meta-method for tracking how thinking changes |

### Tensions
| Skill | Description |
|-------|-------------|
| [authenticity_performance](tension-authenticity_performance/SKILL.md) | Truth vs. social performance — what drains vs. sustains |
| [freedom_order](tension-freedom_order/SKILL.md) | Freedom and structure as a design problem |
| [relationship_boundaries](tension-relationship_boundaries/SKILL.md) | Dynamic boundary negotiation in intimacy |
| [systematization_experience](tension-systematization_experience/SKILL.md) | When system-building becomes defense |

## Presets

| Preset | Skills |
|--------|--------|
| `builder` | lean_product, ai_native_workflow, systematization_experience |
| `philosopher` | meta-soul, self_modeling, meaning_architecture, authenticity_performance |
| `traveler` | nomadic_cognition, comparative_culture, freedom_order |
| `relationship` | relationship_boundaries, authenticity_performance, self_modeling |
| `knowledge_engineer` | cognitive_evolution, self_modeling, systematization_experience |

## Design Principles

- **Self-contained**: Each skill works independently — no external dependencies
- **Instructional**: Frameworks you can apply, not archives to read
- **Evolution-aware**: Each skill documents how the thinking shifted over time
- **Bilingual**: English structure, Chinese concepts preserved where no good translation exists
- **Interconnected**: Skills reference each other through `related_skills` but never require each other

## Contributing

Issues and PRs welcome. If you build something with these skills, share it.

## License

[MIT-K License](LICENSE) — Free to use, modify, and distribute with attribution.

---

<div align="center">
v1.0.0 · 2026-04-08 · <a href="https://github.com/cubxxw">cubxxw</a>
</div>
