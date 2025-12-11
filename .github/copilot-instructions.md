# AI Resources - Copilot Instructions

This repository consolidates research, frameworks, and resources for AI-augmented software development. It is a **documentation-only repository** with no code to build or test.

## Repository Structure

### `dev-of-future/` - Developer of the Future Research
Research and frameworks for AI-augmented development, organized by topic:
- `ai-mentoring/` - Team coaching frameworks (10-5-10 pattern, scaling AI skills)
- `ai-tool-selection/` - Criteria for evaluating AI coding assistants
- `ai-workflows/` - SDLC impact analysis and measurement plans
- `design-skills/` - Developer skills improvement plans
- `spec-driven-dev/` - Spec-Driven Development (SDD) frameworks and implementation guides

### `whiskey-log/` - App Development Prompts
PRDs and prompts for "vibe-coded" applications. The main app lives in a [separate repo](https://github.com/sdbroscious/whiskey-log).

## Content Patterns

### Frontier Model Comparisons
Several topics include outputs from multiple AI models (ChatGPT, Claude, Gemini) on the same prompt. When adding new research:
- Store model outputs in a `frontier-model-takes/` or similar subdirectory
- Use consistent naming: `Topic (ModelName).md`
- Reference the original prompt in YAML frontmatter or document header

### AI-Generated Content
Many files are AI-generated research. Mark AI outputs with:
```yaml
---
tags:
  - ai-output
---
```

### README as Index
Each major directory should have a README.md explaining file purposes and evolution. See [ai-tool-selection/README.md](dev-of-future/ai-tool-selection/README.md) as an example.

## Key Concepts

### Spec-Driven Development (SDD)
A core theme: using structured specifications as context for AI coding tools. Key files:
- [sdd-gai-overview.md](dev-of-future/spec-driven-dev/sdd-gai-overview.md) - Overview and open questions
- [SpecDrivenDevelopment Plan (Claude).md](dev-of-future/spec-driven-dev/frontier-model-takes/SpecDrivenDevelopment%20Plan%20(Claude).md) - Comprehensive implementation guide

### AI Mentoring Framework
The 10-5-10 coaching pattern for scaling AI coding skills:
- 10 min demo → 5 min guided practice → 10 min independent challenge
- Emphasizes "Aha! moments" through guided discovery, not feature lectures
- See [ai_code_mentoring.md](dev-of-future/ai-mentoring/ai_code_mentoring.md)

## Writing Style

- Use Markdown with clear heading hierarchy
- Prefer bullet points over prose for actionable items
- Include context about prompt/source when documenting AI outputs
- Link to external repos for actual code (this repo is documentation only)

## When Adding Content

1. Place files in appropriate topic subdirectories
2. Update the root [README.md](README.md) with file descriptions
3. Add directory-level README.md if creating new topic areas
4. Use relative links between documents
