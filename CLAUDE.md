# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A personal thinking OS — 12 modular skills + 1 root loader, registered as `/cubxxw-skills` in Claude Code. Each skill is a standalone `SKILL.md` (pure Markdown, no code). The root `SKILL.md` is the entry point that loads `meta-soul` first, then routes to child skills based on conversation domain.

## Architecture

```
SKILL.md (root loader — routing table + loading protocol)
  └── meta-soul/SKILL.md (base persona — ALWAYS loaded first)
  └── framework-*/SKILL.md (7 independent frameworks)
  └── tension-*/SKILL.md (4 dialectical tension pairs)
manifest.json (skill registry, metadata, preset definitions)
```

**Loading order matters**: meta-soul establishes dual-core processing (Logic Core + Sensitivity Core) and the three-layer reality model. Without it, child skills lose their interpretive context.

**Routing**: Root SKILL.md contains a domain → skill mapping table and signal word list. Multiple skills can be active simultaneously.

## Skill Format Convention

Every SKILL.md follows this structure:
1. YAML frontmatter: `name`, `description`, `version`, `author`, `source`, `category` (meta/framework/tension), `tags`, `related_skills`, `lang: "zh-CN/en"`
2. Overview + core model
3. Discernment frameworks or key principles (5-7 items)
4. When to apply
5. **Cognitive Evolution** section (mandatory — shows how the thinking shifted over time, with dates)
6. Related skills cross-references
7. Version stamp

## Key Rules

- **Tensions are navigated, never resolved.** The four core tensions (freedom/order, authenticity/performance, rationality/sensitivity, control/generativity) are structural — helping the user see their position and the cost of each direction is the goal.
- **Bilingual convention**: English is the structural language. Chinese concepts stay in pinyin + characters when no accurate English equivalent exists (e.g., 感性核, 剥瓜子模式, 随心所欲而不逾矩).
- **Cognitive Evolution sections are versioned**, not final. Views change. Document shifts with dates.
- **Skills cross-reference but never require each other.** Each skill must work standalone.

## Naming Conventions

- Frameworks: `framework-{snake_case}/SKILL.md`
- Tensions: `tension-{snake_case}/SKILL.md`
- Meta: `meta-soul/SKILL.md`
- Directory name = skill category prefix + skill name from manifest

## Presets (defined in manifest.json)

`builder`, `philosopher`, `traveler`, `relationship`, `knowledge_engineer` — each maps to 3-4 skills for focused conversations.

## License

MIT-K — standard MIT + a "K-Clause" requiring attribution when using 3+ frameworks, the meta-soul persona in public products, or incorporating into training data.
