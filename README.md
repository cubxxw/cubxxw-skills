<div align="center">

# cubxxw-skills

**Personal Thinking Frameworks & Cognitive Tools**

[中文文档](README.zh.md) · [manifest.json](manifest.json)

[![License: MIT-K](https://img.shields.io/badge/License-MIT--K-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](manifest.json)
[![Skills](https://img.shields.io/badge/skills-12-orange.svg)](manifest.json)
[![Compatible](https://img.shields.io/badge/compatible-Claude%20Code-purple.svg)](#usage)

</div>

A personal thinking OS distilled into modular, AI-loadable skills. Extracted from 13 months of structured self-observation (3580+ thinking chunks). Each skill is a standalone `SKILL.md` that teaches a specific method, framework, or mode of discernment.

---

## Install

```bash
git clone https://github.com/cubxxw/cubxxw-skills ~/.claude/skills/cubxxw-skills
```

Then restart Claude Code. The skill registers automatically as `/cubxxw-skills`.

---

## Usage

Type `/cubxxw-skills` in any Claude Code conversation to activate the full thinking OS — it loads the base persona and routes to child skills based on what you're working on.

```
/cubxxw-skills
```

That's it. No flags, no arguments needed. Claude will adopt the thinking partner persona and load the relevant frameworks as the conversation develops.

---

## Typical Use Cases

These are the conversations where `/cubxxw-skills` changes the quality of the output most noticeably:

### 1. Product Validation — "Should I build this?"

```
/cubxxw-skills

I have an idea for a tool that helps indie devs manage context windows across long Claude sessions.
Should I build it? Who would actually pay for it?
```

Activates: `lean_product` + `ai_native_workflow`. Runs scene verification, finds the minimum action unit to test demand before building anything.

---

### 2. Identity & Career — "What do I actually want?"

```
/cubxxw-skills

I've been in backend infra for 6 years. AI is eating my stack. I don't know if I should pivot to
product, go deeper into AI systems, or try something completely different. I feel stuck.
```

Activates: `self_modeling` + `meaning_architecture`. Separates stimulative desires (novelty-seeking) from generative ones (what actually compounds for you). Doesn't give you an answer — maps the terrain so you can choose.

---

### 3. Relationship Friction — "Why does this keep happening?"

```
/cubxxw-skills

Every time I try to set a boundary with my partner, it turns into a fight about something else
entirely. We never resolve the original thing. What's actually going on?
```

Activates: `relationship_boundaries` + `authenticity_performance`. Looks at the pattern underneath the pattern — what social performance is being defended, what real need isn't being said.

---

### 4. Travel & Work Design — "Where should I base myself?"

```
/cubxxw-skills

I'm considering spending 3 months in Japan vs staying in Shenzhen. I work remotely, care about
walkability, density, and having time to think. How do I decide?
```

Activates: `nomadic_cognition` + `comparative_culture`. Environment-thinking mapping — how each city's infrastructure shapes cognitive state, not just lifestyle preferences.

---

### 5. Knowledge System — "My notes are a graveyard"

```
/cubxxw-skills

I have 4 years of Obsidian notes. I can't find anything useful when I need it. I write things down
and never return to them. Is the problem my system or my habits?
```

Activates: `cognitive_evolution` + `systematization_experience`. Diagnoses whether you're building a knowledge system or a defense mechanism. Proposes minimum viable retrieval instead of another reorganization.

---

### 6. Load a Specific Framework Directly

If you know exactly which lens you need, just say so after invoking:

```
/cubxxw-skills

Load freedom_order. I'm trying to figure out how much structure to add to my mornings without
killing spontaneity.
```

Available skills: `meta-soul`, `self_modeling`, `lean_product`, `ai_native_workflow`, `meaning_architecture`, `nomadic_cognition`, `comparative_culture`, `cognitive_evolution`, `authenticity_performance`, `freedom_order`, `relationship_boundaries`, `systematization_experience`

---

## Presets

For focused conversations, you can ask to load a preset cluster:

| Preset | Skills | Best for |
|--------|--------|----------|
| `builder` | lean_product · ai_native_workflow · systematization_experience | Shipping products, avoiding over-engineering |
| `philosopher` | meta-soul · self_modeling · meaning_architecture · authenticity_performance | Identity work, meaning-making, existential questions |
| `traveler` | nomadic_cognition · comparative_culture · freedom_order | Relocation, remote work design, cultural analysis |
| `relationship` | relationship_boundaries · authenticity_performance · self_modeling | Intimacy, social dynamics, boundary negotiation |
| `knowledge_engineer` | cognitive_evolution · self_modeling · systematization_experience | Personal knowledge systems, paradigm tracking |

```
/cubxxw-skills

Load the philosopher preset. I want to think through why I keep abandoning projects right before
they're done.
```

---

## Skill Catalog

### Meta
| Skill | Description |
|-------|-------------|
| [meta-soul](meta-soul/SKILL.md) | Base persona — dual logic/sensitivity cores, three-layer reality model |

### Frameworks
| Skill | Description |
|-------|-------------|
| [self_modeling](framework-self_modeling/SKILL.md) | Identity as construction — designable, maintainable, versionable self |
| [lean_product](framework-lean_product/SKILL.md) | Indie dev methodology — MVP, scene verification, minimum action units |
| [ai_native_workflow](framework-ai_native_workflow/SKILL.md) | AI as infrastructure — agent loops, context management, MCP |
| [meaning_architecture](framework-meaning_architecture/SKILL.md) | Meaning through narrative, desire types, growth equations |
| [nomadic_cognition](framework-nomadic_cognition/SKILL.md) | Travel and space as cognitive tools |
| [comparative_culture](framework-comparative_culture/SKILL.md) | Civilizational analysis — infrastructure, psychological cages, cultural dimensions |
| [cognitive_evolution](framework-cognitive_evolution/SKILL.md) | Meta-method for tracking how thinking changes |

### Tensions
| Skill | Description |
|-------|-------------|
| [authenticity_performance](tension-authenticity_performance/SKILL.md) | Truth vs. social performance — what drains vs. sustains |
| [freedom_order](tension-freedom_order/SKILL.md) | Freedom and structure as a design problem |
| [relationship_boundaries](tension-relationship_boundaries/SKILL.md) | Dynamic boundary negotiation in intimacy |
| [systematization_experience](tension-systematization_experience/SKILL.md) | When system-building becomes defense |

---

## Design Principles

- **Self-contained**: Each skill works independently — no external dependencies
- **Instructional**: Frameworks you can apply, not archives to read
- **Evolution-aware**: Each skill documents how the thinking shifted over time
- **Bilingual**: English structure, Chinese concepts preserved where no good translation exists
- **Interconnected**: Skills reference each other but never require each other

## License

[MIT-K License](LICENSE) — Free to use, modify, and distribute with attribution.

---

<div align="center">
v1.0.0 · 2026-04-08 · <a href="https://github.com/cubxxw">cubxxw</a>
</div>
