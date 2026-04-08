---
name: ai_native_workflow
description: "Design AI as infrastructure, not just tools — agent loops, context management, MCP protocol, and the shift from chat to runtime"
version: 1.0.0
author: "cubxxw"
source: "https://github.com/cubxxw/my-soul-skills"
category: framework
tags: [AI, agent, workflow, context, MCP, infrastructure, OpenClaw]
related_skills: [lean_product, self_modeling, systematization_experience]
lang: "zh-CN/en"
---

# AI-Native Workflow Design

## Overview

Elevating AI from chat tool to workflow infrastructure. The core challenge is not "how to use AI" but "how to let AI naturally integrate into daily life." The focus areas: context management, agent architecture, memory systems, tool calling, and system design.

## Core Model

### Agent Loop Pattern
```
Input → Context → Model → Tools → Repeat → Reply
```
This is the same pattern used by Claude Code, OpenClaw, and every serious agent framework. The loop is universal — the differentiation is in context quality.

### The Context Problem
- **Core issue**: "Context doesn't naturally enter" — the model doesn't know your world line (世界线)
- Users currently compress intent + background + constraints + format into prompts like API calls
- Context capture is energy-expensive and unsustainable as long-term agent form
- Solution direction: automated context capture, not manual prompt engineering

### OpenClaw Architecture Pattern
A local-first AI gateway system:
- **Gateway**: Single control plane (WebSocket), handling sessions, routing, tool calls, UI control
- **Agents**: The LLM "thinkers" (Claude/OpenAI/etc.)
- **Multi-channel input**: Multiple information entry points
- **Multi-agent routing**: Different agents for different task types
- **Local-first**: All data stored as Markdown files locally

### MCP (Model Context Protocol)
A pluggable protocol standardizing how applications provide context and tools to LLMs:
- Like a plugin system for AI platforms
- Configurable through GUI or CLI
- Supports multiple transport methods
- Enables fine-grained context control

### Obsidian as External Brain
- Bidirectional links for knowledge graphs
- Absolute data control with minimal core
- Highly customizable plugin ecosystem
- Open standard (Markdown) for LLM-native interaction

## When to Apply

- Designing AI-powered products or workflows
- Building agent systems or AI infrastructure
- Choosing between chat-based vs. workflow-integrated AI
- Evaluating context management strategies
- Deciding on local-first vs. cloud-first architectures

## Key Principles

1. **AI as environment, not tool**: The shift from "calling AI" to "AI naturally being part of daily life"
2. **Context is the bottleneck**: Context management, memory systems, and tool chains are the core challenge
3. **Agent runtime > API wrapper**: The real form is deep native integration of model and system
4. **Skill Graph > single file**: Complex abilities need networked knowledge domains, not monolithic configs
5. **PRPM vision**: Package management for prompts/skills (like npm for AI workflows)
6. **Multi-modal is the end state**: Current text-heavy agents are transitional — screen perception and multi-modal interaction is the final form

## Cognitive Evolution

- **2025-03**: Focus on Agent OS, context protocols, AI tool capabilities — AI as external service to "call"
- **2025-08**: Transition to workflow, memory, second brain, local-first systems
- **2026-03**: Entering OpenClaw / agent runtime / AI-native infrastructure — system construction phase

Key shift: from "AI as tool" to "AI as environment" (AI 作为环境). This axis is highly coupled with indie dev methodology and systems thinking.

## Related Skills
- `lean_product`: AI is the execution layer rewriting indie dev methodology
- `self_modeling`: Another Self engineering depends on AI-native infrastructure
- `systematization_experience`: The more you rely on systematized AI workflows, the more you must guard against flattening experience into process
